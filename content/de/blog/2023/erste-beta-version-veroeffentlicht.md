---
title: "Erste beta Version veröffentlicht"
date: 2023-02-16
author: ruaq
tags: ["release", "announcement"]
description: Die erste beta-Version ist veröffentlicht. Verspätet und anders als geplant aber veröffentlicht. Sprechen wir über Hintergründe und Zukunft.
---

Die erste beta-Version von courservio ist veröffentlicht. Zwar (leicht) verspätet und nicht mit den Funktionen, die geplant waren, aber veröffentlicht. Die Gründe dafür sind einfach wie komplex.  
Eine kurze ~~Entschuldigung~~ Erklärung:

Der Grund für die (leichte) Verspätung ist einfach: *Privatleben ;-)*  
Ich war gestern den ganzen Tag *unterwegs* und war tatsächlich erst kurz nach Mitternacht wieder zu Hause. *Heute* geht auch nur noch eine Stunde. Damit ist klar, dass die Tage einfach zu kurz sind (und, ich gar nichts dafür kann).

Dass die nun veröffentlichte Version (noch) nicht so *umfangreich* bzw. nicht mit allen geplanten Funktionen ausgestattet ist, ist jedoch (eher) anderen Umständen *geschuldet*. (Wobei sich dies sicher relativieren würde, wenn die Tage länger wären.)  
Die Tatsache, dass courservio **kein** Software-as-a-Service Produkt/Angebot ist, bringt andere *Probleme* mit sich. Unter anderem, dass Dinge *selbst* gemacht werden müssen. Und auch wenn für mich viele Dinge selbstverständlich und daher recht einfach sind, wird dies bei Weitem nicht auf jede Nutzer\*in von courservio zutreffen. Daher musste ich hier *Umdenken* und bin bemüht, Dinge so einfach und wenig technisch wie möglich zu gestalten. Die Zeit dafür fehlt aber bei der Entwicklung an anderer Stelle. Sprachen wir schon über zu kurze Tage?

Eine sehr wichtige, aber vorher nicht (in dieser Form) bedachte Funktion ist die *Auto-Update-Funktion*. Wege für ein einfaches Updaten waren mir selbstverständlich bereits zuvor bekannt und bewusst. *Einfach* aus meiner Sicht. (git ein Begriff? Nicht? Das meine ich...) Und mal ehrlich: Wie viele Menschen machen (regelmäßig) Updates? (Ich weiß ja, wie *nervig* diese schon in der Entwicklung über mehrere Systeme sind...) Insbesondere während der beta-Phase wird es jedoch sicher häufig Updates geben. Und auch danach weiterhin regelmäßig.  
Um sicherzugehen, dass diese Updates auch regelmäßig eingespielt werden, hat bereits die erste beta-Version (v0.1.0) eine Funktion, um sich automatisch und regelmäßig selbst zu updaten. Standardmäßig geschieht dies täglich (um 03:45 Uhr) im Hintergrund und ohne die Notwendigkeit einer Benutzerinteraktion. Hierbei kann selbst gewählt werden, ob auf das *letzte Release* (also die letzte veröffentlichte Version) oder den *letzten Commit* (die neusten hochgeladenen Dateien) aktualisiert werden soll. Selbstverständlich gibt es auch die Möglichkeit, die automatischen Updates zu deaktivieren und *von Hand* zu aktualisieren.

Damit kommen wir dann zu einem weiteren Punkt. Denn solche Einstellungen stehen in einer Config Datei. Und in dieser Angaben zu ändern ist vermutlich nicht für jede\*n alltäglich. Daher gibt es nun eine *Setup Funktion*, mit der (einige) Einstellungen gemacht werden können. Viele Einstellungen können darüber mit *Stand heute* (16.02.2023) noch nicht gemacht werden. (Wer daran schuld ist, dürfte klar sein, oder?) Das wird sich in Zukunft selbstverständlich noch ändern.

Und dabei fällt mir eine dritte Sache ein, die *schmerzhaft* fehlt. Es existiert (noch) keine Dokumentation. Mir sind alle Funktionen und Funktionsweisen vollkommen klar. Aber ich habe diese auch geschrieben. Dabei habe ich versucht, es so intuitiv und simpel wie möglich zu gestalten. Denn *überladene* Programme, für die es einer mehrstündigen Einweisung bedarf, sind mir ein Graus.  
Bei einer unvollständigen Software ist eine *Erklärung* aber zweifelsohne zumindest sinnvoll. Eines der Ziele der beta-Phase ist jedoch auch zu zeigen, wie *gut* es mir (bereits jetzt) gelungen ist, es sinnvoll und intuitiv zu gestalten und was verbessert werden kann. Würde bereits alle *perfekt* funktionieren, wäre es keine beta-Version.

---

Dies führt mich zu einem weiteren Punkt, der für Verzögerung gesorgt hat. Technik kann *versagen* und Dinge können *schiefgehen*. Als Anbieter einer SaaS-Lösung kann man diese überwachen (und tut dies hoffentlich auch). Bei courservio habe ich (bewusst) keine Möglichkeit, diese zu überwachen oder ungefragt zu beeinflussen. Also musste eine Möglichkeit her, dass die Software *sich selbst* überwacht und zumindest mitteilen kann, wenn etwas *schiefgegangen* oder ausgefallen ist.  
Hierbei denke ich in erster Linie an *worker* und *cronjobs*. *Worker* sind *Hintergrundaufgaben* die (wer hätte es vermutet) *im Hintergrund* ausgeführt werden. Dazu zählen zum Beispiel die Erstellung von Bescheinigungen, der Versand von Bestätigungs-E-Mails an Teilnehmer\*innen nach der Buchung und andere Dinge. *Cronjobs* sind *zeitliche geplante* Aufgaben, die ebenfalls im Hintergrund (nach Uhrzeit) ausgeführt werden. So zum Beispiel die Prüfung auf und ggf. Durchführung von neuen Updates oder die regelmäßige Aktualisierung der Sitemap. (Letztere wird für Suchmaschinen wie Google benötigt, um diesen z.B. die neusten Kurstermine mitzuteilen. Anderes Thema aber eine Funktion, die bereits funktioniert. Ich würde hier jetzt gerne auf die Dokumentation verweisen. Erkennt man ein Muster in der Problematik?)

Zur Überwachung gibt es nun eine *Heartbeat*-Funktion. Anhand dieser wird bereits bei der *Installation* geprüft, ob *worker* und *cronjob* korrekt eingerichtet sind. (Die Wahrscheinlichkeit, dass diese danach wieder ausfallen, ist relativ gering.) Aber auch eine dauerhafte Kontrolle bzw. Überwachung ist damit manuell oder automatisiert mit z.B. [upptime](https://upptime.js.org/) möglich. (Tolle Software übrigens. Ebenfalls Open Source und bei uns schon lange für die Überwachung anderer Dienste im Einsatz.) Ja, Dokumentation dazu kommt (zeitnah)...

---

Um der Dokumentation etwas vorzugreifen: courservio ist auf [GitHub](https://github.com/courservio/courservio) verfügbar. Die Update-Funktion lädt neue Versionen ebenfalls direkt von dort. Ob ein Download von *eigenen Servern* sinnvoller wäre, wäre vermutlich zu diskutieren. Aber eine Server-IP dürfte kein allzu großes Geheimnis oder *persönliches Datum* sein.

Es steht also jede\*r frei, sich dort die aktuelle Version herunterzuladen und zu installieren. Die [README](https://github.com/courservio/courservio/blob/main/README.md) wird sicher als Erstes angepasst, allerdings englisch sein und nur rudimentäre Anweisungen enthalten. Für die meisten Menschen wird dies vermutlich wenig verständlich sein.

Eine Dokumentation und eine *Schritt-für-Schritt-Anleitung* wird wie erwähnt zeitnah folgen und zukünftig erweitert werden. Hinweise hierzu werde ich in die Kommentare (unter diesem Beitrag) schreiben.

---
**Update:**

Die Dokumentation ist inzwischen unter https://docs.courservio.de online. Die [Installation](https://docs.courservio.de/de/docs/installation/einfuehrung/) auf einem [uberspace](https://uberspace.de) ist dort bereits beschrieben. Weitere Anleitungen erfolgen nach und nach.

Auch die Dokumentation ist selbstverständlich auf [github](https://github.com/courservio/docs) verfügbar und jede\*r eingeladen diese zu ergänzen. Am Ende jeder Seite gibt es auch einen Link, um die jeweilige Seite auf github direkt zu bearbeiten.\
Bei Fragen, auch hierzu gerne das [Forum](https://forum.courservio.de) nutzen. ;-)

---

Als *bevorzugten Hoster* empfehle ich in jedem Fall [uberspace](https://uberspace.de). Dies ist der Anbieter, den ich selbst auch seit Jahren für alles verwende, wenn es nicht zwangsläufig ein *eigener Server* sein muss.

**Aktuelles Angebot:**  
Aufgrund der aktuellen Situation und einer momentan noch geringen Nachfrage bin ich gerne bereits die Installation (kostenfrei) durchzuführen. Wenn hieran Interesse besteht, gerne einfach eine kurze E-Mail an [support@courservio.de](mailto:support@courservio.de) und wir besprechen alles.

---

Alle Probleme, Rückmeldungen, Fragen, (Funktions-)Wünsche usw. können sehr gerne im [Forum](https://forum.courservio.de) gepostet werden. Mehr Feedback könnte mich auch tendenziell dazu motivieren, mehr Zeit der ohnehin *zu kurzen* Tage für courservio aufzuwenden. ;-)