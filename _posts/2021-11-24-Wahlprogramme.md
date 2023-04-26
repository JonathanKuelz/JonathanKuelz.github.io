---
title: Die Sprache der Wahlprogramme
date: 2021-11-24
categories: [hobby]
tags: [politics]
---

Info: Dieser Artikel ist [auch auf medium verfügbar](https://medium.com/p/389ea4b414de) und wurde dort zuerst veröffentlicht.
Update 24.11: Die Bundestagswahl hat zu einer Ampelkoalition zwischen SPD, Grünen und FDP geführt. Am Ende dieses Artikels ist nun auch eine Analyse zum daraus entstandenen Koalitionsvertrag.

### Nicht immer ist wichtig, was man sagt, stets jedoch, wie man es sagt

Vor der kommenden Bundestagswahl am 26.09 wird häufig die Bitte nach einer stärkeren “inhaltlichen Auseinandersetzung” im Wahlkampf bemüht. Dabei ist die Frage nach Inhalten bei den beteiligten Parteien keineswegs eine triviale: Schließlich gibt es auch innerhalb dieser Richtungskämpfe, Querköpfe und Vordenker*innen, Entwicklung in Positionen und widersprüchliche Kommunikation.

Der größte gemeinsame parteiinterne Nenner scheint da noch das Wahlprogramm zu sein: Teils auf Parteitagen verabschiedet, teils durch die Parteispitzen vorgestellt, stellt es der breiten Öffentlichkeit Schlüsselpositionen und Zukunftsvisionen (mehr oder weniger knapp) vor und dient als Orientierungshilfe bei der Wahlentscheidung. Ein Abgleich der Parteien aufgrund des Wahlprogramms scheint daher einer inhaltlichen Auseinandersetzung so nahe zu kommen, wie es eben geht.

Bei der Kommunikation mit den Wähler*innen (und der Parteibasis) ist dabei jedoch nicht nur von Bedeutung, welche Themen angesprochen werden, sondern auch wie dies geschieht: Werden drängende Fragen der Zukunft als Risiko oder als Chance gewertet? Wird gemahnt oder ermutigt? Werden Kontroversen aufgeworfen oder Gegensätze vereint? Ein inhaltlicher Abgleich der Parteien sollte nicht nur die Themen, sondern auch das verwendete Vokabular in Augenschein nehmen.

Eine einfache, aber effektive Methode, einen solchen Vergleich anzustellen bieten die “computational linguistics” - die Algorithmen-basierte Textanalyse. Ihr Vorteil: Durch eine transparente Kommunikation des Vorgehens, können mögliche (kaum zu vermeidende) “biases”, also eine Voreingenommenheit der analysierenden Person, offen kommuniziert und minimal gehalten werden. In einer wissenschaftlichen Veröffentlichung aus dem Jahre 2009 hat ein Team aus Forschern der Pennsylvania State University, der Michigan State University sowie der Harvard University ein spannendes Konzept zum Abgleich verschiedener “Textkorpora” veröffentlich. In ihrem Paper Fightin’ Words: Lexical Feature Selection and Evaluation for Identifying the Content of Political Conflict beschreiben sie ein Verfahren zum automatisierten Extrahieren Partei-spezifischer “Fighting Words”, also eines Vokabulars, das vornehmlich von einer gewissen Partei verwendet wird. (Ein klassisches Beispiel: Während in der Abtreibungsdebatte in den USA von Demokraten gerne der Begriff “Pro Choice” verwendet wird, sprechen Republikaner in der Gegenposition eher von “Pro Life”)

Zusammengefasst geschieht dabei Folgendes: Die Häufigkeit von Wörtern und Wortfolgen (sogenannte n-grams) wird in verschiedenen Textdokumenten politischer Parteien untersucht. Weicht diese Häufigkeit von dem ab, was erwartet wird, handelt es sich um ein sogenanntes “Fighting Word”: Ein Wort (oder n-gram) welches von einer Partei deutlich häufiger genutzt wird (ein “Kampfbegriff” sozusagen). Dabei wird beachtet, dass einige Wörter naturgemäß häufiger vorkommen als andere und dass statistische Ausreißer ohne Bedeutung durchaus möglich sind. Das oben verlinkte Dokument ist für ein genaueres Verständnis der Methode durchaus lesenswert.

Ich habe mir die Parteiprogramme von CDU/CSU, SPD, AfD, FDP, Die Linke sowie BÜNDNIS 90/DIE GRÜNEN mithilfe des genannten Fighting Word Algorithmus angesehen. Dabei habe ich stets das Programm einer Partei mit der Gesamtheit der anderen Programme verglichen[^vorarbeit]. Anhand dieses Abgleichs wird ein statistisches Modell erstellt, welches eine Erwartung an die Sprache eines Parteiprogramms definiert. Die Folgenden Wörter und Wortfolgen in den einzelnen Programmen weichen dabei besonders stark von dieser Erwartung ab, sind also quasi charakteristisch für die jeweilige Partei.

## Einzelne Wörter
<style>
table th:first-of-type {
    width: 33%;
}
table th:nth-of-type(2) {
    width: 33%;
}
table th:nth-of-type(3) {
    width: 33%;
}
</style>
|                           AFD                            |                           CDU/CSU                           |                         FDP                         |
|:--------------------------------------------------------:|:-----------------------------------------------------------:|:---------------------------------------------------:|
|   ![AFD](/assets/img/wahlprogramme/with_stop/afd.png)    | ![CDU CSU](/assets/img/wahlprogramme/with_stop/cdu_csu.png) | ![FDP](/assets/img/wahlprogramme/with_stop/fdp.png) |
|                 Bündnis 90 / Die Grünen                  |                          Die Linke                          |                         SPD                         |
| ![Grüne](/assets/img/wahlprogramme/with_stop/gruene.png) |   ![Linke](/assets/img/wahlprogramme/with_stop/linke.png)   | ![FDP](/assets/img/wahlprogramme/with_stop/spd.png) |

Üblicherweise werden in der computergestützten Sprachanalyse sehr häufige Wörter, sogenannte “stop words” (der, die, das, und, …) von vornherein ignoriert. In der Betrachtung der Parteiprogramme gibt es jedoch auch hier schon einige interessante Unterschiede, weswegen die obigen Grafiken eine Aanlyse aller Wörter der Parteiprogramme einschließen. Ganz klar fällt direkt der Fokus auf die Wörter “unser” und “wir” bei der Union: Auch wenn SPD und Grüne ebenfalls hauptsächlich in der ersten Person Plural kommunizieren (zu erkennen an der Konjugation der Verben), werden diese von Ihnen dabei nicht so häufig verwendet.

Ein klarer Unterschied lässt sich auch zwischen Regierungspartei und Opposition feststellen: Bei SPD und Union “werden” Zukunftspläne umgesetzt, während die AfD “will”, die Freien Demokraten “fordern” und die Grünen erklären, “es braucht” eine “Transformation”.

Das Bekannte “weiter so” der Union lässt sich übrigens hier (“weiter”, “weiterhin”) ebenso feststellen, wie die Gendergerechte Sprache bei Bündnis 90/Die Grünen. (“innen”)[^innen]

## Wörter unter Ausschluss der stop words

|                          AFD                           |                           CDU/CSU                           |                        FDP                         |
|:------------------------------------------------------:|:-----------------------------------------------------------:|:--------------------------------------------------:|
|   ![AFD](/assets/img/wahlprogramme/1_grams/afd.png)    |  ![CDU CSU](/assets/img/wahlprogramme/1_grams/cdu_csu.png)  | ![FDP](/assets/img/wahlprogramme/1_grams/fdp.png)  |
|                Bündnis 90 / Die Grünen                 |                          Die Linke                          |                        SPD                         |
| ![Grüne](/assets/img/wahlprogramme/1_grams/gruene.png) |    ![Linke](/assets/img/wahlprogramme/1_grams/linke.png)    | ![FDP](/assets/img/wahlprogramme/1_grams/spd.png)  |

Zuerst einmal scheint der eigene Name, wenig überraschend, im Parteiprogramm einer Partei einen prominenten Stellenwert einzunehmen. (Was sowohl das “Deutschland” bei der AfD sowie die “freie/n” “Demokraten” bei der FDP erklären sollte).
Auch sind vereinzelt Wörter zu erkennen, welche nicht parteispezifisch, sondern der Formatierung der Wahlprogramme geschuldet sind ("Seite" bei der CDU/CSU etwa) - ein manueller Ausschluss solcher Wörter wäre eine Option, um diese aus der Analysi zu entfernen.
Weiterhin lassen sich Themenschwerpunkte erkennen:

- Einwanderung und Sprache bei der AFD
- Klimaneutralität bei den Grünen
- Bildung und Gesundheit bei der FDP
- Gesellschaft und Soziales bei den Linken
- Europa, Digitalisierung und Landwirtschaft bei der Union sowie
- Corona und Soziales (“Solidarität”, “Respekt”) bei der SPD.

## 3-Wort-Folgen (“3-grams”)


|                          AFD                           |                          CDU/CSU                          |                        FDP                        |
|:------------------------------------------------------:|:---------------------------------------------------------:|:-------------------------------------------------:|
|   ![AFD](/assets/img/wahlprogramme/3_grams/afd.png)    | ![CDU CSU](/assets/img/wahlprogramme/3_grams/cdu_csu.png) | ![FDP](/assets/img/wahlprogramme/3_grams/fdp.png) |
|                Bündnis 90 / Die Grünen                 |                         Die Linke                         |                        SPD                        |
| ![Grüne](/assets/img/wahlprogramme/3_grams/gruene.png) |   ![Linke](/assets/img/wahlprogramme/3_grams/linke.png)   | ![FDP](/assets/img/wahlprogramme/3_grams/spd.png) |

Betrachtet man Wortfolgen, so machen sich Themenschwerpunkte noch deutlicher bemerkbar, einige spannende Kontraste sind dabei:

- Ein Blick auf die Einwanderungspolitik: Während bei der AfD “Einwanderung, Integration, Asyl” sowie “Kultur, Sprache, Identität” im Mittelpunkt dieses Themas stehen, sieht man bei den Grünen den Begriff “Länder globalen Südens”.
- Der Klimawandel wir von mehreren Parteien behandelt, allerdings mit unterschiedlichem Blickwinkel: Die Union beschreibt den “European Green Deal”, die Linke einen “sozial ökologischen Umbau”, die FDP fokussiert sich auf den “Ausbau erneuerbarer Energien”, bei den Grünen ist von einer “sozial ökologischen Transformation” die Rede und die SPD will einen “ökologischen Umbau [der] Wirtsschaft” um die Erderwärmung auf “[1.5] grad celsius zu begrenzen”. Im Programm der AfD ist das Thema nicht auffällig erkennbar.
- Keine großen Unterschiede gibt es in der Sprache zur Geschlechtergerechtigkeit: Sowohl SPD als auch AfD sprechen von “Gleichstellung Männern Frauen” bzw “Gleichberechtigung Mann Frau” — diese beiden Parteien scheinen sich stärker auf das Thema zu fokussieren als andere. Einzig bei den Grünen ist bei Betrachtung der einzelnen Wörter noch der LSBTIQ auffällig.

Was wollen die Parteien? Es gibt einige Visionen für die Zukunft der Gesellschaft. Basierend auf den Rechercheergebnissen ließe sich folgendes Vermuten:

- SPD: “Zusammenhalt unserer Gesellschaft”
- AfD: Diverse Ziele bezüglich Einwanderung und Kriminalität
- BÜNDNIS 90/DIE GRÜNEN: “Sozial ökologische Transformation”
- FDP: “Ausbau erneuerbarer Energien” als Antwort auf die “Herausforderungen unserer Zeit”
- DIE LINKE: “Soziale Sicherheit”, “Gute Arbeit” und einen “Politikwechsel”
- CDU/CSU: “Freiheit und Sicherheit”

Diese Ergebnisse sollten nicht als tatsächliche Themenschwerpunkte der Parteien verstanden werden. Stattdessen zeigt sich daran nur, wo und wie die Kommunikation der eigenen Ziele von den anderen abweicht.

Die inhaltliche Auseinandersetzung mit den Parteiprogrammen ist sicherlich durch eine solche Betrachtung nicht umfänglich möglich — dennoch hoffe ich, an dieser Stelle dazu beigetragen zu haben und Klarheit in die Unterschiede zwischen den Parteien, die es fraglos gibt, aufgezeichnet zu haben. Welche davon in der kommenden Regierung sitzen werden, liegt in der Hand der Wähler*innen.

## Methoden und Anmerkungen

Der Code ist frei zugänglich unter: https://github.com/JonathanKuelz/election_programmes

Die Wortwolken enthalten jeweils 100 Wörter und/oder n-grams. Der minimale z-score des Fighting Word Algorithmus unter allen abgebildeten Wörtern beträgt:

- Einzelne Wörter, komplett: 2,61
- Einzelne Wörter, ohne stop words: 2,52
- Für die 3.grams: 1,15

Bei der Erstellung der Wörterwolken ist keinerlei inhaltliche Analyse der Parteien eingeflossen — es handelt sich hierbei lediglich um eine Betrachtung der Wort — und n-gram Häufigkeiten. Etwaige Themenschwerpunkte die sich herauslesen lassen müssen nicht bedeuten, dass eine Partei dieses Thema alleinig behandelt — es geschieht lediglich in abweichendem Vokabular von anderen Parteien. (Würde etwa eine Partei stets von “Klimakatastrophe” sprechen während alle Anderen den Begriff “Klimawandel” nutzen, so würde ausschließlich das Wort Klimakatastrophe in der Grafik erscheinen.

Die angestellte Analyse kann interessante Einblicke in die Parteiprogramme geben, ist aber selbstverständlich nur “ein Teil der Wahrheit”. Bitte informiert euch ausführlich vor der Wahl und seid euch der Grenzen einer solchen Analyse bewusst. Insbesondere wurde hier nur untersucht, was einzelne Parteien in einem einzelnen Dokument vorgeben, umzusetzen. Die politische Realität ist in der Regel weit komplexer und kann mitnichten durch einen solchen Beitrag abgedeckt werden.

[^vorarbeit]: Nach einiger Vorarbeit: Zahlen, Satzzeichen und sonstige Sonderzeichen wurden durch Leerzeichen ersetzt. Groß- und Kleinschreibung wurde ignoriert. Wenn es eine Lang- und Kurzfassung gibt, so habe ich die Langfassung genommen. Als Basis dient die jeweils zur Verfügunge stehende PDF-Datei mit allen darin enthaltenen Textstellen, also auch etwaigen Inhaltsverzeichnissen, Anhängen etc. Die Datei wurde mithilfe des Online-Converters zu https://pdftotext.com/ in maschinenleserlichen Text umgewandelt.
[^innen]: Durch das “preprocessing”, also das vorherige bearbeiten des Textes, wird aus einem Wort wie “Wähler*innen” in der Analyse “wähler” und “innen”.
