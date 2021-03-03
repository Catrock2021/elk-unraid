## ELK auf Unraid installieren & einbinden von OPNSense / Sensei

Ich habe lange versucht, ELK so zum laufen zu bekommen, dass alle Daten von meiner Sense-Box an mein Unraid gesendet werden. Dies möchte ich im folgenden Artikel mit euch gemeinsam durchgehen. Dies können wir abschließend dann in [Grafana](https://Grafana.com/) einbinden. 

Das komplette Tutorial nutze ich eine VM in Kombination mit Unraid. Ich würde sagen, wir fangen jetzt an!

## 1. Installation von Ubuntu-Server

In meinem Fall habe ich mir auf meinem Unraid-Server eine VM erstellt. Diese hat 100GB Festplattenspeicher bekommen, 8GB RAM und 4 CPU Kerne. Wir downloaden uns [Ubuntu-Server](https://ubuntu.com/download/server) und installieren dies. Bitte setzt bei dem Punkt SSH einen Haken! Damit wir uns später via Putty etc. auf den Server schalten können. 

<img src="https://user-images.githubusercontent.com/79945933/109850031-5a5ae180-7c52-11eb-90dc-fa3484194fb6.png" width="200px" style="display: block; margin: audo;" />


WICHTIG
Da ELK, wenn es richtig läuft, ständig Daten schreibt und löscht, solltet Ihr das ganze auf einer SSD realisieren. Dies schont die HDD's und ist auch noch sehr leise. 

## 2. Wir beginnen mit der Installation von ELK

Wir nutzen hierbei ein Script, welches der User a3ilson geschrieben hat. Dieses Script übernimmt alle benätigten Schritte. Wir loggen uns über das Terminal (Mac) oder Putty (Windows) via SSH auf unseren installierten Server ein. Direkt nach der Anmeldung geben wir uns ROOT-Rechte, damit wir dies nicht andauernt während der Installation machen müssen. Dies geht mit dem Befehl ```sudo su```


1. Zuerst Laden wir uns das Script auf unseren Server
```wget https://raw.githubusercontent.com/pfelk/pfelk/main/etc/pfelk/scripts/pfelk-installer.sh```

2. Dann müssen wir das Script noch ausführbar machen
```chmod +x pfelk-installer.sh```

3. Nun können wir das Script starten
```./pfelk-installer.sh```

Direkt am Anfang werdet ihr gefragt, was Ihr installieren möchtet. Hier wählt Ihr Elasticsearch aus (Nummer 2). Nun lasst ihr den Prozess einmal durchlaufen. Kurz vor dem Ende frägt er euch, ob ihr das Script auf dem Server nach der Installation behalten wollt oder nicht. 

Nach der Installation könnt ihr mit http://[Eure-IP]:5601 auf die Kibana-Weboberfläche gehen. (YEAH)!


## 3. OPNSense und Sensei einrichten 

Damit Elasticsearch in Zukunft Daten bekommt, die wir verarbeiten können, müssen wir nun 2 Sachen einstellen. 

### 3.1 OPNSense 

Zuerst müssen wir OPNSense sagen, wohin es seine Daten "Senden" soll. Hierzu gehen wir System / Settings / Logging & targets und Drücken auf das *+*
Hier gebt ihr Folgende werte ein. (Bei IP bitte eure Elasticsearch IP angeben. Der Port bleibt wie auf dem Foto!)

<img src="https://user-images.githubusercontent.com/79945933/109860290-3d2c1000-7c5e-11eb-861e-13a6322bed88.png" width="200px" style="display: block; margin: audo;" />

Unter Applications wählt Ihr die Sachen aus, die OPNSense senden soll. Auf dem Foto seht Ihr meine Einstellungen

<img src="https://user-images.githubusercontent.com/79945933/109860508-8bd9aa00-7c5e-11eb-913a-5e249512f821.png" width="200px" style="display: block; margin: audo;" />

```markdown
Syntax highlighted code block!


# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Catrock2021/elk-unraid/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
