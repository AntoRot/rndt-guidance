## 3.2 Identificazione dei dati

**REQUISITO 1.2** - **```metadata/2.0/req/datasets-and-series/only-one-md-data-identification```**

La prima proprietà _```gmd:identificationInfo```_ dell&#39;elemento _```gmd:MD_Metadata```_ deve contenere solo un elemento _```gmd:MD_DataIdentification```_ per identificare il dataset o la serie di dataset descritto.

---

***Raccomandazione 1.1** - **```metadata/2.0/rec/datasets-and-series/md-element-id```***

*L&#39;elemento ```gmd:MD_DataIdentification``` dovrebbe contenere un identificatore univoco dell&#39;elemento stesso per poter essere utilizzato come riferimento all&#39;interno dei metadati dei servizi per indicare la risorsa accoppiata.*

*Questo identificatore dovrebbe essere fornito come valore dell&#39;attributo ```id``` dell&#39;elemento ```gmd:MD_DataIdentification```.*

*Esso dovrebbe essere persistente per un particolare dataset o servizio e univoco fra tutti gli attributi id utilizzati nel documento di metadati e in altri documenti XML in cui potrebbe apparire (come nelle risposte GetRecords di un servizio di ricerca). La persistenza degli attributi id è importante per impedire l&#39;interruzione dei collegamenti della risorsa accoppiata tra i metadati del servizio e i metadati del dataset.*

---

**Elementi:**

3.2.1 Formato di presentazione

3.2.2 ID livello superiore

3.2.3 Altri dettagli

3.2.4 Parole chiave

3.2.5 Set di caratteri

3.2.6 Tipo di rappresentazione spaziale

3.2.7 Risoluzione spaziale

3.2.8 Lingua

3.2.9 Categoria tematica

3.2.10 Informazioni supplementari
