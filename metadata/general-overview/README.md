## 1. Indicazioni generali

[1.1 Introduzione](general-overview#11-introduzione)

[1.2 Conformità](general-overview#12-conformità)

[1.3 Classi di conformità](general-overview#13-classi-di-conformità)

[1.4 Implementazione della struttura gerarchica e relazioni tra risorse](general-overview#14-implementazione-della-struttura-gerarchica-e-relazioni-tra-risorse)

### 1.1 Introduzione

Le Linee Guida recanti le regole tecniche del Repertorio Nazionale dei Dati Territoriali individuano, al cap. 1, l&#39;ambito di applicazione identificato in dataset, serie di dataset e servizi, in coerenza con il [Regolamento 1205/2008].

Lo stesso cap. 1 delinea la struttura, mutuata dallo Standard [ISO 19115], in cui possono essere organizzati i metadati di dataset e serie di dataset e quella relativa alle tipologie di servizi di cui al [Regolamento 976/2009] e al [Regolamento 1089/2010].

La struttura gerarchica dei metadati individuata per i dati permette di generalizzare a livello di serie tutte le informazioni condivise da più dataset e di mantenere a livello di dataset quelle informazioni che effettivamente distinguono un dataset da un altro.

Non esiste, in effetti, una definizione univoca di cosa si intenda per dataset e di conseguenza anche di serie di dataset: l&#39;esatta definizione di dataset può essere funzione del tipo di dato da descrivere, dell&#39;ambiente istituzionale in cui lo stesso viene prodotto, dal modo in cui viene gestito e fornito. Per questo, il modello di metadati proposto è definito in modo da contenere il set minimo di elementi di metadati ed allo stesso tempo risulta sufficientemente &quot;generico&quot; al fine di poter essere adattato alle diverse tipologie di dati che dovranno essere documentati nel Repertorio.

Come precisato nel citato cap.1, la scelta della strutturazione dei metadati nei livelli gerarchici indicati è comunque lasciata alla singola Amministrazione: il principio che deve guidare nella documentazione è quello di scendere all&#39;elemento minimo che si può fornire o a cui si può accedere ovvero di attenersi all&#39;elemento minimo che ha senso descrivere, che può anche non coincidere con l&#39;elemento minimo di fruizione, se esiste.


### 1.2 Conformità
    
#### 1.2.1 Corrispondenza tra metadati RNDT e ISO _core_

Nella tabella 1 è riportata la corrispondenza tra i metadati previsti dal profilo del RNDT e quelli previsti dal _core set_ dello Standard [ISO 19115] (tabella 3, § 6.5). Accanto ad ogni elemento è indicato, tra parentesi, il livello di obbligatorietà (_ **O** _ per obbligatorio, _ **Op** _ per opzionale, _ **C** _ per condizionato).

I diversi livelli di obbligatorietà degli elementi del profilo del RNDT, rispetto ai corrispondenti ISO, sono stati imposti rispettando le regole di cui all&#39;allegato C dello Standard ISO.

Si può, quindi, affermare che i metadati previsti nel set &quot;_core_&quot; di [ISO 19115] rappresentano un sottoinsieme di quelli previsti dal RNDT; pertanto, la conformità di un set di metadati al core di ISO non garantisce la conformità al RNDT in quanto devono essere considerati anche quei metadati obbligatori nel Repertorio ma non previsti nel &quot;_core_&quot; ISO.

Viceversa, la conformità di un set di metadati al profilo del RNDT garantisce la conformità al &quot;_core_&quot; di [ISO 19115].

| **Metadati RNDT** |  **Core** **ISO 19115** |
| --- | --- |
| **Informazioni sui metadati** |
| Identificatore del file (O) | Metadata file identifier (Op) |
| Lingua dei metadati (O) | Metadata language (C) |
| Set dei caratteri dei metadati (C) | Metadata character set (C) |
| Id file precedente (Op) | - |
| Livello gerarchico (O) | - |
| Responsabile dei metadati (O) | Metadata point of contact (O) |
| Data dei metadati (O) | Metadata date stamp (O) |
| Nome dello Standard (O) | Metadata standard name (Op) |
| Versione dello Standard (O) | Metadata standard version (Op) |
| **Identificazione dei dati** |
| Titolo (O) | Dataset title (O) |
| Data (O)Tipo data (O) | Dataset reference date (O) |
| Formato di presentazione (O) | - |
| Responsabile (O) | ~~-~~ |
| Identificatore (O) | - |
| Id livello superiore (O) | - |
| Altri dettagli (Op) | - |
| Descrizione (O) | Abstract describing the dataset (O) |
| Parola chiave (O)Thesaurus (Op) | -- |
| Punto di contatto (O) | Dataset responsible party (Op) |
| Tipo di rappresentazione spaziale (O) | Spatial representation type (Op) |
| Risoluzione spaziale (O) | Spatial resolution of the dataset (Op) |
| Lingua (O) | Dataset language (O) |
| Set di caratteri (C) | Dataset character set (C) |
| Categoria tematica (O) | Dataset topic category (O) |
| Informazioni supplementari (Op) | - |
| **Vincoli sui dati** |
| Limitazione d&#39;uso (Op) | - |
| Vincoli di accesso (O) | - |
| Vincoli di fruibilità (O) | - |
| Altri vincoli (C) | - |
| Vincoli di sicurezza (Op) | - |
| **Estensione dei dati** |
| Localizzazione geografica (O) | Geographic location of the dataset (C) |
| Estensione verticale (Op) | Additional extent information for the dataset(vertical) (Op) |
| Estensione temporale (Op) | Additional extent information for the dataset(temporal) (Op) |
| **Qualità dei dati** |
| Livello di qualità (O) | - |
| Accuratezza posizionale (O) | - |
| Coerenza topologica (C) | - |
| Genealogia (O) | Lineage (Op) |
| Conformità: specifiche (C) | - |
| Conformità: grado (C) | - |
| **Sistema di riferimento** |
| Sistema di riferimento spaziale (O) | Reference system (Op) |
| Sistema di riferimento temporale (C) | - |
| **Distribuzione dei dati** |
| Formato di distribuzione (O) | Distribution format (Op) |
| Distributore (O) | - |
| Risorsa on line (O) | On-line resource (Op) |
| **Gestione dei dati** |
| Frequenza di aggiornamento (Op) | - |


#### 1.2.2 Corrispondenza tra metadati RNDT e INSPIRE

Nella tabella che segue è riportata la corrispondenza tra i metadati previsti dal Repertorio e i metadati INSPIRE, definita al § 4.2.8.1 delle [LG RNDT].

I metadati INSPIRE sono riportati:

- con il numero e il nome indicati nella parte B dell&#39;allegato al [Regolamento 1205/2008] (es. B-10.3 per indicare il metadato riportato al n. 10.3 nella parte B dell&#39;allegato);
- con il numero e il nome indicati all&#39;art. 13 del [Regolamento 1089/2010] (es. art.13-1 per indicare il metadato riportato al n. 1 dell&#39;art. 13);
- con il numero e il nome indicati nella parte B degli allegati V, VI e VII del [Regolamento 1089/2010] (es. V-B.1 per indicare il metadato riportato al n. 1 della parte B dell&#39;allegato V);
- con il nome (in inglese) indicato nel paragrafo 8.3 delle specifiche di dati (_data specifications_) per i metadati specifici per alcune categorie di dati (in questo caso è indicato il riferimento a dette specifiche con DS-8.3).

Per ogni elemento RNDT riportato nei successivi capitoli, inoltre, viene anche indicato, se esistente, il corrispondente elemento INSPIRE.

Anche in questo caso, i metadati INSPIRE risultano essere un sottoinsieme dei metadati del Repertorio; pertanto, la conformità ad INSPIRE non garantisce la conformità al RNDT, mentre è vero il contrario.

| **Metadati RNDT** | **Metadati INSPIRE** |
| --- | --- |
| **Informazioni sui metadati** |
| Identificatore del file | - |
| Lingua dei metadati | B-10.3 - Lingua dei metadati |
| Set dei caratteri dei metadati | - |
| Id file precedente | - |
| Livello gerarchico | B-1.3 - Tipo di risorsa |
| Responsabile dei metadati | B-10.1 - Punto di contatto dei metadati |
| Data dei metadati | B-10.2 - Data dei metadati |
| Nome dello Standard | - |
| Versione dello Standard | - |
| **Identificazione dei dati** |
| Titolo | B-1.1 - Titolo della risorsa |
| Data Tipo data | B-5.2, B-5.3, B-5.4 - Data di pubblicazione, Data dell&#39;ultima revisione, Data di creazione |
| Formato di presentazione | - |
| Responsabile | - |
| Identificatore | B-1.5 - Identificatore univoco della risorsa |
| Id livello superiore | - |
| Altri dettagli | - |
| Descrizione | B-1.2 - Breve descrizione della risorsa |
| Parola chiave | B-3.1 - Valore della parola chiave |
| Thesaurus | B-3.2 - Vocabolario controllato di origine |
| Punto di contatto | B-9.1, B-9.2 - Parte responsabile, Ruolo della parte responsabile |
| Tipo di rappresentazione spaziale | art.13-6 - Tipo di rappresentazione territoriale |
| Risoluzione spaziale | B-6.2 - Risoluzione spaziale |
| Lingua | B-1.7 - Lingua della risorsa |
| Set di caratteri | art.13-5 - Codifica dei caratteri |
| Categoria tematica | B-2.1 - Categoria di argomento |
| Informazioni supplementari | DS-8.3 - Supplemental information |
| **Vincoli sui dati** |
| Limitazione d&#39;uso | - |
| Vincoli di accesso | B-8.1, B-8.2 - Condizioni applicabili all&#39;accesso e all&#39;uso, Vincoli per l&#39;accesso pubblico |
| Vincoli di fruibilità | B-8.1 - Condizioni applicabili all&#39;accesso e all&#39;uso |
| Altri vincoli | B-8.1, B-8.2 - Condizioni applicabili all&#39;accesso e all&#39;uso, Vincoli per l&#39;accesso pubblico |
| **Estensione dei dati** |
| Localizzazione geografica | B-4.1 - Riquadro di delimitazione geografica |
| Estensione verticale | DS-8.3 - Extent |
| Estensione temporale | B-5.1 - Estensione temporale |
| **Qualità dei dati** |
| Livello di qualità | - |
| Accuratezza posizionale | DS-8.3 - Data quality–Quantitative results |
| Coerenza topologica | art.13-4 - Coerenza topologica |
| Genealogia | B-6.1 - Genealogia |
| Conformità: specifiche | B-7.1 - Specifica |
| Conformità: grado | B-7.2 - Grado |
| **Sistema di riferimento** |
| Sistema di riferimento spaziale | art.13-1 - Sistema di riferimento di coordinate |
| Sistema di riferimento temporale | art.13-2 - Sistema di riferimento temporale |
| **Distribuzione dei dati** |
| Formato di distribuzione | art.13-3 - Codifica |
| Distributore | - |
| Risorsa on line | B-1.4 - Localizzatore della risorsa |
| **Gestione dei dati** |
| Frequenza di aggiornamento | DS-8.3 - Maintenance information |
| **Contenuto dei dati raster** |
| Descrizione degli attributi | DS-8.3 - Image description |
| Tipo di contenuto | DS-8.3 - Image description |
| Risoluzione radiometrica | - |
| Triangolazione aerea | - |
| **Rappresentazione spaziale dei dati raster** |
| Numero di dimensioni | DS-8.3 - Spatial representation information |
| Proprietà dimensioni | DS-8.3 - Spatial representation information |
| Geometria della cella | DS-8.3 - Spatial representation information |
| Disponibilità coefficienti della trasformazione | DS-8.3 - Spatial representation information |
| **Rappresentazione spaziale dei dati raster georeferenziati** |
| Disponibilità dei check-points | DS-8.3 - Spatial representation information |
| Descrizione check-points | DS-8.3 - Spatial representation information |
| Punto del pixel | DS-8.3 - Spatial representation information |
| Coordinate dei vertici | DS-8.3 - Spatial representation information |
| **Rappresentazione spaziale dei dati raster georeferenziabili** |
| Disponibilità dei punti di controllo | DS-8.3 - Spatial representation information |
| Disponibilità dei parametri di orientamento | DS-8.3 - Spatial representation information |
| Parametri per la georeferenziazione | DS-8.3 - Spatial representation information |
| **Informazioni specifiche sui servizi** |
| Tipo di servizio | B-2.2 - Tipo di servizio di dati territoriali |
| Tipo di aggancio | - |
| Risorsa accoppiata | B-1.6 - Risorsa accoppiata |
| Operazioni | - |
| **Servizi di dati territoriali invocabili** |
| Categoria | V-B.1 -  Categoria |
| **Servizi di dati territoriali interoperabili** |
| Qualità del servizio – Criteri | VI-B.4.1 - Qualità del servizio-Criteri |
| Qualità del servizio - Misurazione | VI-B.4.2 - Qualità del servizio–Misurazione |
| **Servizi di dati territoriali armonizzati** |
| Metadati di richiamata (Operazioni) | VII-B.3 -  Metadati di richiamata |

### 1.3 Classi di conformità

Le classi di conformità di riferimento per i requisiti e le raccomandazioni sono riportate di seguito in una rappresentazione gerarchica:

- Classe di conformità **1** : **metadata/2.0/datasets-and-series**

  **Titolo:** _Metadati di base per dataset e serie di dataset_

  - Classe di conformità **R1** : **rndt/metadata/2.0/datasets-and-series**

    **Titolo:** _Metadati di base RNDT per dataset e serie di dataset_

  - Classe di conformità **2** : **metadata/2.0/isdss**

    **Titolo** : _Metadati per l&#39;interoperabilità di dataset e serie di dataset_

    - Classe di conformità **R2** : **rndt/metadata/2.0/isdss**

      **Titolo** : _Metadati RNDT per l&#39;interoperabilità di dataset e serie di dataset_

  - Classe di conformità **R8** : **rndt/metadata/2.0/grid-data**

    **Titolo** : _Metadati RNDT per i dati raster_

- Classe di conformità **3** : **metadata/2.0/sds**

  **Titolo** : _Metadati di base per i servizi di dati territoriali_

  - Classe di conformità **R3** : **rndt/metadata/2.0/sds**

    **Titolo** : _Metadati di base RNDT per i servizi di dati territoriali_

  - Classe di conformità **4** : **metadata/2.0/ns**

    **Titolo** : _Metadati per i servizi di rete_

    - Classe di conformità **R4** : **rndt/metadata/2.0/ns**
    
      **Titolo** : _Metadati RNDT per i servizi di rete_

  - Classe di conformità **5** : **metadata/2.0/sds-invocable**

    **Titolo** : _Metadati per i servizi di dati territoriali invocabili_

    - Classe di conformità **R5** : **rndt/metadata/2.0/sds-invocable**

      **Titolo** : _Metadati RNDT per i servizi di dati territoriali invocabili_

    - Classe di conformità **6** : **metadata/2.0/sds-interoperable**

      **Titolo** : _Metadati per i servizi di dati territoriali__interoperabili_

    - Classe di conformità **7** : **metadata/2.0/sds-harmonised**

      **Titolo** : _Metadati per i servizi di dati territoriali__armonizzati_

      - Classe di conformità **R7** : **rndt/metadata/2.0/sds-harmonised**

        **Titolo** : _Metadati RNDT per i servizi di dati territoriali armonizzati_

- Classe di conformità **R9** : **rndt/metadata/2.0/scheduled-data**

  **Titolo** : _Metadati RNDT per le nuove acquisizioni di dati_

Nel caso di metadati che in RNDT, diversamente da INSPIRE, sono comuni a tutte le risorse, vengono definiti requisiti e raccomandazioni specifici indicando a quali requisiti e raccomandazioni INSPIRE corrispondono.

Nei prossimi capitoli, all&#39;inizio di ogni sezione dedicata a ciascuna risorsa da documentare, vengono indicate le classi di conformità (sia INSPIRE che RNDT) di riferimento per i requisiti e le raccomandazioni riportate.

### 1.4 Implementazione della struttura gerarchica e relazioni tra risorse

#### 1.4.1 Gerarchia e relazioni serie/dataset

Come indicato nella premessa, il [Regolamento 1205/2008] relativo ai metadati contempla, per quanto riguarda i dati territoriali, i livelli di serie e dataset.

Dal Regolamento e da [TG MD INSPIRE] si evince che non esiste nessuna relazione tra i due livelli tale da consentire di creare una gerarchizzazione dell&#39;informazione contenuta nei metadati, come previsto dal diagramma UML riportato nella figura 3 del paragrafo 6.2 dello Standard [ISO 19115] e come indicato, a livello informativo, negli allegati G e H del medesimo Standard.

Il RNDT, di converso, prevede la possibilità di implementare, attraverso gli identificatori presenti, la gerarchia e, quindi, le relazioni, se esistenti, tra i livelli previsti.

Il profilo di metadati definito con le [LG RNDT], infatti, prevede, per la gestione delle relazioni tra livelli gerarchici, i metadati &quot;_Identificatore_&quot; (_identifier_) e &quot;_ID livello superiore_&quot; (_series_). Le relative istruzioni di compilazione sono riportate ai successivi paragrafi [2.3.4](#_Identificatore) e [3.2.2](#_ID_livello_superiore).

I casi possibili nella implementazione della gerarchia, pertanto, sono i seguenti:

1. nel caso di una serie o di un dataset &quot;flat&quot;, cioè senza nessuna relazione con una serie, i metadati &quot;_Identificatore_&quot; e &quot;_Id livello superiore_&quot; assumeranno lo stesso valore in riferimento al livello gerarchico corrente;
2. nel caso di un dataset appartenente a una serie, il metadato &quot;_Id livello superiore_&quot; assumerà il valore del metadato &quot;_Identificatore_&quot; della serie a cui il dataset appartiene.

    
#### 1.4.2 Relazioni dati/servizi

Per quanto riguarda le relazioni tra dati e servizi, nel set di metadati individuato dal RNDT sono presenti alcuni elementi che consentono di documentare tali relazioni.

In particolare, a livello di metadati dei servizi, l&#39;elemento &quot;_Risorsa accoppiata_&quot; (_operatesOn_) consente di indicare i dataset agganciati dal servizio indicando il link dei relativi metadati.

A livello di metadati dei dati, invece, l&#39;elemento &quot;_Risorsa on-line_&quot; può essere utilizzato per indicare l&#39;URL dei servizi disponibili sui dati (v., a tale proposito, le indicazioni al § [3.6.3](#_Risorsa_on-line)).

Nella figura che segue sono rappresentate le relazioni tra i vari livelli in cui è possibile descrivere i metadati dei dati territoriali e relativi servizi.



Ai fini dell&#39;accessibilità delle risorse geografiche nel geoportale INSPIRE, il processo di collegamento tra dati e servizi è basato oltre che sui metadati, come indicato innanzi, anche sulle informazioni documentate nei documenti di _GetCapabilities_ dei servizi di rete. È necessario, pertanto, configurare correttamente i servizi di rete secondo le linee guida tecniche INSPIRE di riferimento.

A tale proposito, si rimanda alla **guida operativa per interventi correttivi su metadati e servizi di rete** che, al cap. 4, fornisce indicazioni puntuali in merito.

#### 1.4.3 Approccio semplificato per il collegamento dati/servizi

Nell&#39;ambito di INSPIRE è in corso di sperimentazione un nuovo approccio per la possibile semplificazione del collegamento tra dati e servizi con l&#39;obiettivo di aumentare la loro accessibilità nel geoportale INSPIRE e, quindi, agevolare l&#39;accesso a tali risorse da parte degli utenti.

Come segnalato nella guida sugli interventi correttivi citata innanzi, infatti, la mancata implementazione del corretto collegamento tra le risorse ha comportato che l&#39;attuale livello di accessibilità dei set di dati attraverso i servizi di visualizzazione e download sia molto basso.

Come noto, attualmente l&#39;indicazione di tale collegamento richiede:

- la documentazione degli URL degli endpoint dei servizi (WMS, WFS e/o Atom) nei metadati dei dati;
- la compilazione dei metadati dei servizi (oltre a quelli dei dati);
- la presenza nel documento di _GetCapabilities_ dei servizi di rete delle estensioni previste dalle linee guida INSPIRE sui servizi di visualizzazione e download;
- l&#39;indicazione degli URL dei metadati dei servizi e dei dataset resi disponibili nel documento di _GetCapabilities_ dei servizi di rete;
- l&#39;indicazione degli identificativi dei dataset resi disponibili nel documento di _GetCapabilities_.

Il nuovo approccio, invece, richiederebbe:

- la compilazione dei metadati solo dei dataset con l&#39;indicazione, all&#39;interno di essi, degli endpoint (_GetCapabilities_) dei servizi di visualizzazione e download;
- l&#39;aggiunta dei metadati _Protocollo_, _Profilo applicativo_, _Descrizione_ con riferimento all&#39;URL del servizio indicato nel record del dataset_;_
- il documento di _GetCapabilities_ dei servizi di rete (in cui non sarebbero più richieste le estensioni INSPIRE) solo con l&#39;indicazione del titolo e dell&#39;organizzazione responsabile (oltre a quanto richiesto dallo standard base OGC);

Come si evince dalle [LG RNDT] i tre metadati aggiuntivi indicati innanzi sono richiesti comunque a prescindere dal tipo di servizio indicato. Le istruzioni di compilazione relative ai nuovi elementi sono riportati al § [3.6.3](#_Risorsa_on-line).

Ciò consentirà di avere metadati già conformi al nuovo approccio quando questo sarà adottato formalmente.

Da tenere presente che, se la sperimentazione si chiuderà positivamente e il nuovo approccio sarà formalizzato, questo non sostituirà, ma si aggiungerà come alternativa all&#39;approccio attuale. Di conseguenza, se ci sono in corso implementazioni dell&#39;approccio attuale, è opportuno non stoppare tali implementazioni. In pratica, si può mantenere l&#39;approccio attuale (qualora già implementato) per i dati già pubblicati e utilizzare il nuovo approccio per i nuovi dati.

---

Vai a [2. Requisiti comuni per i metadati RNDT](common)
