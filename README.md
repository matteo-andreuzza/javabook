# javabook
 basi di Java 
# le basi di Java

## Premesse iniziali:
Prima di addentrarci nel linguaggio Java è necessario fare delle premesse:
- Java è KeySensitive, cioè fa distinzione fa Maiuscole e minuscole
- Ogni istruzione deve terminare con un punto e virgola;
- Per i primi punti non ci preoccuperemo del significato di 
 ```java
  public class Main {
	  public static void main(String[] args) { 
		  //codice
	  }
  }
 ```
basterà solo inserire il codice all'interno.
- Questa guida NON è sostituibile per NESSUN MOTIVO ad uno studio dettagliato accompagnato da una buona dose di esercizio
- 
## Variabili e costanti
Per contenere dei valori utilizziamo variabili e costanti:
- variabili per contenere un valore che **può variare**
- costanti per contenere un valore che **NON può variare**

Per essere considerata esistente, una variabile o una costante dev'essere **DICHIARATA**:
**Dichiarazione di una variabile:**

```java
int myNum = 5;               // intero (whole number)
float myFloatNum = 5.99f;    // numero a virgola variabile (floating point)
char myLetter = 'D';         // carattere
boolean myBool = true;       // booleano 
String myText = "Hello";     // Stringa
```

Scrivo, in ordine : datatype, nome della variabile, contenuto.
- **Datatype:** tipo della variabile, varia in base a ciò che contiene (int, String, ecc)
- **Nome:** scelgo un nome a piacere per la variabile
- **Contenuto:** Il contenuto della variabile deve rispettare le condizioni del datatype, ad esempio numeri interi per variabili `int`, numeri con virgola per variabili `float`, valori `true` o `false` per le variabili `boolean`, valori di singole lettere per variabili `char`.
> **Nota bene:**
>la variabile `bool` accetta SOLO valori `true` e `false`, i quali vanno inserirti rigorosamente in minuscolo. 


ATTENZIONE:
Dopo aver **Dichiarato** una variabile, quando la si va ad utilizzare, non si deve inserire il datatype!
```java
int ciao = 0;
int bella = 2
bella  = ciao;
```
 
## Funzioni di base di Input/Output:
Per comunicare con l'utente, il programma utilizza la finestra della console dove viene eseguito il programma. Per interagire con l'utente esistono due funzioni, per scrivere sulla finestra e per leggere un dato inserito dall'utente.

**Scrivere sulla console (Stampa a schermo)**
Utilizziamo il metodo `println()` della classe `System` per stampare un messaggio a schermo:
```java
  System.out.println("Hello World");
```
La **concatenazione** si effettua tramite il carattere + e serve a unire più stringhe. 
```java
  System.out.println("Hello" + "World");
```

**Leggere dati inseriti dall'utente:**
Utilizziamo il metodo `Scanner` per leggere ciò che digita l'utente. Il contenuto verrà memorizzato in una variabile.
Per prima cosa importiamo all'inizio del programma Scanner

```cpp
import java.util.Scanner;
```

Quindi all'interno del programma:
```cpp
System.out.println("inserire valore");
Scanner in = new Scanner(System.in);  // new perchè in diventa un oggetto dalla classe scanner
int n;
n = in.nextInt();
```

## Operazioni matematiche:
Possiamo compiere semplici operazioni matematiche sfruttando gli operatori presenti in java.
```java
float operazione = (34.5+1552) - ((568 * 645) / 4);
```

# Costrutti in Java (1)

## Operatori di selezione
### Selezione semplice
Possiamo effettuare delle operazioni di **selezione** di dati o istruzioni. Parangonandola al linguaggio comune, la selezione è l'equivalente di espressioni del tipo:
>_Se accade questo_ [condizione]
   _allora_ [e cosa succede]
   _altrimenti_ [e cosa succede altrimenti]
   
**esempio 1:**
_Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male._
**esempio 2:**
_Se ti metti questo vestito, allora sei bellissima, altrimenti sei bella comunque, anche senza, rimarrai la donna più bella di questo mondo._

Paragoniamo ora il primo esempio ad un codice di programmazione:

<div style="width: 100%;">
	<!-- THE LEFT COLUMN -->
		<div style="width: 48%; float: left; margin-right: 4%;">
			Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male.
		</div>
	<!-- END THE LEFT COLUMN -->
	
	<!-- THE RIGHT COLUMN -->
		<div style="width: 48%; float: left;">
			if(bevi_acido_cloridiro){ <br>
				starai male
			}<br>
			else{<br>
				non starai male
			}
		</div>
	<!-- END THE RIGHT COLUMN -->
</div>
Vediamo quindi come costruire un costrutto di selezione:

```cpp
if(condizione){
	// blocco di codice da eseguire se la condizione è vera
}
else{
	// blocco di codice da eseguire se la condizione risulta falsa
}
```
La prima parte contiene la parola chiave ```if``` che ordina al computer di **verificare** le condizioni presenti all'interno delle parentesi ed eseguire blocco di codice contenuto nelle parentesi graffe in caso le condizioni siano vere.
La seconda parte contiene la parola chiave ```else``` che ordina al computer di eseguire il blocco di codice contenuto nelle parentesi graffe se la condizione risulta falsa.

Per comprendere meglio, analizziamo il funzionamento del costrutto:
1. Il computer verifica le condizioni all'interno delle parentesi tonde. Una condizione vera è ad esempio 1 == 1, una falsa è ad esempio 1== 2.
> ATTENZIONE!
> Per fare un'operazione di confronto, occorre inserire due simboli di uguale ( == ), in quanto un solo = corrisponde ad un'operazione di ASSEGNAZIONE, ad esempio float a = 2.

2. Se la condizione è VERA, viene eseguito il blocco di codice contenuto nelle parentesi graffe, se è falsa invece, si passa al passo 3.
3. Se la condizione è FALSA, viene eseguito il blocco di codice contenuto nelle parentesi graffe dell'else. 

### Selezione annidata
La selezione annidata è un'estensione della selezione semplice, che consiste nell'inserimento di uno o più if all'interno di un'altro if.
Nel linguaggio comune un'operazione di selezione annidata potrebbe corrispondere ad un'espressione del tipo:
_Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola._
Applichiamo una subordinazione grafica alla frase per comprenderla meglio:

_Se avrò dei figli_
		  _se questi avranno figli_
		 	_sarò nonna
		 se non avranno figli_
		 	rimarrò madre
Se non avrò figli
	rimarrò sola._

Paragoniamo ancora una volta con un linguaggio di programmazione:

<div style="width: 100%;">
	<!-- THE LEFT COLUMN -->
		<div style="width: 48%; float: left; margin-right: 4%;">
			Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola.
		</div>
	<!-- END THE LEFT COLUMN -->
	
	<!-- THE RIGHT COLUMN -->
		<div style="width: 48%; float: left;">
			if(avrò dei figli){ <br>
				if(avranno dei figli){ <br>
					cout << "sarò nonna" << endl; <br>
				}<br>
				else{<br>
					cout << "rimarrò madre" << endl;<br>
				}<br>
			}<br>
			else{<br>
				cout << "rimarrò sola" << endl;<br>
			}<br>
			<!-- END THE RIGHT COLUMN -->
</div>
</div>
Vediamo quindi come costruire un costrutto di selezione annidata:

``` cpp
if(condizione){
	if(condizione2){
		// blocco di codice da eseguire se la condizione2 è vera
	}
	else{
		// blocco di codice da eseguire se la condizione2 risulta falsa
	}
	// blocco di codice da eseguire se la condizione è vera
}
else{
	// blocco di codice da eseguire se la condizione risulta falsa
}
```
Un secondo if si può inserire anche nell'else:

``` cpp
if(condizione){
	// blocco di codice da eseguire se la condizione è vera
}
else{
	if(condizione2){
		// blocco di codice da eseguire se la condizione2 è vera
	}
	else{
		// blocco di codice da eseguire se la condizione2 risulta falsa
	}
	// blocco di codice da eseguire se la condizione risulta falsa
}
```

## Gli operatori logici
Come in logica e matematica, anche nell'informatica esistono degli operatori logici. 
- Or (o questo o quello)
- And (e)
- Not (non)
- Uguale 
I loro corrispettivi in linguaggio di programmazione:
- ```||```
- ```&&```
- ```!=```
- ```==```
> **NOTA BENE ==IMPORTANTE==**
> Il doppio uguale (= =) significa UGUALIANZA 
> Un uguale singolo (=) significa ASSEGNAZIONE DI UN VALORE

Facciamo degli esempi di comparazione tra proposizioni logiche e in linguaggio di programmazione:
_Se queste mele pesano meno di 7 o più 10 le compro._

```java
float pesoMele;
if(pesoMele < 7 || pesoMele > 10){
	System.out.println("Compro le mele");
}
```

## Lo switch case

Nel linguaggio di programmazione Java, lo statement `switch case` è una costruzione che consente di selezionare una delle varie alternative basandosi sul valore di una singola espressione, senza utilizzare molteplici `if`. È particolarmente utile quando si devono prendere decisioni basate su un numero finito di possibili valori o casi.

La sintassi generale dello statement `switch case` è la seguente:

```java
switch (espressione) {
    case valore1:
        // istruzioni da eseguire se l'espressione è uguale a valore1
        break;
    case valore2:
        // istruzioni da eseguire se l'espressione è uguale a valore2
        break;
    // altri casi possibili...
    default:
        // istruzioni da eseguire se nessun caso corrisponde all'espressione
        break;
}
```

Vediamo ora come funziona lo statement `switch case` nel dettaglio:

1. L’espressione posta tra le parentesi tonde dopo la parola chiave `switch` viene valutata.
2. L’espressione viene confrontata con i valori specificati dopo ogni parola chiave `case`.
3. Se il valore dell’espressione corrisponde a uno dei valori specificati, vengono eseguite le istruzioni all’interno del blocco di codice corrispondente a quel caso.
4. Dopo l’esecuzione delle istruzioni relative al caso corrispondente, viene utilizzata la parola chiave `break` per uscire dallo statement `switch case` e proseguire con il codice successivo.
5. Se non viene trovato nessun caso corrispondente al valore dell’espressione, viene eseguito il blocco di codice associato alla parola chiave `default` (che è facoltativo). Anche in questo caso, l’utilizzo di `break` è consigliato per evitare l’esecuzione dei blocchi di codice dei casi successivi.
6. Alla fine dello statement `switch case`, il programma continua l’esecuzione dal punto successivo al blocco `switch`.

Ecco un esempio di utilizzo dello statement `switch case`:

```java
public class Main {
    public static void main(String[] args) {
        int numero = 2;

        switch (numero) {
            case 1:
                System.out.println("Il numero è 1");
                break;
            case 2:
                System.out.println("Il numero è 2");
                break;
            case 3:
                System.out.println("Il numero è 3");
                break;
            default:
                System.out.println("Il numero non è né 1, né 2, né 3");
                break;
        }
    }
}
```

In questo esempio, l’espressione `numero` viene confrontata con i vari casi. Poiché il valore di `numero` è 2, verrà eseguito il blocco di codice associato al caso `2`. Pertanto, l’output sarà:

```
Il numero è 2
```

È importante notare che il tipo di dato dell’espressione utilizzata nello statement `switch case` può essere qualsiasi tipo intero o carattere, come `int`, `char` o `enum`. Inoltre, i casi possono essere specificati in qualsiasi ordine e possono anche essere valori costanti o variabili. 
È inoltre possibile includere più istruzioni all’interno di ciascun caso. 