```bash 

mkdir Ecosysteme_Marin

cd Ecosysteme_Marin/

pwd
/home/goyeir/AdminLinux/EXO1/Ecosysteme_Marin

mkdir Donnees
mkdir Articles
mkdir Images
mkdir Rapports

ls
Articles  Donnees  Images  Rapports

vim Article.txt

*vim- p*
'Les coraux qui s’assemblent pour former des récifs coralliens abritent 25% de la vie marine de notre planète. Mais si nous n’agissons pas d’urgence pour faire face au changement climatique, à la pollution, à la surpêche et aux autres menaces qui planent sur eux, ces magnifiques organismes où la vie prospère pourraient bel et bien disparaître.'
*vim- :wq *

cat Article001.txt
'Les coraux qui s’assemblent pour former des récifs coralliens abritent 25% de la vie marine de notre planète. Mais si nous n’agissons pas d’urgence pour faire face au changement climatique, à la pollution, à la surpêche et aux autres menaces qui planent sur eux, ces magnifiques organismes où la vie prospère pourraient bel et bien disparaître.'

cp ~/Downloads/le-corail.jpg .

file le-corail.jpg 
"le-corail.jpg: JPEG image data, Exif standard: [TIFF image data, little-endian, direntries=17, height=5304, bps=218, PhotometricInterpretation=RGB, description=Pocillopora Sp, cette colonie de corail soumise \303\240 un stress thermique est en phase de blanchissement. L'animal a expuls\303\251 son , manufacturer=SONY, model=ILCE-7RM2, orientation=upper-left, width=7952], progressive, precision 8, 1280x640, components 3"

vim donnes.data
*vim- p*
'data = [
	{
		numberrange: "1"
	},
	{
		numberrange: "1"
	},
	{
		numberrange: "10"
	},
	{
		numberrange: "9"
	},
	{
		numberrange: "5"
	}
]'
*vim- :wq*

more donnees.data 
'data = [
	{
		numberrange: "1"
	},
	{
		numberrange: "1"
	},
	{
		numberrange: "10"
	},
	{
		numberrange: "9"
	},
	{
		numberrange: "5"
	}
]'

mv Article.txt Articles/

mv donnes.data Donnees/

mv le-corail.jpg Images/

find . -name Article.txt
'./Articles/Article.txt'

find . -name "*.txt"
'./Articles/Article.txt'

cd ..

find . -name "*.txt"
'./Ecosysteme_Marin/Articles/Article.txt'

cd /

cat /home/goyeir/AdminLinux/EXO1/Ecosysteme_Marin/Articles/Article.txt | grep "coraux"
'Les coraux qui s’assemblent pour former des récifs coralliens abritent 25% de la vie marine de notre planète. Mais si nous n’agissons pas d’urgence pour faire face au changement climatique, à la pollution, à la surpêche et aux autres menaces qui planent sur eux, ces magnifiques organismes où la vie prospère pourraient bel et bien disparaître.'

ls . | grep  "fichierX"

echo "bonjour" > text.txt


/home/goyeir/AdminLinux/EXO1/Ecosysteme_Marin/Articles


usermod -aG sudo toto


```


```Bash

- all passwords toto - 
{
sudo adduser alice

su - alice

sudo chage -M 30 alice

sudo chage -l alice
}

{
sudo adduser bob

sudo chage -M 60 bob

sudo chage -l bob
}

{
sudo adduser charlie

sudo chage -M 90 charlie

sudo chage -l charlie
}

sudo groupadd dev

sudo groupadd admin

sudo usermod -aG dev alice

sudo usermod -aG admin alice

sudo usermod -aG sudo alice

visudo
// bob ALL=(ALL) 
// which apt
// /user/bin/apt
#user privilages spec
bob ALL=(ALL) NOPASSWD: /usr/bin/apt
charlie ALL=(ALL:ALL) ALL

sudo chage -W 7 alice

#members of group sudo to ex any command
%dev ALL=(ALL)





sudo userdel -r 

```

#### Ls -lh

| object type | user | group | world |
| ----------- | ---- | ----- | ----- |
| -           | rw-  | rw-   | rw-   |

| bit | meaning            | binary |
| --- | ------------------ | ------ |
| r   | read               | 4      |
| w   | wright             | 2      |
| x   | execute as program | 1      |

#### chmod 

```bash

vi cmdls
{vim
ls -la
}

sh cmdls

chmod 700 cmdls

ls -l

chmod 600 cmdls

./cmdls
// fail

chmod +x cmdls

chmod 660 cmdls

chmod 777 cmdls
// never do this // security and performance problems

etc.

```

```bash

mkdir -p /tmp/toto/tata

cd toto/

ls

pwd

ls -l /var/toto/

echo "ls -l" > /var/toto/tata/script.sh

chmod +x -R /var/toto/tata/script.sh

ls /var/toto/tata/script.sh

chmod +x /var/toto/tata/script.sh

sh /var/toto/tata/script.sh



```

#### chown

```bash

useradd blablabla test1
su test1

mkdir testfile

ls -l

exit
ls

cd /home/test1/

cd ..

ls -l /home/test1/

useradd test2
su test2

cd test1/

cd ..

ls

ls -l

exit

chmod 600 /home/test1/
chmod 600 /home/test2/

su test1 

cd

cd /home

cd test2/
:Permission denied

exit

chown test1:test1 /home/test2/

ls -l /home/test2/

ls -l /home/

su test1 
cd test2/
exit

chown -R test1:test1 /home/test2/

usermod -aG sudo test1

// reload may be required

su test1

cd

cd /home/test1

//////

adduser test1 

sudo usermod -aG sudo test1

su test1

mkdir REP1

ls -l

exit

chown -R test1 /home/test1/REP1
// -R acced a tout les fichier dans le dir pas seulment le dir

adduser test2

sudo chown -R test2:test2 test1

su test2

ls

cd test1
cd REP1

exit

cd test1

ls

chmod 600 REP1



su test1

ls
cd rep1
//permission denied

```

```bash

mkdir /opt/prometheus

cd /opt/prometheus

sudo wget https://github.com/prometheus/prometheus/releases/download/v2.52.0/prometheus-2.52.0.linux-amd64.tar.gz

sudo tar -xvzf prometheus-2.52.0.linux-amd64.tar.gz 

sudo mv prometheus-2.52.0.linux-amd64/* /opt/prometheus/

adduser prometheus

sudo usermod -aG prometheus prometheus

chown -R prometheus:prometheus /opt/prometheus/

ls -l

chmod -R 705 /opt/prometheus/

chmod -R 700 /opt/prometheus/prometheus.yml 

ls -l
{
total 364716
-rwxr-x--- 1 prometheus prometheus     11357 May  8 22:11 LICENSE
-rwxr-x--- 1 prometheus prometheus      3773 May  8 22:11 NOTICE
drwxr-x--- 2 prometheus prometheus      4096 May  8 22:11 console_libraries
drwxr-x--- 2 prometheus prometheus      4096 May  8 22:11 consoles
drwxr-x--- 4 prometheus prometheus      4096 May 15 12:25 data
-rwxr-x--- 1 prometheus prometheus 138438117 May  8 21:58 prometheus
drwxr-x--- 2 prometheus prometheus      4096 May 15 12:22 prometheus-2.52.0.linux-amd64
-rwxr-x--- 1 prometheus prometheus 104659766 May  8 22:25 prometheus-2.52.0.linux-amd64.tar.gz
-rwx------ 1 prometheus prometheus       934 May  8 22:11 prometheus.yml
-rwxr-x--- 1 prometheus prometheus 130329948 May  8 21:58 promtool
}

sudo adduser test

sudo usermod -aG prometheus test

su - test

cd /opt/prometheus/

ls -l

```
## Day 3

```bash
systemctl start prometheus

wget

tar xzvf prometheus

cd /opt/prometheus
ubuntu $ sudo mv prometheus-2.52.0.linux-amd64/* /opt/prometheus/
ubuntu $ ls
LICENSE  NOTICE  console_libraries  consoles ' prometheus ' prometheus-2.52.0.linux-amd64  prometheus-2.52.0.linux-amd64.tar.gz  prometheus.yml ' promtool ' 
ubuntu $ 

'[Unit]
Description=Prometheus application /site.
Wants=network-online.target
After=network-online.target

[Service]
Type=simple
User=root
Group=root
RemainAfterExit=yes
ExecStart=/opt/prometheus/prometheus start
ExecReload=/bin/kill -HUP $MAINPID
ExecStop=/opt/prometheus/prometheus stop

Restart=on-failure

[Install]
WantedBy=multi-user.target'

diff prometheus.service prometheus.service.backup
>differences


```

```bash

du -hl | ls -l

```

### aprem

```Bash

useradd -d /home/user1 -m user1
-d repository
-m username

cat /etc/passwd
cat /etc/group
#pour trouver tout les utilisateur

su user1
# connecter a un untilisateur

passwd user1
#changer mot de pass de lutilisateur

adduser test1
"Adding user `test1' ...
Adding new group `test1' (1003) ...
Adding new user `test1' (1003) with group `test1' ...
Creating home directory `/home/test1' ...
Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for test1
Enter the new value, or press ENTER for the default
        Full Name []: 
        Room Number []: 
        Work Phone []: 
        Home Phone []: 
        Other []: 
Is the information correct? [Y/n] y"

su test1

apt update -y
#denied
sudo apt update -y
#test1 is not in the sudoers file.  This incident will be reported.

# All Config files in /etc/  

exit

root$ 

nano /etc/sudoers/

sudo usermod -aG sudo test1
# add user to sudo group

apt install -y
# -y pre answers confirmation questions

sudo groupadd ADMIN
#create user group

cat /etc/group
#Show groups

sudo usermod -aG ADMIN test1

ubuntu $ su test1
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

test1@ubuntu:/home$ id
uid=1003(test1) gid=1003(test1) groups=1003(test1),27(sudo),1004(ADMIN)


sudo usermod -g ADMIN test1
cat /etc/group
'ADMIN:x:1004:test1'

sudo mkdir REP1
ls
REP1
ls -l
total 4
drwxr-xr-x 2 root root 4096 May 16 13:33 REP1
#Repository belongs to root by default 


cd /var/

sudo mkdir REP2
ls -l
drwxr-xr-x  2 root root   4096 May 16 13:38 REP2

chown -R user1:ADMIN /var/REP2/
#change owner of file 
ls -l
drwxr-xr-x  2 user1 ADMIN  4096 May 16 13:47 REP2

touch 'script.sh'

ls -l
-rw-r--r-- 1 user1 ADMIN 0 May 16 13:47 script.sh

//

sudo chmod -R 600 REP2/

| object type | user | group | world |
| ----------- | ---- | ----- | ----- |
| -           | rw-  | rw-   | rw-   |

| bit | meaning            | binary |
| --- | ------------------ | ------ |
| r   | read               | 4      |
| w   | wright             | 2      |
| x   | execute as program | 1      |






source.liste

nano source.list
 paste {deb *ref*}



```

## EXO gestion des packet avec apt


