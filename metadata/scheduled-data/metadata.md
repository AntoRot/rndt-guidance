## 6.1 Informazioni sui metadati


### 6.1.1 Livello gerarchico

|  |  |
| --- | --- |
| **Nome elemento** | Livello gerarchico |
| **Riferimento** | [LG RNDT] – tab. I-5 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Tipo di risorsa |
| **Definizione** | Categoria di informazione cui vengono applicati i metadati. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere il valore &quot;_model_&quot; (_modello_) dell&#39;elenco di codici &quot;_MD\_ScopeCode_&quot; (§ 4.2.3.13 [LG RNDT]). |

**REQUISITO R9.1** - **```rndt/metadata/2.0/req/scheduled-data/resource-type```**

Per indicare che il tipo di risorsa che si sta descrivendo è un set di dati in fase di acquisizione, deve essere dichiarato con il valore &quot;_model_&quot; (_modello_) di cui all&#39;elenco di codici _```MD_ScopeCode```_, attraverso l&#39;elemento _```gmd:MD_Metadata/gmd:hierarchyLevel/gmd:MD_ScopeCode```_.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:hierarchyLevel>
    <gmd:MD_ScopeCode codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_ScopeCode" codeListValue="model">modello</gmd:MD_ScopeCode>
  </gmd:hierarchyLevel>
  …
</gmd:MD_Metadata>
```
---

> Vai a [**6.2 Identificazione dei dati**](identification.md)
