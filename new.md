# Le basi di Java

## Variabili e costanti

Per contenere dei valori utilizziamo variabili e costanti:

- variabili per contenere un valore che **può variare**
- costanti per contenere un valore che **NON può variare**

Per essere considerata esistente, una variabile o una costante dev’essere **DICHIARATA**: **Dichiarazione di una variabile:**

```java
int raggio = 20;
```

Scrivo, in ordine : datatype, nome della variabile, contenuto.

- **Datatype:** tipo della variabile, varia in base a ciò che contiene (char, int, float, boolean, ecc…)
- **Nome:** scelgo un nome a piacere per la variabile
- **Contenuto:** Il contenuto della variabile deve rispettare le condizioni del datatype, ad esempio numeri interi per variabili `int`, numeri con virgola per variabili `float`, valori `true` o `false` per le variabili `boolean`, valori di singole lettere per variabili `char`.

**Dichiarazione di una COSTANTE:**

```java
final float PIGRECO = 3.14f;
```

Scrivo, in ordine : final, datatype, nome della variabile, contenuto.

- **final:** parola chiave per definire una costante.
- **Datatype:** tipo della costante, varia in base a ciò che contiene (char, int, float, boolean, ecc…)
- **Nome:** scelgo un nome a piacere per la costante, buona norma metterlo in MAIUSCOLO.
- **Contenuto:** Il contenuto della costante deve rispettare le condizioni del datatype

ATTENZIONE: Dopo aver **Dichiarato** una variabile, quando la si va ad utilizzare, non si deve inserire il datatype!

```java
int ciao = 0;
int bella = 2;
bella  = ciao;
```

## Funzioni di base di System.out e Scanner:

Per comunicare con l’utente, il programma utilizza la finestra della console dove viene eseguito il programma. Per interagire con l’utente esistono due funzioni, per scrivere sulla finestra e per leggere un dato inserito dall’utente.

**Scrivere sulla console (Stampa a schermo)** Utilizziamo il metodo println di System.out per stampare un messaggio a schermo:

```java
System.out.println("Hello World");
```

La **concatenazione** si effettua tramite il carattere + e serve a unire più stringhe.

```java
System.out.println("Hello" + "World");
```

**Leggere dati inseriti dall’utente:** Utilizziamo la classe Scanner per leggere ciò che digita l’utente. Il contenuto verrà memorizzato in una variabile.

```java
Scanner scanner = new Scanner(System.in);
raggio = scanner.nextFloat();
```

La combinazione di System.out.println e Scanner dà vita ad una prima forma di interazione con l’utente.

```java
float raggio = 0;
System.out.println("Inserisci il valore del raggio del cerchio");
Scanner scanner = new Scanner(System.in);
raggio = scanner.nextFloat();
```

## Operazioni matematiche:

Possiamo compiere semplici operazioni matematiche sfruttando gli operatori presenti in Java.

```java
operazione = (34.5+1552) - ((568 * 645) / 4)
```

## Funzione principale

Per la natura di Java, il programma viene eseguito in una funzione main(), è necessario quindi che il codice principale sia in una costruzione come:

```java
public class Main {
    public static void main(String[] args) {
        // il tuo codice qui
    }
}
```

# Costrutti complessi in Java (1)

## Operatori di selezione

### Selezione semplice

Possiamo effettuare delle operazioni di **selezione** di dati o istruzioni. Parangonandola al linguaggio comune, la selezione è l’equivalente di espressioni del tipo:

> _Se accade questo_ [condizione] _allora_ [e cosa succede] _altrimenti_ [e cosa succede altrimenti]

**esempio 1:** _Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male._ **esempio 2:** _Se ti metti questo vestito, allora sei bellissima, altrimenti sei bella comunque, anche senza, rimarrai la donna più bella di questo mondo._

Paragoniamo ora il primo esempio ad un codice di programmazione:

```java
if (beviAcidoCloridrico) {
    stareMale = true;
} else {
    stareMale = false;
}
```

```java
if (mettiQuestoVestito) {
    seiBellissima = true;
} else {
    seiBellissima = false;
}
```

Vediamo quindi come costruire un costrutto di selezione:

```java
if(condizione){
	// blocco di codice da eseguire se la condizione è vera
}
else{
	// blocco di codice da eseguire se la condizione risulta falsa
}
```

La prima parte contiene la parola chiave `if` che ordina al computer di **verificare** le condizioni presenti all’interno delle parentesi ed eseguire blocco di codice contenuto nelle parentesi graffe in caso le condizioni siano vere. La seconda parte contiene la parola chiave `else` che ordina al computer di eseguire il blocco di codice contenuto nelle parentesi graffe se la condizione risulta falsa.

Per comprendere meglio, analizziamo il funzionamento del costrutto:

1. Il computer verifica le condizioni all’interno delle parentesi tonde. Una condizone vera è ad esempio 1 == 1, una falsa è ad esempio 1== 2.

> ATTENZIONE! Per fare un’operazione di confronto, occorre inserire due simboli di uguale ( == ), in quanto un solo = corrisponde ad un’operazione di ASSEGNAZIONE, ad esempio float a = 2.

2. Se la condizione è VERA, viene eseguito il blocco di codice contenuto nelle parentesi graffe, se è falsa invece, si passa al passo 3.
3. Se la condizione è FALSA, viene eseguito il blocco di codice contenuto nelle parentesi graffe dell’else.

### Selezione annidata

La selezione annidata è un’estensione della selezione semplice, che consiste nell’inserimento di uno o più if all’interno di un’altro if. Nel linguaggio comune un’operazione di selezione annidata potrebbe corrispondere ad un’espressione del tipo: _Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola._

Paragoniamo ancora una volta con un linguaggio di programmazione:

```java
if(avròDeiFigli){ 
	if(avrannoDeiFigli){ 
		System.out.println("Sarò nonna"); 
	}
	else{
		System.out.println("Rimarrò madre");
	}
}
else{
	System.out.println("Rimarrò sola");
}
```

Vediamo quindi come costruire un costrutto di selezione annidata:

```java
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

Un secondo if si può inserire anche nell’else:

```java
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

Come in logica e matematica, anche nell’informatica esistono 3 operatori logici.

- Or (o questo o quello)
- And (e)
- Not (non) I loro corrispettivi in linguaggio di programmazione:
- `||`
- `&&`
- `!=` Facciamo degli esempi di comparazione tra proposizioni logiche e in linguaggio di programmazione: _Se queste mele pesano meno di 7 o più 10 le compro._

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

È importante notare che il tipo di dato dell’espressione utilizzata nello statement `switch case` può essere qualsiasi tipo intero o carattere, come `int`, `char` o `enum`. Inoltre, i casi possono essere specificati in qualsiasi ordine e possono anche essere valori costanti o variabili. Tuttavia, non è possibile utilizzare tipi di dati float o double nelle espressioni dello `switch case`.

È inoltre possibile includere più istruzioni all’interno di ciascun caso. 

# Cicli in Java

In Java, come in ogni altro linguaggio di programmazione, i cicli sono dei costrutti che servono a ripetere delle istruzioni per un numero di volte, in base alla veridicità di una condizione.

## Ciclo While

Il ciclo While si presenta come il ciclo più semplice. Il suo scopo è quello di ripetere un blocco di codice se una determinata condizione è vera. Quando questa diventerà falsa, il blocco di istruzioni non verrà più eseguito, ed il programma uscirà dal ciclo.

> _fino a quando questo è vero_ [condizione] _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo while e la sua sintassi:

```java
while(condizione){
	istruzione1;
	istruzione2;
	ecc;
}
```

Facciamo un esempio pratico:

```java
int a = 5;

while(a > 0){
	System.out.println("Il ciclo è in funzione. Giro numero " + a);
	a++;
}
```

output:

```shell
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

Notiamo che dopo aver completato il decimo ciclo, il programma è uscito dal ciclo, non eseguendo più le istruzioni contenute nelle parentesi graffe. Per verificare questo avvenimento, inseriamo un System.out.println dopo il ciclo, per vedere quando il ciclo sarà terminato.

```java
int a = 5;

while(a > 0){
	System.out.println("Il ciclo è in funzione. Giro numero " + a);
	a++;
}
System.out.println("Il programma è uscito dal ciclo");
```

output:

```shell
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

> **NOTA BENE | valore della variabile:** Come puoi vedere, il valore della variabile nell’ultimo giro è 9, non 10, eppure il ciclo ha compiuto 10 giri. Questo è una conseguenza del fatto che in informatica i numeri partono dallo 0, e non da 1. Questo ci tornerà molto utile più avanti.

> **NOTA BENE | incremento di una variabile** Come puoi notare, l’ultima istruzione all’interno del ciclo è `a++` . `a++` è l’equivalente di scrivere `a = a+1`

## Ciclo Do - While

Il ciclo Do - While è un’evoluzione del ciclo While. La differenza principale è che il blocco di istruzioni da eseguire viene eseguito almeno una volta, poi viene verificata la condizione e il blocco di istruzioni verrà eseguito di nuovo fino a quando la condizione non diventerà falsa.

> _esegui [blocco di istruzioni] fino a quando questo è vero_ [condizione] _esegui [blocco di istruzioni]

Vediamo quindi come inserire nel codice un ciclo do-while e la sua sintassi:

```java
do {  
 //blocco di codice 
 }  
while (condizione);
```

Facciamo un esempio pratico:

```java
int i = 0;  
do {  
  System.out.println(i);  
  i++;  
}  
while (i < 5);
```

output:

```shell
0
1
2
3
4
```

In questo esempio, il blocco di istruzioni all’interno del ciclo do-while viene eseguito almeno una volta, indipendentemente dal valore iniziale di `i`. Solo dopo la prima esecuzione, la condizione `i < 5` viene verificata. Se la condizione è vera, il blocco di istruzioni viene eseguito di nuovo. Questo processo continua fino a quando la condizione diventa falsa. In questo caso, dopo che `i` diventa 5, la condizione `i < 5` diventa falsa e il ciclo termina. 