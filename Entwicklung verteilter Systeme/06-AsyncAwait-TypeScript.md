# Erklären Sie die grundsätzliche Funktionsweise von `async`/`await` in TypeScript.

Um `async`/`await`zu verstehen, muss man zuerst das Prinzip von `Promises` verstehen

### Promises
Ein Promise repräsentiert einen Wert, der jetzt, in der Zukunft oder vielleicht niemals verfügbar ist.
Ein Promise hat folgende Zustände:
* **pending** - der initiale Zustand eines Promises
* **resolved** - Die Operation innerhalb des Promise wurde erfolgreich durchgeführt
* **rejected** - Die Operation ist fehlgeschlagen

```typescript
function getRandomWithPromise() { 
  return new Promise((resolve, reject) => { 
    setTimeout(() => { 
      if (error) { 
        reject("some error"); 
        return; 
      } 
      resolve(Math.floor(Math.random() * 100)); 
    }, 200); 
  });
};

```
`getRandomWithPromise()` definiert ein Promise, welches einen zufälligen Wert irgendwann zurück liefert. 
`setTimeout()` simuliert hier zum Beispiel einen asynchronen HTTP Request.

Hier ist ein Beispiel, wie obige Funktion mit einem `Promise` aufgerufen wird:
```typescript
getRandomWithPromise()
  .then(result => {
    console.log(`Your random number is ${result}!`); 
    })
  .catch(error => { 
    console.log(`Ups! Something went wrong! Details: ${error}`); 
  });

```

### `async`/`await`
`async`/`await` erleichtert den Umgang mit Promises erheblich
* `async` definiert eine Funktion als asynchron
* `await` wird verwendet um auf die Erfüllung des Promise zu warten. await kann nur innerhalb einer async Funktion verwendet werden

Hier ist ein Beispiel, wie obige Funktion mit `async`/`await` aufgerufen wird:
```typescript
async function getRandomWithAsync() { 
  try { 
    return await getRandomWithPromise(); 
  } catch (error) { 
    return error; 
  }
};
```

Das erste, was auffällt, ist das `async` Keyword bei der Funktionsdeklaration. 
Dieses deklariert die Funktion `getRandomWithAsync()` als asynchron.

Der `await` Operator pausiert `getRandomWithPromise()` bis das Promise erfüllt wurde.
