# Kleine Mathe-Challenge

Folgende Aufgabe habe ich an ChatGPT 4o and DeepSeek V3 gestellt. Beide sind krachend gescheitert. Das war aber zu erwarten, weil es sich um allgemein trainierte LLMs handelt, die nicht auf "reasoning" ausgelegt sind. Möglicherweise sind ChatGPT o3 und DeepSeek R1 besser - auf die habe ich aber keinen Zugriff. Anfrage läuft. 

Here's a simple math problem. Given are six three-digit numbers 187, 623, 435, 822, 774, and 378. With these and only these numbers used once and arbitrary mathematical operators, create the number 720. 

Diese Aufgabe habe ich in die Jahrgangs-Physik-Gruppe und in Gruppe mit Master-EI-Studierenden gestellt, weil ich mal wissen wollte, wer schneller auf die kürzeste und einfachste Lösung kommt. OK, statistisch fragwürdig weil kleine Stichprobe und so, aber als Indikation vielleicht ganz interessant. 


ChatGPT 4o kam mir mit [dieser Lösung](https://chatgpt.com/share/6799fd15-a76c-8001-897e-536bc0b49ab5). Die 560 kommt ganz nach dem Spruch meines ehemaligen Mathe-Profs Dr. Pilzweger "eine starke Behauptung ersetzt einen schwachen Beweis".   
  
DeepSeek V3 versuchte sich [so](DeepSeek.md). Man sieht, wie er nachdenkt. Aber er kommt auch nicht drauf, mal abgesehen davon, dass er sich die Zahlen 151 und 248 ausgedacht oder zumindest nicht begründet hat. Also so ähnlich wie ChatGPT. 

Aus der Runde meiner Mitstudierenden kamen folgende interessante Vorschläge, auf die ich nicht gekommen wäre. 

ChatGPT o1 versuchte es mit einem brute force Ansatz, der rechnerisch stimmt und sogar noch etwas einfacher geht. 

![ChatGPT o1](IMG-20250129-WA0000.jpg)

nämlich so:   
  
    >>> factorial(gcd(822,378))**gcd(774-623,435-187)
    720

Folgende Lösung finde ich (soweit es mir überhaupt zusteht, das so zu sagen) sehr clever:   
  
![floor und ceil](IMG-20250129-WA0001.jpg)

Oder diese:   
  
    >>> factorial(factorial(int(((sqrt((435-378)-(822-774))))))) + floor(187/623)
    720

Der zweite Summand ist natürlich eine null. OK.   
  
Alternativ sowas:   
  
    >>> factorial(factorial(ceil(187/387)+ceil(435/623)+ceil(774/822)))
    720

Stimmt rechnerisch und finde ich bewundernswert, aber da wollte ich nicht hin, vor allem nicht mit den LLMs. 

Habe dann doch noch selber gesehen, dass man ja auch DeepSeek R1 im Testmodus nutzen kann, und es ist lustig zuzusehen, wie er das [entwickelt](DeepSeek-R1.md). Ob das Geplappere wirklich weniger Energie braucht als die bisherigen LLMs?

## Lösung

OK, lösen wir das mal auf. Inspiriert dazu hat mich die Denksportaufgabe [Sechs Nullen wachsen über sich hinaus](https://www.spiegel.de/karriere/raetsel-der-woche-sechs-nullen-wachsen-ueber-sich-hinaus-a-68661c8e-1f19-4e82-ab9e-72d56359b6de). 
Die Musterlösung ist zwar richtig, fand ich aber wegen des Kunstgriffes 0! = 1 unbefriedigend. OK, mann muss drauf kommen, dass 720 = 6! und dass 0! = 1 ist. Und dann kam mir der Gedanke: 

    (|{0, 0, 0, 0, 0, 0}|)! = 6! = 720

Das funktioniert natürlich mit sechs beliebigen Zahlen mit jeweils beliebig vielen Stellen, oder allgemein mit sechs beliebigen Objekten in einer Menge. Die in der Aufgabe genannten Zahlen habe ich pseudozufällig ausgewählt. Reine Ablenkung. Und richtig, die LLMs (um die ging es mir) versuchten sich wie gezeigt an wilden Rechnereien mit den Grundrechenarten. Zugegeben (das habe ich auch als Feedback bekommen) war die Aufgabe sehr "sloppy" gestellt. Wie sich herausstellt, kann man mit brute force alle möglichen rechnerischen Kombinationen finden, die in Richtung Ergebnis gehen. Mir ging es aber darum heraus zu finden, ob die LLMs "out of the box" denken und auf die genannte kürzeste (eleganteste) Lösung kommen. Leider: Fehlanzeige. Vielleicht probiere ich es mit den Nullen nochmal. 
  
Die Aktion hier erhebt natürlich überhaupt keinen Anspruch auf statistische Relevanz - dazu war schon die Stichprobe zu klein, und freiwillige Teilnahme ist ja auch immer so eine Sache. Es ist also nur eine Momentaufnahme. 
  
Ich hoffe, dass mir die Aufgabenstellung nicht als Hochnäsigkeit ausgelegt wird, aber ich fand die Frage spannend, welche Lösungsansätze kommen würden, und habe selber eine Menge gelernt. Vor allem beim Programmieren in Python und C nutze ich ChatGPT viel und reichlich (für einen Moment den CO2-Footprint ignorierend), und wenn man mal gelernt hat, brauchbare Informationen von BS zu unterscheiden, ist das in diesem Bereich ein nützliches Werkzeug.
  
Der Weg zur AGI (artificial general intelligence) scheint mir aber noch weit. 

Den Teilnehmenden sei vielen Dank fürs Mitmachen! :-) 



















