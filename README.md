## Il est temps d'immigrer vers **Lunix** et supporter le monde d'**OpenSource**##
Pour commencer , j'ai choisi d'installer **Ubuntu 16.04** à coté de **KaliLinux** pour quelques raisons.
Le dépôt suivant contient la configuration que j'utilise souvent pour démarrer mes projets vitement aussi l'ensembles des tweaks que j'installe sur mon pc 

**Voici ce qui fait la force et le succès de Ubuntu:**

 1. **disponible gratuitement et librement :** tout un chacun peut télécharger gratuitement et légalement une copie d'Ubuntu et l'installer pour lui-même et d'autres personnes. Il peut aussi obtenir le code ayant servi à construire Ubuntu, l'étudier, le modifier et le redistribuer ensuite (avec ou sans rétribution financière) en toute légalité ;
 2. **stable** : 
*Pas besoin de réinstaller régulièrement tout le système d'exploitation 
*Si les droits sont correctement gérés, les utilisateurs "classiques" sont incapables de modifier quoi que ce soit qui pourrait compromettre la stabilité générale ;
 3. **sécurisé**
les virus et autres vers attaquent principalement Windows ;
il faut réellement le vouloir pour "installer" un des rares virus destinés à Linux ;
 4. **Ubuntu continuellement vers l'avant**
le système des dépôts de logiciels permet d'installer en quelques clics, avec une facilité déconcertante, des logiciels extrêmement variés. Les dépôts contiennent des paquets logiciels dont le nombre est passé à 41 000. Dans ce cadre, on peut dire que Ubuntu est parfaitement adapté pour exploiter Internet. Des miroirs du dépôt Ubuntu sont disponibles localement pour accélérer les transferts. La compatibilité générale (mais imparfaite) avec les paquets Debian permet une bonne interaction entre les 2 distributions ;
les mises à jour de sécurité sont simplifiées et gérées graphiquement : une tâche de notification vous prévient lorsqu'une mise à jour est disponible. En quelques clics, votre machine et vos logiciels sont sécurisées ;
 4. **une vaste communauté contributive **

## Screenshots ##
 ![](https://github.com/aminelch/workspace/blob/master/screenshots/1.png)

 ![](https://github.com/aminelch/workspace/blob/master/screenshots/2.png)
 
 ![](https://github.com/aminelch/workspace/blob/master/screenshots/3.png)

## Configuration ##

###Removing Guest Session at login in Ubuntu ###

    sudo -H gedit /etc/lightdm/lightdm.conf
  
  If the file exists, then just add the following line:
  

    allow-guest=false
   Otherwise copy and paste the following into it:
   

    [SeatDefaults]
	user-session=ubuntu
	greeter-session=unity-greeter
	allow-guest=false


###.bashrc ###
[.bashrc](https://github.com/aminelch/workspace/blob/master/.bashrc)


## Packages ##
 1.**Mysql workbench**	
	[https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/) 

 2.**remarkable Markdown Editor**		
 [https://remarkableapp.github.io/linux.html](https://remarkableapp.github.io/linux.html) 
 
 3.**arc-icon-theme**
	

git clone https://github.com/horst3180/arc-icon-theme --depth 1 && cd arc-icon-theme
./autogen.sh --prefix=/usr
sudo make install	

4.**SublimeText**
 

sudo add-apt-repository ppa:webupd8team/sublime-text-2 && sudo apt-get update && sudo apt-get install sublime-text

#### Packages names ####
	

* Materialize
* Boxy Theme
* PHP Grammer
* Emmet
* Sublime Linter
* CackePHP 
* CSS3 autocomplete

## Restart nautilus from terminal ##

nautilus -q && nautilus &

##Installing Java 
	sudo apt-get install default-jre gcj-5-jre-headless
	
	sudo apt-get install gcj-4.8-jre-headless gcj-4.9-jre-headless openjdk-9-jre-headless
	 
##Share wifi connection

* Create a connection
	
		nmcli connection add type wifi ifname '*' con-name my-hotspot autoconnect no ssid my-local-hotspot

* Put it in Access Point

		nmcli connection modify my-hotspot 802-11-wireless.mode ap 802-11-wireless.band bg ipv4.method shared

* Set a WPA password (you should change it)

		nmcli connection modify my-hotspot 802-11-wireless-security.key-mgmt wpa-psk 802-11-wireless-security.psk myhardpassword

* Enable it (run this command each time you want to enable the access point)

		nmcli connection up my-hotspot


* Disable it with :

		nmcli connection down my-hotspot
	
##Is Gcc enable
	#!/bin/sh
	gcc -v
	if [ $? != 0 ]; then
	       echo "GCC is not installed!"
	fi
	ld -v
	if [ $? != 0 ]; then
	        echo "Please install binutils!"
	fi
[isgccavaible.sh](https://github.com/aminelch/workspace/blob/master/isgccavaible.sh) 