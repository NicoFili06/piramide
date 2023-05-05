# piramide
-Il tuo compito oggi è scrivere un programma che calcoli l'altezza massima di una piramide (in piani) dato un certo numero di cubi di pietra.

Ipotizzando che:

- i piani della piramide siano quadrati
- la piramide da costruire sia compatta, cioè non ci siano cavità al suo interno. 
- ogni piano è quadrato, con una lunghezza laterale inferiore di due rispetto a quella sottostante.
- il primo piano è sempre di un mattone
- 
-codice intero
```c#
using System;
namespace Piramide{
public class Piramide{
    public static int Piani(int mattoni) {
        int piani = 0;
        while (mattoni >= (2 * piani + 1) * (2 * piani + 1)) {
            piani++;
            mattoni -= (2 * piani - 1) * (2 * piani - 1);
        }
        
        return piani;

    }


    public static int Rimanenti(int mattoni) {
        int piani = Piani(mattoni);
        int mattoniUtilizzati = 0;
        for (int i = 1; i <= piani; i++) {
            mattoniUtilizzati += (2 * i - 1) * (2 * i - 1);
        }
        return mattoni - mattoniUtilizzati;
    }


    }


}
```
-Viene usato un ciclo while per calcolare il numero massimo di piani. Ad ogni iterazione, il numero di piani viene incrementato e il numero di mattoni utilizzati per costruire i piani precedenti viene sottratto dal numero totale di mattoni. La condizione del ciclo while è verificata finché il numero di mattoni rimasti è sufficiente per costruire un altro piano.
```c#
public static int Piani(int mattoni) {
        int piani = 0;
        while (mattoni >= (2 * piani + 1) * (2 * piani + 1)) {
            piani++;
            mattoni -= (2 * piani - 1) * (2 * piani - 1);
        }
        
        return piani;
```
-Il metodo Rimanenti utilizza il valore restituito dal metodo Piani per calcolare il numero di mattoni utilizzati per costruire l'intera piramide.  Quindi sottratto il numero di mattoni utilizzati dal numero totale di mattoni per ottenere il numero di mattoni rimanenti.
```c#
 public static int Rimanenti(int mattoni) {
        int piani = Piani(mattoni);
        int mattoniUtilizzati = 0;
        for (int i = 1; i <= piani; i++) {
            mattoniUtilizzati += (2 * i - 1) * (2 * i - 1);
        }
        return mattoni - mattoniUtilizzati;
    }


    }


}
```

