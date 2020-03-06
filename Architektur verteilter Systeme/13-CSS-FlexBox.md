# Was ist das CSS Flexible Box Layout (aka flexbox)? Wofür wird es bei der Erstellung mobiler Webapplikationen verwendet? Skizzieren Sie das Grundprinzip anhand eines einfachen Beispiels (mit oder ohne Angular).

Das CSS Flexible Box Layout ist ein CSS Modul, das ein CSS Box Model definiert, welches für das designen von User Interfaces optimiert ist.
Die Kindelemente eines flexbox Layouts können in jeder Richtung angeordnet sein und ihre Größe "flexen". Damit können sie
ungebrauchten Platz ausfüllen oder kleiner werden. Die vertikale und horizontale Ausrichtung der Kinder kann leicht manipuliert werden.

Um Flexbox zu aktivieren, muss der Parentcontainer den style `display: flex;` beinhalten. 

Flexbox ist sehr nützlich bei der Erstellung mobiler Webapplikationen, die auf einer Vielzahl von Geräten vernünftig aussehen soll.
Beispielsweise kann die vertikale oder horizontale Ausrichtung je nachdem, wie viel Platz verfügbar ist, verändert werden.
Darüber hinaus ist es möglich, Elemente gar nicht erst anzuzeigen, falls der Platz am Bildschirm nicht ausreichen sollte.

![FlexBox Skizze](https://github.com/michaelhitzker/5BHIF-MC-Maturafragen/blob/master/Architektur%20verteilter%20Systeme/img/FlexboxLayout.png?raw=true)

Auf obiger Skizze ist zu erkennen, wie sich das Layout ändert, wenn man vom Desktop auf das Smartphone wechselt. Um dieses Verhalten zu definieren, muss man mit CSS Media Queries die Flex-Eigenschaften der Elemente ändern, sobald der Bildschirm eine gewisse Größe unter- bzw. überschreitet.  

Um Elemente, welche auf dem Desktop nebeneinander, auf dem Smartphone aber untereinander angezeigt werden sollen, eignet sich folgender Code:

```html
<div class="parent">
  <div class="child">I'm child 1</div>
  <div class="child">I'm child 2</div>
  <div class="child">I'm child 3</div>
</div>
```
```css
.parent{
  display: flex;
  flex-direction: row;
}

.child{
  margin: 10px;
}

@media only screen and (max-width: 959px) {
  .parent{
  flex-direction: column;
  }
}
```
### [Live demo](https://jsfiddle.net/2kspnue5/)

Angular erleichtert den Umgang mit dem FlexBox Layout durch das Package [@angular/flex-layout](https://github.com/angular/flex-layout) enorm!  
Um obiges Beispiel mit `@angular/flex-layout` zu lösen, reicht folgender Code (vorausgesetzt, das Package ist installiert):
```html
<div class="parent" fxLayout.lt-md="column" fxLayout="row">
  <div class="child">I'm child 1</div>
  <div class="child">I'm child 2</div>
  <div class="child">I'm child 3</div>
</div>
```
Wie man sieht, ist kein CSS nötig!
### [Live demo](https://stackblitz.com/edit/angular-a5eva7)
