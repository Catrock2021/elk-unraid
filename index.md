## ELK auf Unraid installieren & einbinden von OPNSense / Sensei

Ich habe lange versucht, ELK so zum laufen zu bekommen, dass alle Daten von meiner Sense-Box an mein Unraid gesendet werden. Dies möchte ich im folgenden Artikel mit euch gemeinsam durchgehen. Dies können wir abschließend dann in [Grafana](https://Grafana.com/) einbinden. 

Das komplette Tutorial nutze ich eine VM in Kombination mit Unraid. Ich würde sagen, wir fangen jetzt an!

### 1. Installation von Ubuntu-Server

In meinem Fall habe ich mir auf meinem Unraid-Server eine VM erstellt. Diese hat 100GB Festplattenspeicher bekommen, 8GB RAM und 4 CPU Kerne. Wir downloaden uns [Ubuntu-Server](https://ubuntu.com/download/server) und installieren dies. Bitte setzt bei dem Punkt SSH einen Haken! Damit wir uns später via Putty etc. auf den Server schalten können. 

<img src="https://user-images.githubusercontent.com/79945933/109850031-5a5ae180-7c52-11eb-90dc-fa3484194fb6.png" width="200px" style="display: block; margin: audo;" />



WICHTIG
Da ELK, wenn es richtig läuft, ständig Daten schreibt und löscht, solltet Ihr das ganze auf einer SSD realisieren. Dies schont die HDD's und ist auch noch sehr leise. 



<img src=" " style="display: block; margin: auto;" />


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
