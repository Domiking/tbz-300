---


---

<h1 id="m300---dokumentation-von-ramon--caner">M300 - Dokumentation von Dominic Kleiner und Yanik Togo</h1>
<p>Im Modul 300 haben wir plattformübergreifende Dienste angeschaut und deren Umsetzung mit VMs und Container angeschaut und umgesetzt.<br>
Diese Dokumentation behandelt die Umsetzung von Docker.</p>
<h2 id="auftrag">Auftrag</h2>
<p>Unser Auftrag war es in einer Containerisierten Umgebund Dienste anzubieten.<br>
Container bieten den Vorteil gegenüber virtuellen Maschinen, dass sie .<br>
</p>
<h2 id="github">GITHUB</h2>
<p>Auf Github haben wir uns registriert, damit wir Repositories pushen und auch klonen können.</p>
<p>Github macht es einem möglich mit anderen Leuten zusammen zu kollaberieren und gleichzeitig am gleichen Projekt zu arbeiten</p>
<h2 id="docker">Docker</h2>
<p>Docker bietet einem die Möglichkeit Container aufzusetzen und diese zu Verwalten.</p>
<p><strong>Docker</strong>  ist eine  Open Source-Software zur Isolierung von Anwendungen mit Containervirtualisierung.</p>
<blockquote>
<p><em>“Docker vereinfacht die Bereitstellung von Anwendungen, weil sich Container, die alle nötigen Pakete enthalten, leicht als Dateien transportieren und installieren lassen. Container gewährleisten die Trennung und Verwaltung der auf einem Rechner genutzten Ressourcen. Das beinhaltet laut Aussage der Entwickler: Code, Laufzeitmodul, Systemwerkzeuge, Systembibliotheken - alles was auf einem Rechner installiert werden kann”</em></p>
</blockquote>
<h2 id="eigener-service">Eigene Dienste</h2>
<p>Eigene Dienste aufzusetzen ist mehr oder weniger simpel, in dem man ein Dockerfile beschreibt, von welchem man Images erstellen kann.<br>
Hier ein kleines Beispiel:</p>
<pre><code>FROM ubuntu:16.04
</code></pre>
<p>Hier wird mit dem <code>FROM</code> Paramter angegeben, von welchem Basisimage <code>Ubuntu</code> vom Docker Repository heruntergeladen werden soll.<br>
Mit<code>:16:04</code> geben wir die gewünschte Version an.<br>
Docker bietet einem viele vorgefertigte Images, die man unter <a href="https://hub.docker.com/">https://hub.docker.com/</a> anschauen können.</p>
<p>Wie man hier sehen kann, haben wir im Moment keine Container.</p>
<p><img src="https://perrone.myqnapcloud.com:450/share.cgi/1_keine%20container.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2FNeuer%20Ordner&amp;filename=1_keine%20container.PNG&amp;openfolder=normal&amp;ep=" alt="BILD 1"></p>
<p>Als erstes haben  das Hello-World ausgeführt um zu sehen ob Docker richtig installiert wurde.</p>
<p><img src="https://perrone.myqnapcloud.com:450/share.cgi/2_hello%20world.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2FNeuer%20Ordner&amp;filename=2_hello%20world.PNG&amp;openfolder=normal&amp;ep=" alt="BILD 2"></p>
<p>Wir haben mit befehl **** den Containe rmit dem Apache Image gebuildet und diesen später mit befehl **** gestartet.<br>
Wie man sieht, sind wir nun im server drin.</p>
<p><img src="https://perrone.myqnapcloud.com:450/share.cgi/3_apache%20after%20build.PNG?ssid=02YbC2K&amp;fid=02YbC2K&amp;path=%2FNeuer%20Ordner&amp;filename=3_apache%20after%20build.PNG&amp;openfolder=normal&amp;ep=" alt="BILD 3"></p>




## Befehle für Docker

    docker run hello-world --> Installation Überprüfen
    docker run -it ubuntu /bin/bash --> Container mit Shell
    docker run -d ubuntu sleep 20 --> Container im Hintergrund
    docker run -d ubuntu touch /tmp/lock --> Container und File erstellen
    docker ps --> Überblick über alle Containern
    docker rm <name> --> Container löschen
    docker rm `docker ps -a -q` --> Beendenten Container lösch.
    docker rm -f `docker ps -a -q` --> Auch Aktive löschen
    docker rmi ubuntu --> ISO löschen
    docker start <id> --> Gestoppte Container starten
    RAM begrenzen --> docker run -m 2096m --memory-swap 2096m




## Docker User

<p>Mit diesem Befehl kann ein Docker user erstellt werden </p>

RUN groupadd -r User_Group && useradd -r -g User_group xyz
