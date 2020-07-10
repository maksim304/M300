# Lb3 Dokumentation - Modul 300

## Einleitung

Zuerst musste ich mich mit Docker auseinandersetzen, da ich noch nie zuvor mit Docker gearbeitet habe. Als ich es dan im Griff hatte, entschied ich mich mithilfe von Wordpress, zwischen einem Webserver-Container und einem Db-Container eine Verbindung erstellt, damit der Webserver Zugriff auf die Db hat.

### Wichtigste Befehle
| Befehl                    | Beschreibung                                                      |
| ------------------------- | ----------------------------------------------------------------- | 
| `docker run hello-world`            | Ist der Befehl zum Starten neuer Container. |
| `docker ps`              | Gibt einen Überblick über die aktuellen Container |
| `docker image ls`             | Gibt eine Liste lokaler Images aus                  |
| `docker rm [name]`          | Löscht den Docker-Container                                |
| `docker start [id]`            | Startet den Docker-Container                           |
| `docker stop`            | Stoppt den Docker-Container                                 |
| `docker kill`         | Killt den Docker-Container                   |

### Kompetenz 3

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


#### Test

Ob alles funktioniert hat, habe ich so getestet, indem ich die welche mir zugewiesen wurdene IP (192.168.113.19) in die url eingebe.

![](https://github.com/maksim304/M300/blob/master/LB3/img/wordpress-hallo%20welt.PNG)

 ### Kompetenz 4

 Bei der Service-Überwachung habe ich mich für das Docker Tool 'cAdvisor' entschieden, da es mir einen grafischen Überblick über den Ressourceneinsatz und Performance-Metriken von Containern anzeigt. Den 'cAdvisor' brachte ich mit folgendem Befehl zum laufen;

 ```Ruby
 docker run -d --name cadvisor -v /:/rootfs:ro -v /var/run:/var/run:rw -v /sys:/sys:ro -v /var/lib/docker/:/var/lib/docker:ro -p 8181:8080 google/cadvisor:latest
 ```
 

 So sieht das ganze dann aus:

 ![](https://github.com/maksim304/M300/blob/master/LB3/img/cadvisor1.PNG)
 ![](https://github.com/maksim304/M300/blob/master/LB3/img/cadvisor2.PNG)

Ich haette

## Fazit

Ich fand es gut das wir die möglichkeit hatten, um Docker kennezulernen. Auch wenn ich in Zukunft höchstwahrscheinlich nie wieder mit Docker arbeiten werde, emfand ich es als wichtige Erfahrung.








