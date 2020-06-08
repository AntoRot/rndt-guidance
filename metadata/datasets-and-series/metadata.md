## 3.1 Informazioni sui metadati

### 3.1.1 Livello gerarchico

|  |  |
| --- | --- |
| **Nome elemento** | Livello gerarchico |
| **Riferimento** | [LG RNDT] – tab. I-5 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Tipo di risorsa |
| **Definizione** | Categoria di informazione cui vengono applicati i metadati. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_ScopeCode_&quot; (§ 4.2.3.13 [LG RNDT]). |

**REQUISITO 1.1** - **```metadata/2.0/req/datasets-and-series/resource-type```**

Il tipo di risorsa deve essere dichiarato come &quot;_dataset_&quot; o &quot;_series_&quot; (serie di dataset), di cui all&#39;elenco di codici _```MD_ScopeCode```_, attraverso l&#39;elemento _```gmd:MD_Metadata/gmd:hierarchyLevel/gmd:MD_ScopeCode```_.

---

***Raccomandazione R1.1** - **```rndt/metadata/2.0/rec/datasets-and-series/resource-type```***

*La scelta del valore più appropriato per il tipo di risorsa dovrebbe essere fatta tenendo conto delle definizioni presenti al § 2.5 delle [LG RNDT] e alle seguenti indicazioni:*

*- **dataset** : collezione identificabile di dati che può essere parte di una serie oppure una risorsa a sè stante;*

*- **serie** : collezione di risorse o di dataset in relazione tra di loro che condividono le stesse specifiche di prodotto.*

---

**Esempio di XML:**
