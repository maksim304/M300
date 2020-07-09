# Lb3 Dokumentation - Modul 300

## Einleitung

Zuerst musste ich mich mit Docker auseinandersetzen, da ich noch nie zuvor mit Docker gearbeitet habe. Als ich es dan im Griff hatte, entschied ich mich mithilfe von Wordpress, zwischen einem Webserver-Container und einem Db-Container eine Verbindung erstellt, damit der Webserver Zugriff auf die Db hat.

### Vorgehen

#### K3

Ich habe den bestehenden Docker-Container kombiniert, als Backend und Frontend als Desktop-App und das Volumen zur persistenten eingerichtet, indem ich eine Verbindung zwischen der VM und Worpress hergestellt habe. Um überhaupt zugriff auf den Server zu haben, welcher von der TBZ zur verfügung gestellt wurde, musste ich zuerst Wireguard einrichten. Danach konnte ich über Git-Bash auf die VM zugreifen, auf welcher Docker bereits installiert war.

Als nächstes habe ich einen MySQL-Container ausgeführt. Dies habe ich mit diesem Befehl gemacht:

```Ruby
sudo docker run --name my-db -e MYSQL_ROOT_PASSWORD=db-password -d mysql
```

Danach habe ich einen Wordpress-Container ausgeführt und zwar mit folgendem Befehl:
```Ruby
sudo docker run --name my-wordpress -p 8080:80 --link my-db:mysql -d wordpress
```
Nachdem ich diese zwei command ausgeführt habe, musste ich auf diesen Link http://192.168.113.19:8080 gehen, um die installation zu beenden. 


##### Test

Ob alles funktioniert hat, habe ich so getestet, indem ich die welche mir zugewiesen wurdene IP (192.168.113.19) in die url eingebe.

![](https://github.com/maksim304/M300/blob/master/LB3/img/wordpress-hallo%20welt.PNG)

 #### K4

 Bei der Service-Überwachung habe ich mich für das Docker Tool 'cAdvisor' entschieden, da es mir einen grafischen Überblick über den Ressourceneinsatz und Performance-Metriken von Containern anzeigt.

 ![](https://github.com/maksim304/M300/blob/master/LB3/img/wordpress-hallo%20welt.PNG)