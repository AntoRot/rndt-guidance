### 4.5.1 Identificazione dei servizi


#### 4.5.1.1 Metadati di richiamata

|  |  |
| --- | --- |
| **Nome elemento** | Operazioni |
| **Riferimento** | [LG RNDT] – tab. VI-5 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Metadati di richiamata |
| **Definizione** | Informazioni sulle operazioni che compongono il servizio. |
| **Istruzioni di implementazione** | - **Nome operazione** [1] – Testo libero; - **DCP** [1..\*] – L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_DCPList_&quot; di cui al § 4.2.5.4 [LG RNDT]; - **Parametri** [0..\*] – Parametri da utilizzare per richiamare l&#39;operazione; - **Punto di connessione** [1..\*] – Riferimento per l&#39;accesso all&#39;interfaccia del servizio da esprimere come URL; - **Nome richiesta** [0..1] – Testo libero. |

**REQUISITO R7.1** - **```rndt/metadata/2.0/req/sds-harmonised/invocation-metadata```**

Devono essere indicate tutte le operazioni e il relativo elenco degli endpoint insieme alle informazioni sui parametri obbligatori e facoltativi per ciascuna operazione attraverso l&#39;elemento _```srv:containsOperations/srv:SV_OperationMetadata```_ per ciascuna operazione fornita.

Il contenuto di questo elemento deve essere specificato secondo lo Standard 19119, paragrafo C.2.

---

**REQUISITO R7.2** - **```metadata/2.0/req/sds-harmonised/operation-metadata```**

Per ciascuna operazione, devono essere forniti, oltre agli elementi di cui al Requisito [R3.2](#reqR32), anche le informazioni relativi ai **parametri** attraverso l&#39;elemento _```srv:parameters/srv:SV_Parameter```_ con una descrizione del parametro della singola operazione da utilizzare per richiamare l&#39;operazione. Il contenuto per questo elemento deve essere specificato come indicato dal Requisito [7.3](#7.3). La molteplicità di questo elemento è 0..N ed è obbligatorio per tutti i parametri obbligatori e facoltativi forniti dall&#39;operazione.

---

<a name=7.3>**REQUISITO 7.3**</a>  **```metadata/2.0/req/sds-harmonised/operation-metadata-parameters```**

Per tutti i parametri obbligatori e facoltativi di ciascuna operazione devono essere fornite le informazioni relative ai seguenti elementi figli di _```srv:parameters/srv:SV_Parameter```_:

- _```srv:name/gco:aName```_ con il nome del parametro utilizzato dal servizio. L&#39;elemento _```srv:name/gco:attributeType```_ deve contenere il record o la parte del tipo del nome dell&#39;attributo. La molteplicità di _```srv:name```_ è 1;

- _```srv:optionality```_ con l&#39;indicazione se l&#39;attributo è obbligatorio o facoltativo. La molteplicità di questo elemento è 1;

- _```srv:repeatability/gco:Boolean```_ con l&#39;indicazione se l&#39;attributo può essere presente più di una volta in un&#39;operazione. Il valore &quot;_true_&quot; deve essere usato per indicare che l&#39;attributo può essere ripetuto; il valore &quot;_false_&quot; che l&#39;attributo può essere utilizzato solo una volta;

- _```srv:valueType/gco:TypeName/gco:Name```_ con l&#39;indicazione del tipo dei dati dell&#39;attributo.

---
