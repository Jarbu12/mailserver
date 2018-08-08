Cara install mailserver BIND 9 dan Postfix 

Pertama setting IP dulu 
cd /etc/network/interfaces

Setelah itu install BIND9 dengan cara
sudo apt-get install bind9

Buka folder BIND copy and replace 3 file tersebut ke dalam main folder bind

->restart Bind -> service bind9 restart
jika tak ada error lanjut  edit resolv.conf atau replace aja file nya yang ada di ETC folder

coba tes dulu mengggunakan nslookup

setelah itu install postfix

sudo apt-get install postfix courier-imap courier-pop

setelah itu replace main.cf pada folder postfix 

selanjutnya ketikan telnet 192.168.1.32 25 (port 25 untuk kirim)
ketik
mail from:user1
rcpt to:user1
data
isikan data bla bla bla lalu diakhiri dengan titik ( . )
untuk keluar ketik "quit"

selanjutnya untuk cek apakah email masuk ketikan
telnet 192.168.1.32 110(port 110 untuk menerima pesan)
ketik
user user1
pass as(password usermu)
stat
retr 1(tergantung pesan ke berapa)
