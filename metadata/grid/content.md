## 5.1 Informazioni sul contenuto

**Elementi:**

[5.1.1 Descrizione degli attributi](#511-descrizione-degli-attributi)

[5.1.2 Tipo di contenuto](#512-tipo-di-contenuto)

[5.1.3 Risoluzione radiometrica](#513-risoluzione-radiometrica)

[5.1.4 Triangolazione aerea](#514-triangolazione-aerea)



### 5.1.1 Descrizione degli attributi

|  |  |
| --- | --- |
| **Nome elemento** | Descrizione degli attributi |
| **Riferimento** | [LG RNDT] – tab. II-1 |
| **Molteplicità** | [1] |
| **Definizione** | Descrizione dell&#39;attributo descritto dal valore di misura. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO R8.1** - **```rndt/metadata/2.0/req/grid-data/attribute-description```**

La descrizione dell&#39;attributo descritto dal valore di misura deve essere indicata attraverso l&#39;elemento _```gmd:contentInfo/gmd:MD_ImageDescription/gmd:attributeDescription/gco:RecordType```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:contentInfo>
    <gmd:MD_ImageDescription>
      <gmd:attributeDescription>
        <gco:RecordType>valore di RGB dell'immagine</gco:RecordType>
      </gmd:attributeDescription>
      …
    </gmd:MD_ImageDescription>
  </gmd:contentInfo>
  …
</gmd:MD_Metadata>
```

### 5.1.2 Tipo di contenuto

|  |  |
| --- | --- |
| **Nome elemento** | Tipo di contenuto |
| **Riferimento** | [LG RNDT] – tab. II-2 |
| **Molteplicità** | [1] |
| **Definizione** | Tipo di informazione rappresentato dal valore della cella. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_CoverageContentTypeCode_&quot; (§ 4.2.3.8 [LG RNDT]). |

**REQUISITO R8.2** - **```rndt/metadata/2.0/req/grid-data/content-type```**

Deve essere indicato il tipo di informazione rappresentato dal valore della cella attraverso l&#39;elemento _```gmd:contentInfo/gmd:MD_ImageDescription/gmd:contentType/gco:MD_CoverageContentTypeCode```_ con riferimento a uno dei valori dell&#39;elenco di codici _```MD_ CoverageContentTypeCode```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:contentInfo>
    <gmd:MD_ImageDescription>
    …
      <gmd:contentType>
        <gco:MD_CoverageContentTypeCode codeList="https://standards.iso.org/iso/19139/resources/gmxCodelists.xml# MD_ CoverageContentTypeCode" codeListValue="image">Immagine</gco: MD_CoverageContentTypeCode>
      </gmd:contentType>
    </gmd:MD_ImageDescription>
  </gmd:contentInfo>
  …
</gmd:MD_Metadata>
```


### 5.1.3 Risoluzione radiometrica

|  |  |
| --- | --- |
| **Nome elemento** | Risoluzione radiometrica |
| **Riferimento** | [LG RNDT] – tab. II-3 |
| **Molteplicità** | [0..1] |
| **Definizione** | Numero massimo di bit significativi in cui può essere rappresentata l&#39;intensità radiometrica di ogni pixel. |
| **Istruzioni di implementazione** | Utilizzare il tipo _gco:Integer_. |

**REQUISITO R8.3** - **```rndt/metadata/2.0/req/grid-data/bits-per-value```**

Deve essere indicato il numero di bit per pixel rappresentativo della risoluzione radiometrica attraverso l&#39;elemento _```gmd:contentInfo/gmd:MD_ImageDescription/gmd:dimension/gmd:MD_Band/gmd:bitsPerValue/gco:Integer```_.

La molteplicità di questo elemento è 0..1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:contentInfo>
    <gmd:MD_ImageDescription>
    …
      <gmd:dimension>
        <gmd:MD_Band>
          <gmd:bitsPerValue>
            <gco:Integer>8</gco:Integer>
          </gmd:bitsPerValue>
        </gmd:MD_Band>
      </gmd:dimension>
      …
    </gmd:MD_ImageDescription>
  </gmd:contentInfo>
  …
</gmd:MD_Metadata>
```

### 5.1.4 Triangolazione aerea

|  |  |
| --- | --- |
| **Nome elemento** | Triangolazione aerea |
| **Riferimento** | [LG RNDT] – tab. II-4 |
| **Molteplicità** | [0..1] |
| **Definizione** | Indicazione se la triangolazione aerea è stata effettuata o meno. |
| **Istruzioni di implementazione** | Tipo dato booleano. |

**REQUISITO R8.4** - **```rndt/metadata/2.0/req/grid-data/triangulation-indicator```**

Devono essere fornite informazioni sulla triangolazione aerea attraverso l&#39;elemento _```gmd:contentInfo/gmd:MD_ImageDescription/gmd:triangulationIndicator/gco:Boolean```_. Il valore &quot;_true_&quot; indica che la triangolazione aerea è stata effettuata, &quot;_false_&quot; il caso contrario.

La molteplicità di questo elemento è 0..1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:contentInfo>
    <gmd:MD_ImageDescription>
    …
      <gmd:triangulationIndicator>
        <gco:Boolean>true</gco:Boolean >
      </gmd:triangulationIndicator>
    …
    </gmd:MD_ImageDescription>
  </gmd:contentInfo>
  …
</gmd:MD_Metadata>
```
---

> Vai a [**5.2 Rappresentazione spaziale dei dati raster**](spatial-representation.md)
