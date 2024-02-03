# javabook
Le basi della programmazione in generale ed in linguaggio [Java](https://www.java.com/it/).

> **ATTENZIONE**: Il _Javabook_ non è ancora completo per tutto il linguaggi ma è utilizzabile. Se cerchi concetti di programmazione non strettamente legati a Java, puoi usufruire del [_javabook_](https://matteo-andreuzza.github.io/java-book/).

- [javabook](#javabook)
- [le basi di Java](#le-basi-di-java)
   * [Premesse iniziali:](#premesse-iniziali)
   * [Variabili e costanti](#variabili-e-costanti)
   * [Funzioni di base di Input/Output:](#funzioni-di-base-di-inputoutput)
   * [Operazioni matematiche:](#operazioni-matematiche)
- [Costrutti in Java (1)](#costrutti-in-java-1)
   * [Operatori di selezione](#operatori-di-selezione)
      + [Selezione semplice](#selezione-semplice)
      + [Selezione annidata](#selezione-annidata)
   * [Gli operatori logici](#gli-operatori-logici)
   * [Lo switch case](#lo-switch-case)
- [Cicli in Java](#cicli-in-java)
- [Ciclo While](#ciclo-while)
   * [Ciclo Do - While](#ciclo-do-while)
   * [Ciclo For](#ciclo-for)
   * [Istruzioni utili nei cicli](#istruzioni-utili-nei-cicli)
      + [istruzione break](#istruzione-break)
      + [Istruzione continue](#istruzione-continue)
- [Arrays in Java](#arrays-in-java)
   * [Arrays Monodimensionali](#arrays-monodimensionali)
      + [Arrays nel codice:](#arrays-nel-codice)
      + [Usare gli arrays:](#usare-gli-arrays)

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
- è utile anche se non indispensabile avere un editor di codice/IDE per programmare. Consigliamo:
	- [onlinegdb](https://www.onlinegdb.com/), online, senza installare nulla, basico. Consigliata la **registrazione** con il pulsante singup/login.  <=_**fortemente consigliato**_
	- [IntelliJ IDEA](https://www.jetbrains.com/idea/), più avanzato, pesante ma pronto all'uso.
	- [VisualStudio Code](https://visualstudio.microsoft.com/it/#vscode-section), fortemente sconsigliato per gli utenti alle prime armi, è necessario saperlo configurare ed avere dunque una buona conoscenza del software. 
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
int cocacola = 1;
int acqua = 0;

//imposto le variabili su valori differenti:
cocacola = 2;
acqua = 3;
```

Spiegherò ora un concetto che non tutte le persone che iniziano a programmare capiscono:
Bobbiamo immaginarci le variabili come dei veri e propri contenitori, quindi per effettuare operazioni tra di essere dobbiamo avere alcuni accorgimenti.
Facciamo dunque un esempio con due bicchieri, uno contenente acqua e l'altro CocaCola:
- Voglio **scambiare il contenuto dei due bicchieri**, quindi:
All'inizio avrò due variabili, ovvero i due bicchieri pieni:
```java
String bicchiere1 = "Cocacola";
String bibcchiere2 = "Acqua";
```
Per scambiare i valori, quindi i contenuti dei due bicchieri, **dovrò utilizzare un terzo bicchiere**, ovvero una nuova variabile
```java
String temporaneo = "" //dichiaro una variabile temporanea dello stesso tipo
```
Quindi svuoterò un bicchiere in quello temporaneo, lo riempirò con il contenuto dell'altro bicchiere e quest'ultimo lo riempirò a sua volta con il contenuto di quello temporaneo.
```java
temporaneo = bicchiere1; //svoto 1 in temporaneo: 1 vuoto, 2 pieno
bicchiere1 = bicchiere2; //svuoto 2 in 1: 1 pieno, 2 vuoto
bicchiere2 = temporaneo; //svuoto temporaneo in 2: 1 pieno, 2 pieno
```

## Funzioni di base di Input/Output:
Per comunicare con l'utente, il programma utilizza la console dove viene eseguito il programma. Per interagire con l'utente esistono due funzioni, per scrivere sulla finestra e per leggere un dato inserito dall'utente.

**Scrivere sulla console (Stampa a schermo)**
Utilizziamo il metodo `println()` della classe `System` per stampare un messaggio a schermo:
```java
  System.out.println("Hello World");
```
La **concatenazione** si effettua tramite il carattere + e serve ad unire più stringhe. 
```java
  System.out.println("Hello" + "World");
```

**Leggere dati inseriti dall'utente:**
Utilizziamo il metodo `Scanner` per leggere ciò che digita l'utente. Il contenuto verrà memorizzato in una variabile.
Per prima cosa importiamo all'inizio del programma Scanner

```java
import java.util.Scanner;
```

Quindi all'interno del programma:
```java
System.out.println("inserire valore numerico intero");
Scanner input = new Scanner(System.in);// creo input, che sarà il mio scanner
int n; //creo una variabile qualsiasi di tipo int
n = input.nextInt(); //memorizzo nella variabile quello che viene scritto da tastiera
```
Il codice qui sopra funziona però solo quando devo leggere da tastiera un **numero intero** `int`, in caso volessi leggere una stringa dovrò:
- Cambiare il tipo della variabile dove memorizzo il dato in questo caso da `int` a `String`.
- Cambiare il _metodo_ che utilizzo, infatti al posto di `nextInt()`,  il quale, come dice il nome, legge un numero intero (int, appunto), dovrò utilizzare `nextLine()
```java
System.out.println("inserire testo");
Scanner input = new Scanner(System.in);// creo input, che sarà il mio scanner
String n; //creo una variabile qualsiasi di tipo Stringa
n = input.nextLine(); //memorizzo nella variabile quello che viene scritto da tastiera
```
In particolare nella tabella qui sotto ci sono gli altri metodi per leggere altri tipi di dati.

|Metodo |Descrizione |
|---|---|
|`nextBoolean()`|Reads a `boolean` value from the user|
|`nextByte()`|Reads a `byte` value from the user|
|`nextDouble()`|Reads a `double` value from the user|
|`nextFloat()`|Reads a `float` value from the user|
|`nextInt()`|Reads a `int` value from the user|
|`nextLine()`|Reads a `String` value from the user|
|`nextLong()`|Reads a `long` value from the user|
|`nextShort()`|Reads a `short` value from the user|
Di più [qui](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html).
## Operazioni matematiche:
Possiamo compiere semplici operazioni matematiche sfruttando gli operatori presenti in java.
```java
float operazione = (34.5+1552) - ((568 * 645) / 4);
```

## Pensare binario, pensare come il programma.
Quando programmiamo, è necessario capire come esegue le operazioni il computer. Per progettare i nostri programmi è utile pensare capire come vengono valutate determinate condizioni.

Facciamo un esempio di espressione:
$$
5 = 5
$$
Questa condizione **è vera o falsa?**
La risposta è semplice, **è vera**, in quanto 5 è sempre uguale a 5.
Mentre questa espressione:
$$
5 ≠ 5
$$
è falsa, dato che come abbiamo detto prima 5 = 5.

Ricordando un po' di matematica, possiamo definire vere delle espressioni anche al solo verificarsi di alcune condizioni, come:
$$
3x>6
$$
Questa infatti è vera **solo se**:
$$
x>2
$$
Ragioniamo un po':
Se:
$$
x>2
$$
Allora:
$$
3x>6
$$
è vera, altrimenti per:
$$
x≤2
$$
è falsa.

Mettendo insieme le cose possiamo dire che:
E' sempre vera la seguente condizione:
$$
3x>6 ⇔ x>2
$$
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



# Costrutti in Java (1)

## Operatori di selezione
### Selezione semplice
Possiamo effettuare delle operazioni di **selezione** di dati o istruzioni. Paragonandola al linguaggio comune, la selezione è l'equivalente di espressioni del tipo:
>_Se accade questo_ [condizione]
   _allora_ [e cosa succede]
   _altrimenti_ [e cosa succede altrimenti]
   
**esempio 1:**
_Se bevi acido cloridrico allora starai male, altrimenti non starai male._
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

```java
if(condizione){
	// blocco di codice da eseguire se la condizione è vera
}
else{
	// blocco di codice da eseguire se la condizione risulta falsa
}
```

La prima parte contiene la parola chiave ```if``` che ordina al computer di **verificare** la condizione all'interno delle parentesi ed eseguire blocco di codice contenuto nelle parentesi graffe in caso questa fosse vera.
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

``` java
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

``` java
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


## Lo switch case

Nel linguaggio di programmazione Java, lo statement `switch` è una costruzione che consente di selezionare una delle varie alternative basandosi sul valore di una singola espressione, senza utilizzare molteplici `if`. È particolarmente utile quando si devono prendere decisioni basate su un numero finito di possibili valori o casi.

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

# Cicli in Java
I cicli in programmazione sono dei costrutti che permettono di ripetere una serie di istruzioni più volte.

# Ciclo While
Il ciclo While si presenta come il ciclo più semplice. Il suo scopo è quello di ripere un blocco di codice se una determinata condizione è vera. Quando questa diventerà falsa, il blocco di istruzioni non verrà più eseguito, ed il programma uscirà dal ciclo. 
> Usiamo quindi il ciclo while quando NON sappiamo (o meglio, quando non viene specificato) il numero di volte che verranno eseguite le istruzioni.

>_fino a quando questo è vero_ [condizione]
   _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo while e la sua sintassi:

``` java
while(condizione){
	istruzione1;
	istruzione2;
	ecc;
}
```

Facciamo un esempio pratico:

``` java
int a = 0;

while(a < 10){
	System.out.println("Il ciclo è in funzione. Giro numero " + a);
	a++;
}
```

output:

``` shell
Il ciclo è in funzione. Giro numero 0
Il ciclo è in funzione. Giro numero 1
Il ciclo è in funzione. Giro numero 2
Il ciclo è in funzione. Giro numero 3
Il ciclo è in funzione. Giro numero 4
Il ciclo è in funzione. Giro numero 5
Il ciclo è in funzione. Giro numero 6
Il ciclo è in funzione. Giro numero 7
Il ciclo è in funzione. Giro numero 8
Il ciclo è in funzione. Giro numero 9
```

Notiamo che dopo aver completato il decimo ciclo, il programma è uscito dal ciclo, non eseguendo più le istruzioni contenute nelle parentesi graffe.
Per verificare questo avvenimento, inseriamo un println dopo il ciclo, per vedere quando il ciclo sarà terminato.
``` java
int a = 0;

while(a < 10){
	System.out.println("Il ciclo è in funzione. Giro numero " + a);
	a++;
}
System.out.println("Il programma è uscito dal ciclo");
```

output:

``` shell
Il ciclo è in funzione. Giro numero 0
Il ciclo è in funzione. Giro numero 1
Il ciclo è in funzione. Giro numero 2
Il ciclo è in funzione. Giro numero 3
Il ciclo è in funzione. Giro numero 4
Il ciclo è in funzione. Giro numero 5
Il ciclo è in funzione. Giro numero 6
Il ciclo è in funzione. Giro numero 7
Il ciclo è in funzione. Giro numero 8
Il ciclo è in funzione. Giro numero 9
Il programma è uscito dal ciclo
```

Visto? Appena il programma esce dal ciclo, esso esegue le istruzioni che compaiono successivamente.
 
 >**NOTA BENE | valore della variabile:**
 >	Come puoi vedere, il valore della variabile nell'ultimo giro è 9, non 10, eppure il ciclo ha compiuto 10 giri.
 >	Questo è una conseguenza del fatto che in informatica i numeri partono dallo 0, e non da 1.
 >	Questo ci tornerà molto utile più avanti.
 
  >**NOTA BENE | incremento di una variabile**
 >	Come puoi notare, l'ultima istruzione all'interno del ciclo è `a++` .
 >	 `a++` è l'equivalente di scrivere  `a = a+1`  

## Ciclo Do - While
Il ciclo do - While è un'evoluzione del ciclo While. L'unica cosa che cambia da quest'ultimo infatti, è che il blocco di istruzioni da eseguire, **viene eseguito una volta**, poi viene verificata la condizione e allora verrà eseguito di nuovo fino a quando la condizione non diventerà falsa.
``` java
do {  
 //blocco di codice 
 }  
while (condizione);
```
esempio:
> Chiedere in input all’utente un numero intero compreso nell’intervallo[1,7], memorizzalo nella variabile number, iterando questa richiesta fintanto che il numero inserito dall’utente non è corretto

``` java
Scanner input = new Scanner (System.in);
int number;
do{
	System.out.println("Caro utente, inserisci il numero [1,7]");
	number = input.nextInt();
}while (number < 1 || number > 7);
``` 
## Ciclo For
Il ciclo for è un ciclo più complesso del ciclo while, che permette di ripetere un blocco di istruzioni **un determinato numero di volte**. Come per il While, per eseguire il blocco di codice dovrà essere soddisfatta una condizione.
>_fino a quando questo è vero_ [condizione]
   _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo for e la sua sintassi:

``` java
for(<inizializzazione>; <condizione>; <espressione_iterativa>){
	istruzione1;
	istruzione2;
	ecc;
}
```

Come possiamo notare, tra le parentesi non è presente la sola condizione che dev'essere soddisfatta, ma anche un'**istruzione di inizializzazione e un'espressione iterativa**.
Queste sono utili per utilizzare il ciclo for con Vettori, matrici, e altro che non abbiamo ancora trattato.
Ci limiteremo quindi ad inserire nel parametro di inizializzazione, la dichiarazione di una variabile contatore, e nell'espressione iterativa, l'incremento della suddetta variabile. 
In sostanza:
- L'**inizializzazione** prevede la **dichiarazione di una variabile** che è utilizzabile nel solo ciclo for.
- La **condizione** è, come nel while, quella che determina la fine dell'iterazione del ciclo
- L'**espressione iterativa** è un'istruzione di qualsiasi genere, che viene eseguita **ad ogni iterazione del ciclo**. 

Facciamo un esempio pratico:

``` java
int acc = 0;
for (int i = 0; i < 10; i ++){
    System.out.println("Questo è il giro numero" + i);
    acc += i;
}
```

output:

``` shell
Questo è il giro numero0
Questo è il giro numero1
Questo è il giro numero2
Questo è il giro numero3
Questo è il giro numero4
Questo è il giro numero5
Questo è il giro numero6
Questo è il giro numero7
Questo è il giro numero8
Questo è il giro numero9

```

Il ciclo stampa a schermo 10 volte la scritta, scrivendo alla fine il numero del giro.
> Chiariamo che questo è un uso estremamente riduttivo del ciclo for, tanto che questo risultato si potrebbe ottenere anche con un ciclo while.
> Ci limitiamo però a questi esempi, dato che un uso intensivo del ciclo for verrà fatto più avanti.

**Esempio:**
Dato un numero, stampare a video 5 righe dove ogni riga ha un numero di  asterischi pari ai primi 5 multipli in successione 
	Esempio: Numero generato 3:
```shell
1-*** 
2-****** 
3-********* 
4-************ 
5-*************** 
```

```java
int number = 3;
	for(int i = 1; i <= 5; i++){//scorre le righe
			System.out.print(i + "-"); //stampa i numeri di riga
		for(int k = 0; k < (i * number); k++){//scorre il numero di * per riga
			System.out.print("*"); // gli stampa
		}
	   System.out.println(" "); // va a capo a fine di ogni riga
	}
```

> Ci limitiamo però a questi esempi, dato che un uso intensivo del ciclo for verrà fatto più avanti.

## Istruzioni utili nei cicli

### istruzione break
l'istruzione break serve a fermare un ciclo in un determinato momento. Questo può essere utile per terminare il ciclo quando una condizione è soddisfatta.
Esempio:
```java
for (int i = 1; i < 10; i++)
{
	if (i == 4) {
		break;
	}
	System.out.println(i);
}
```
output:
```shell
1
2
3
```
il ciclo si ferma quando ```i``` diventa 4

### Istruzione continue
L'istruzione ```continue``` salta un'iterazione del ciclo. Più specificatamente:

> L'istruzione `continue` ha come effetto l'interruzione dell'iterazione corrente. Il controllo di flusso rimane confinato all'interno del ciclo, ma viene reindirizzato all'iterazione successiva in conseguenza di una circostanza inattesa che invalida o rende superflua l'esecuzione di tale iterazione.

esempio:
```java
int i = 0;
while (i < 10) {
  if (i == 4) {
    i++;
    continue;
  }
  System.out.println(i);
  i++;
}
```

output
```shell
0
1
2
3  # <= manca il 4
5
6
7
8
9
```
Possiamo notare che quando ```i``` è uguale a 4, la corrente iterazione del ciclo viene interrotta.

# Arrays in Java

In Java, come in ogni linguaggio di programmazione che li supporta, gli arrays servono ad immagazzinare più elementi all'interno di una variabile. 
## Arrays Monodimensionali
Detti anche vettori, sono caratterizzati da:
- Il tipo di elementi che deve contenere
- La lunghezza dell'array
- Gli elementi che contiene
- Gli indici degli elementi
Questa rappresentazione ci aiuta a capire la struttura dell'array
![[Array1.jpg]]
Un array è costituito da delle "caselle". Queste devono essere tante quante la lunghezza dell'array (nell'immagine: Array lenght). Ad ogni "casella" è assegnato un numero che la rappresenta, questo numero è chiamato indice.
> **Nota bene**
> Gli indici delle "caselle" partono da 0. Questo significa che la prima casella avrà indice 0, la seconda 1 e così via. 

Le caselle possono essere riempite con degli elementi, a patto che questi elementi siano **tutti dello stesso tipo**, specificato nella creazione dell'array.

### Arrays nel codice:
Come per le variabili, anche gli arrays vanno inizializzati:
La struttura per inizializzare un vettore è la seguente:
```java
tipo[] nome = new tipo[lunghezza];
```

Per inizializzare un vettore di 3 elementi:
```java
int[] numbers1 = new int[3]; // il valore standard è 0
```
>Nota bene:
>in un array gli elementi sono separati da una virgola e contenuti dentro parentesi graffe.

Opzionale: 
Posso scriverlo anche così: (array literal)
```java
int[] numbers2 = { 1, 2, 3 };
```
 oppure: (array inizializzato)
 ```java
int[] numbers3 = new int[] { 1, 2, 3 };
```

### Usare gli arrays:

Possiamo utilizzare gli array in svariati modi. Per ricavare un valore in una determinata posizione in un array usiamo la sintassi:
```java
int[] numeri = {1, 2, 3, 4, 5};
System.out.println(numeri[1]);
```
output:
```shell
2
```

Vediamo per esempio come stampare tutti i valori di un array:
```java
int[] numeri = {1, 2, 3, 4, 5};
for(int i = 0; i < numeri.length; i++){
	System.out.println(numeri[i]);
}
```
Notare come il ciclo for risulta molto utile in questi casi, dato che ci permette di eseguire determinate operazioni su un array un determinato numero di volte. Sapendo la dimensione dell’array (che può essere ottenuta con `array.length`), possiamo utilizzare tutti gli elementi. La sintassi vista qui sopra è utile in diversi casi.

Un altro algoritmo utile può invertire tutti gli elementi di un array:

```java
// Inverti l'array
for (int i = 0; i < numeri.length / 2; i++)
{
	int temp = numeri[i];
	numeri[i] = numeri[numeri.length - i - 1];
	numeri[numeri.length - i - 1] = temp;
}
System.out.println("STAMPA ARRAY GIRATO");
// Stampa l'array
for (int i = 0; i < numeri.length; i++)
{
	System.out.print(numeri[i] + ", ");
}
```