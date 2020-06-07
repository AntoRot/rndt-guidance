## 2.5 Estensione dei dati

**Elementi:**

2.5.1 Localizzazione geografica

### 2.5.1 Localizzazione geografica

|  |  |
| --- | --- |
| **Nome elemento** | Localizzazione geografica |
| **Riferimento** | [LG RNDT] – tab. I-30, tab. V-26, tab. VII-16 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Riquadro di delimitazione geografica |
| **Definizione** | Estensione della risorsa nello spazio geografico fornita sotto forma di un riquadro di delimitazione. |
| **Istruzioni di implementazione** | - **Longitudine ovest** [1] - Utilizzare il tipo _gco:Decimal_; - **Longitudine est** [1] - Utilizzare il tipo _gco:Decimal_; - **Latitudine sud** [1] - Utilizzare il tipo _gco:Decimal_; - **Latitudine nord** [1] - Utilizzare il tipo _gco:Decimal_ |

**Requisito C.19** - **metadata/2.0/req/common/bounding-box**

Deve essere indicato il più piccolo riquadro di delimitazione geografica (bounding box) che copre il dataset o la serie di dataset attraverso l&#39;elemento _gmd:extent/gmd:EX\_Extent/gmd:geographicElement/gmd:EX\_GeographicBoundingBox_.

La molteplicità di questo elemento è 1.

Le coordinate della longitudine est e ovest e della latitudine nord e sud devono essere espresse in gradi decimali con una precisione di almeno due cifre decimali nel sistema di riferimento WGS84.

---

**Esempio di XML:**
