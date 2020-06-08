## 3.4 Qualità dei dati

**Elementi:**

3.4.1 Livello di qualità

3.4.2 Accuratezza posizionale

3.4.3 Coerenza topologica

3.4.4 Genealogia

3.4.5 Conformità: specifiche


### 3.4.1 Livello di qualità

|  |  |
| --- | --- |
| **Nome elemento** | Livello di qualità |
| **Riferimento** | [LG RNDT] – tab. I-33 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Livello cui sono applicate le informazioni di qualità. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_ScopeCode_&quot; (§ 4.2.3.13 [LG RNDT]). |

**REQUISITO 1.9** - **```metadata/2.0/req/datasets-and-series/one-data-quality-element```**

Deve esserci un solo elemento _```gmd:dataQualityInfo/gmd:DQ_DataQuality```_ con riferimento all&#39;intero dataset o serie di dataset descritto.

Il campo di applicazione della qualità deve essere codificato attraverso l&#39;elemento _```gmd:scope/gmd:DQ_Scope/gmd:level/gmd:MD_ScopeCode```_ con il valore &quot;dataset&quot; o &quot;series&quot; presente nell&#39;elenco di codici ISO _```MD_ScopeCode```_.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dtataQualityInfo>
    <gmd:DQ_DataQuality>
      <gmd:scope>
        <gmd:DQ_Scope>
          <gmd:level>
            <gmd:MD_ScopeCode codeListValue="dataset" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_ScopeCode">dataset</gmd:MD_ScopeCode>
          </gmd:level>
        </gmd:DQ_Scope>
      </gmd:scope>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```
