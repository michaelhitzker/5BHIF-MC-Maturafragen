# Was ist das CSS Flexible Box Layout (aka flexbox)? Wofür wird es bei der Erstellung mobiler Webapplikationen verwendet? Skizzieren Sie das Grundprinzip anhand eines einfachen Beispiels (mit oder ohne Angular).

Das CSS Flexible Box Layout ist ein CSS Modul, das ein CSS Box Model definiert, welches für das designen von User Interfaces optimiert ist.
Die Kindelemente eines flexbox Layouts können in jeder Richtung angeordnet sein und ihre Größe "flexen". Damit können sie
ungebrauchten Platz ausfüllen oder kleiner werden. Die vertikale und horizontale Ausrichtung der Kinder kann leicht manipuliert werden.

Um Flexbox zu aktivieren, muss der Parentcontainer den style `display: flex;` beinhalten. 

Flexbox ist sehr nützlich bei der Erstellung mobiler Webapplikationen, die auf einer Vielzahl von Geräten vernünftig aussehen soll.
Beispielsweise kann die vertikale oder horizontale Ausrichtung je nachdem, wie viel Platz verfügbar ist, verändert werden.
Darüber hinaus ist es möglich, Elemente gar nicht erst anzuzeigen, falls der Platz am Bildschirm nicht ausreichen sollte.
