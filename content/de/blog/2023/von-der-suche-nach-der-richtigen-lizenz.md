---
title: "Von der Suche nach der richtigen Lizenz"
date: 2023-01-27
author: ruaq
tags: ["Gedanken", "Lizenz"]
description: "Open-Source ist keine Frage. Aber welche Lizenz ist hier die Richtige? Passt die GNU AGPLv3 wirklich oder gibt es bessere Alternativen?"
---

Die Zeit schreitet voran, die Veröffentlichung von [courservio](https://courservio.de) rückt näher und auch die Entwicklung der Funktionen läuft gut. Das *Feedback* in Hinsicht auf *gewünschte Funktionen* ist momentan noch sehr übersichtlich. Aber dies bietet mir die Möglichkeit, mehr Augenmerk auf Funktionen zu legen, die mir selbst *am Herzen liegen*.  
So ist jetzt auch die automatisierte Erstellung von Bescheinigungen aus .docx Dateien als Vorlage voll funktionsfähig. Auch ein *Stresstest* mit (unrealistischen) 2.500 Teilnehmer\*innen im Kurs / Bescheinigungen am Stück lief dabei problemlos durch.

Eine Sache, mit der ich bislang nicht zu 100 % glücklich (gewesen) bin, ist die Lizenz. Dies war bislang die [GNU AGPLv3](https://de.wikipedia.org/wiki/GNU_Affero_General_Public_License). Die Entscheidung für diese Lizenz beruhte in erster Linie darauf, dass diese ein *starkes [Copyleft](https://de.wikipedia.org/wiki/Copyleft)* bietet, die *Saas-Nutzung* abdeckt und das [ASP-Schlupfloch](https://de.wikipedia.org/wiki/GNU_Affero_General_Public_License#ASP-Schlupfloch) geschlossen wird.  
Hintergrund ist, dass ich sichergehen möchte, dass [courservio](https://courservio.de) später **nicht** (in Teilen) von closed-source Anbietern / für proprietäre Produkte genutzt werden kann.

*Problem* mit der AGPL ist, dass diese auf *amerikanischem Recht* beruht. Hiernach ist z. B. die *Aufgabe des Urheberrechts* vollständig möglich und entsprechend in der Lizenz verankert. Dies ist aber z. B. nach deutschem Recht nicht möglich. Eine *Kleinigkeit*, die vermutlich niemals zum Tragen kommen wird. Aber auch andere *Kleinigkeiten* stören hierbei, da diese teilweise zu *rechtlicher Unsicherheit* führen.  
Ein Punkt, der mich persönlich sehr stört, ist § 8. Dieser regelt, dass die Rechte aus der Lizenz auch bei Verstößen weiter bestehen bzw. wiederhergestellt werden, wenn man diese innerhalb von 30 Tagen nach *geeignetem Hinweis* abstellt. Somit ist es (meiner Auffassung nach) möglich die Lizenz zu *ignorieren* und erst auf Hinweis (des Lizenzinhabers) diese Verstöße beenden / rückgängig machen muss, um dann wieder in den vollen Genuss der Vorteile und Freiheiten der Lizenz zu gelangen. Schönes Beispiel für dieses Vorgehen war dabei die *Luca-App*, welche ja auch diverse Bibliotheken und Programme unter *Open-Source-Lizenz* verwendeten, ohne hierauf hinzuweisen und dies nachholen konnte, nachdem es aufgefallen war.

Eine Alternative wäre die [Elastic-Lizenz 2.0](https://www.elastic.co/de/licensing/elastic-license/faq) gewesen. Diese lässt ebenfalls relativ viele Freiheiten untersagt eine SaaS-Nutzung aber vollständig. Ein großes Kriterium dagegen ist jedoch, dass diese keine (echte) *Open-Source-Lizenz* ist, da sie nicht (vollständig) der [Definition](https://de.wikipedia.org/wiki/Open_Source_Initiative#Definition_von_Open_Source) entspricht.

Beide Lizenzen liegen außerdem (wie fast alle Lizenzen) offiziell *nur* in englischer Sprache vor, auch wenn es *inoffizielle* und damit *nicht verbindliche* Übersetzungen gibt.

Diversen anderen Lizenzen fehlt die *[Copyleft-Komponente](https://de.wikipedia.org/wiki/Copyleft)*. Diese ist mir aber wichtig, um wie gesagt zu verhindern, dass [courservio](https://courservio.de) bzw. dessen Code von anderen Anbietern genutzt werden kann, ohne etwas *zurückzugeben*, wie dies leider häufig mit Open-Source-Software geschieht.

---

Die *Lösung* dieser *Probleme* ist (für mich) die [European Union Public Licence (EUPL)](https://de.wikipedia.org/wiki/European_Union_Public_Licence). Die Besonderheit ist hier, dass diese Lizenz von der *Europäischen Kommission* stammt, sie u. a. zur GNU AGPL kompatibel ist, jedoch mit Blick auf die rechtlichen Gegebenheiten in der EU entworfen wurde. Außerdem ist die EUPL v1.2 in [23 Sprachen](https://joinup.ec.europa.eu/collection/eupl/eupl-text-eupl-12), darunter selbstverständlich auch [deutsch](https://joinup.ec.europa.eu/sites/default/files/custom-page/attachment/eupl_v1.2_de.pdf) als offizielle Übersetzung verfügbar. Zudem passt der Lizenztext auf vier DIN A4 Seiten und damit deutlich kürzer und verständlicher.  
Dennoch werden hier alle Möglichkeiten der Verwendung inkl. des Betriebes als *SaaS* bedacht und ein entsprechendes Copyleft angewendet. Ziel dieser Lizenz ist es ausdrücklich, dass Software als Open Source in der EU rechtssicher erstellt und verwendet werden kann.

Für mich besonders erfreulich ist *"12. Beendigung der Lizenz"*, worin klargestellt wird, dass die eingeräumten Rechte erlöschen, wenn gegen die Lizenzbedingungen verstoßen wird. Hier ohne den Zusatz, dass dies rückgängig machbar wäre, nur weil man sich nach Hinweis dann doch daran hält. Jede\*r bekommt also dauerhaft und unwiderruflich die Rechte eingeräumt, solange sich an die *Spielregeln* gehalten wird.  
Außerdem ist die EUPL seit v1.1 von der [Open Source Initiative](https://de.wikipedia.org/wiki/Open_Source_Initiative) *bestätigt*.

Nach diversen Überlegungen und Vergleichen dieser und vieler anderer Open-Source-Lizenzen ist also nun die Entscheidung gefallen, dass die EUPL den Zielen der GNU AGPLv3 und auch meinen Ansprüchen entspricht, jedoch verschiedene Vorteile bietet und daher die EUPL v1.2 als zukünftige Lizenz verwendet wird.

Damit ändert sich die Lizenz (bzw. wurde im [Repository](https://github.com/courservio/courservio) bereits geändert) und trotzdem bleibt alles gleich. Denn dieser Schritt bekräftigt noch einmal, dass [courservio](https://courservio.de) freie Software ist und auch immer bleiben wird.