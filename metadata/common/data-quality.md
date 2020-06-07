## 2.6 Qualità dei dati

**Elementi:**

[2.6.1 Conformità: specifiche](data-quality.md#261-conformità-specifiche)

[2.6.2 Conformità: grado](data-quality.md#262-conformità-grado)

### 2.6.1 Conformità: specifiche

|  |  |
| --- | --- |
| **Nome elemento** | Conformità: specifiche |
| **Riferimento** | [LG RNDT] – tab. I-37, tab. V-29 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Conformità - specifica |
| **Definizione** | Citazione delle specifiche INSPIRE (adottate a norma dell&#39;art. 7 par. 1 della direttiva 2007/2/CE) cui la risorsa si conforma. |
| **Istruzioni di implementazione** | - **Titolo** [1] – Testo libero; - **Data** [1] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1] **–** Il valore da inserire, tratto dall&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]), è &quot;_pubblicazione_&quot; (_publication_). Nel tracciato XML è presente anche un ulteriore elemento (che è obbligatorio per gli schemi XSD ma che non è richiesto nè da INSPIRE nè dal RNDT): &quot;_explanation_&quot;. Valorizzare tale elemento come da esempio XML. |

**REQUISITO C.20** - **```metadata/2.0/req/common/conformity```**

Il grado di conformità della risorsa rispetto alle disposizioni di esecuzione INSPIRE, ai documenti di specifica o alle classi di conformità, deve essere documentato attraverso uno o più elementi _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_. Per ogni dichiarazione di conformità (cioè per ogni specifica), deve essere utilizzato un elemento _```gmd:DQ_ConformanceResult```_ ad hoc.

La molteplicità di questo elemento è 1..N.

---

**Requisito C.21** - **```metadata/2.0/req/common/conformity-specification```**

Ogni elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_ deve contenere la citazione della disposizione di esecuzione INSPIRE, del documento di specifica o della classe di conformità, compresi il titolo ufficiale e la data di pubblicazione del documento, attraverso l&#39;elemento _```gmd:specification/gmd:CI_Citation```_.

Il titolo deve essere indicato attraverso l&#39;elemento _```gmd:title```_. Per i documenti delle disposizioni di esecuzione INSPIRE il valore di tale elemento deve corrispondere esattamente al titolo ufficiale del documento nella lingua dei metadati.

La data di pubblicazione deve essere indicata attraverso l&#39;elemento _```gmd:date```_ e deve essere espressa in conformità allo Standard ISO 8601 includendo solo la parte della data (e non anche quella relativa all&#39;orario).

Deve essere presente anche l&#39;elemento relativo al codice del tipo di data, _```gmd:date/gmd:CI_Date/gmd:dateType/gmd:CI_DateTypeCode```_, con il valore &quot;_pubblicazione_&quot; (_publication_) presente nell&#39;elenco di codici ISO _```CI_DateTypeCode```_.

---


### 2.6.2 Conformità: grado

|  |  |
| --- | --- |
| **Nome elemento** | Conformità: grado |
| **Riferimento** | [LG RNDT] – tab. I-38, tab. V-30 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Conformità - grado |
| **Definizione** | Indicazione del grado di conformità alle specifiche INSPIRE (adottate a norma dell&#39;art. 7 par. 1 della direttiva 2007/2/CE). |
| **Istruzioni di implementazione** | Tipo booleano. Indicare &quot;true&quot; se i dati sono conformi alle specifiche indicate, &quot;false&quot; altrimenti. Se la conformità non è stata ancora valutata, lasciare vuoto il tag. |

**REQUISITO C.22** - **```metadata/2.0/req/common/conformity-degree```**

Ogni elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_, che contiene la citazione di una specifica come da Requisito [C.21](#reqC21), deve includere anche il grado di conformità dichiarato verso quella specifica attraverso la proprietà _```gmd:pass```_ con l&#39;elemento _```gco:Boolean```_ che dovrà contenere il valore &quot;true&quot; nel caso di una risorsa conforme alla specifica, il valore &quot;false&quot; nel caso opposto. Se la conformità non è stata ancora valutata, l&#39;elemento _```gmd:pass```_ dovrà essere vuoto e contenere l&#39;attributo _```nil reason```_ con il valore &quot;_unknown_&quot;.

---

**Esempi di XML**

```xml
<gmd:MD_Metadata>
…
  <gmd:dataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_DomainConsistency>
          <gmd:result>
            <gmd:DQ_ConformanceResult>
            …
              <gmd:pass>
                <!-- Se i dati non sono conformi il valore deve essere "false" -->
                <gco:Boolean>true</gco:Boolean>
              </gmd:pass>
              …
            </gmd:DQ_ConformanceResult>
          </gmd:result>
        </gmd:DQ_DomainConsistency>
      </gmd:report>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
…
</gmd:MD_Metadata>
```    


```xml
<gmd:MD_Metadata>
…
  <gmd:dataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_DomainConsistency>
          <gmd:result>
            <gmd:DQ_ConformanceResult>
            …
              <gmd:pass gco:nilReason="unknown"/>
              …
            </gmd:DQ_ConformanceResult>
          </gmd:result>
        </gmd:DQ_DomainConsistency>
      </gmd:report>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
…
</gmd:MD_Metadata>
```
