## 3.3 Estensione dei dati

### 3.3.1 Estensione verticale

|  |  |
| --- | --- |
| **Nome elemento** | Estensione verticale |
| **Riferimento** | [LG RNDT] – tab. I-31 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Dominio verticale dei dati. |
| **Istruzioni di implementazione** | - **Quota minima** [1] - utilizzare il tipo _gco:Real_; - **Quota massima** [1] - utilizzare il tipo _gco:Real_; - **CRS verticale** [1] - Per la documentazione di questo elemento, utilizzare, facendo comunque riferimento all&#39;elenco di codici &quot;_MD\_ReferenceSystemCode_&quot; (§ 4.2.3.11 [LG RNDT]) utilizzando l&#39;URI riportato nella tabella di cui all&#39;allegato [A.1](../code-lists/md-reference-system-code.md). |

***Raccomandazione R1.8** - **```rndt/metadata/2.0/rec/datasets-and-series/vertical-extent```***

*L&#39;estensione verticale può essere documentata attraverso l&#39;elemento ```gmd:extent/gmd:EX_Extent/gmd:verticalElement/gmd:EX_VerticalExtent```.*

*Se documentato, devono essere fornite le seguenti informazioni:*

*- **quota minima** , attraverso l&#39;elemento ```gmd:minimumValue/gco:Real```, utilizzando come unità di misura il metro (m);*

*- **quota massima** , attraverso l&#39;elemento ```gmd:maximumValue/gco:Real```, utilizzando come unità di misura il metro (m);*

*- **CRS verticale** , attraverso l&#39;elemento ```gmd:verticalCRS```.*

*La molteplicità dell&#39;elemento ```gmd:extent/gmd:EX_Extent/gmd:verticalElement``` è 0..1.*

*Per l&#39;elemento &quot;CRS verticale&quot; deve essere utilizzato, facendo comunque riferimento all&#39;URI indicato nella tabella &quot;MD\_ReferenceSystemCode&quot; di cui all&#39;allegato [A.1](../code-lists/md-reference-system-code.md), il tag ISO relativo con la compilazione del solo attributo ```href```.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:extent>
        <gmd:EX_Extent>
         …
          <gmd:verticalElement>
            <gmd:EX_VerticalExtent>
              <gmd:minimumValue>
                <gco:Real>15.56</gco:Real>
              </gmd:minimumValue>
              <gmd:maximumValue>
                <gco:Real>345.15</gco:Real>
              </gmd:maximumValue>
              <gmd:verticalCRS xlink:href="http://www.opengis.net/def/crs/EPSG/0/6704"/>
            </gmd:EX_VerticalExtent>
          </gmd:verticalElement>
        </gmd:EX_Extent>
      </gmd:extent>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
---

> Vai a [**3.4 Qualità dei dati**](data-quality.md)
