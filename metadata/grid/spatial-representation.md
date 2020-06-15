## 5.2 Rappresentazione spaziale dei dati raster

**Elementi:**

[5.2.1 Numero di dimensioni](#521-numero-di-dimensioni)

[5.2.2 Proprietà dimensioni](#522-proprietà-dimensioni)

[5.2.3 Geometria della cella](#523-geometria-della-cella)

[5.2.4 Disponibilità coefficienti della trasformazione](#524-disponibilità-coefficienti-della-trasformazione)



### 5.2.1 Numero di dimensioni

|  |  |
| --- | --- |
| **Nome elemento** | Numero di dimensioni |
| **Riferimento** | [LG RNDT] – tab. II-5 |
| **Molteplicità** | [1] |
| **Definizione** | Numero degli assi spaziali-temporali indipendenti. |
| **Istruzioni di implementazione** | Utilizzare il tipo _gco:Integer_. |

**REQUISITO R8.5** - **```rndt/metadata/2.0/req/grid-data/number-of-dimensions```**

Per indicare il numero di assi della griglia deve essere utilizzato l&#39;elemento _```gmd:spatialRepresentationInfo/*/gmd:numberOfDimensions/gco:Integer```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_Georectified> [oppure <gmd: MD_Georeferenceable >]
      <gmd:numberOfDimensions>
        <gco:Integer>2</gco:Integer>
      </gmd:numberOfDimensions>
      …
    </gmd:MD_Georectified> [oppure </gmd:MD_Georeferenceable>]
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.2.2 Proprietà dimensioni

|  |  |
| --- | --- |
| **Nome elemento** | Proprietà dimensioni |
| **Riferimento** | [LG RNDT] – tab. II-6 |
| **Molteplicità** | [1..\*] |
| **Definizione** | Informazioni sulle proprietà degli assi spaziali-temporali. |
| **Istruzioni di implementazione** | - **Nome dimensione** [1] – L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_DimensionNameTypeCode_&quot; (§ 4.2.3.9 [LG RNDT]); - **Misura dimensione** [1] – Utilizzare il tipo _gco:Integer_; - **Risoluzione** [0..1] - Indicare il valore in numero reale come da esempio XML. |

**REQUISITO R8.6** - **```rndt/metadata/2.0/req/grid-data/axis-dimension-properties```**

Devono essere fornite le informazioni relative alle proprietà degli assi della griglia attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/*/gmd:axisDimensionProperties```_. La molteplicità di questo elemento è 1..N.

Per ciascun asse, devono essere fornite le seguenti informazioni:

- **nome dimensione** attraverso l&#39;elemento _```gmd:MD_Dimension/gmd:dimensionName/gmd:MD_DimensionNameTypeCode```_ con riferimento a uno dei valori dell&#39;elenco di codici ISO _```MD_DimensionNameTypeCode```_. La molteplicità di questo elemento è 1;

- **misura dimensione** attraverso l&#39;elemento _```gmd:MD_Dimension/gmd:dimensionSize/gco:Integer```_ con l&#39;indicazione del numero di elementi lungo l&#39;asse considerato. La molteplicità di questo elemento è 1;

- **risoluzione** attraverso l&#39;elemento _```gmd:MD_Dimension/gmd:resolution/gco:Measure```_ con l&#39;indicazione del grado di dettaglio dei dati (dimensione del lato della cella elementare). L&#39;unità di misura da utilizzare è il metro (m) da indicare attraverso l&#39;attributo uom che deve assumere il valore [http://standards.iso.org/iso/19139/resources/uom/ML\_gmxUom.xml#m](http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/uom/gmxUom.xml#m). Il valore della misura deve essere espresso come numero reale. La molteplicità di questo elemento è 0..1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo >
    <gmd:MD_ Georectified> [oppure <gmd: MD_Georeferenceable>]
    …
      <gmd:axisDimensionProperties>
        <gmd:MD_Dimension>
          <gmd:dimensionName>
            <gmd:MD_DimensionNameTypeCode codeListValue="row" codeList="https://standards.iso.org/iso/19139/resources/gmxCodelists.xml# MD_DimensionNameTypeCode ">riga</gmd:MD_DimensionNameTypeCode>
          </gmd:dimensionName>
          <gmd:dimensionSize>
            <gco:Integer>37600</gco:Integer>
          </gmd:dimensionSize>
          <gmd:resolution>
            <gco:Measure uom="http://standards.iso.org/iso/19139/resources/uom/ML_gmxUom.xml#m" >5.0</gco:Measure>
          </gmd:resolution>
        </gmd:MD_Dimension>
      </gmd:axisDimensionProperties>
      <gmd:axisDimensionProperties>
        <gmd:MD_Dimension>
          <gmd:dimensionName>
            <gmd:MD_DimensionNameTypeCode codeListValue="column " codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/uom/gmxUom.xml#m">colonna</gmd:MD_DimensionNameTypeCode>
          </gmd:dimensionName>
          <gmd:dimensionSize>
            <gco:Integer>53334</gco:Integer>
          </gmd:dimensionSize>
          <gmd:resolution>
            <gco:Measure uom="http://standards.iso.org/iso/19139/resources/uom/ML_gmxUom.xml#m" >5.0</gco: Measure>
          </gmd:resolution>
        </gmd:MD_Dimension>
      </gmd:axisDimensionProperties>
      …
    </gmd:MD_ Georectified> [oppure <gmd: MD_Georeferenceable>]
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.2.3 Geometria della cella

|  |  |
| --- | --- |
| **Nome elemento** | Geometria della cella |
| **Riferimento** | [LG RNDT] – tab. II-7 |
| **Molteplicità** | [1] |
| **Definizione** | Indicazione dei dati raster come punti o celle. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_CellGeometryCode_&quot; (§ 4.2.3.6 [LG RNDT]). |

**REQUISITO R8.7** - **```rndt/metadata/2.0/req/grid-data/cell-geometry```**

Deve essere indicato se i dati raster sono rappresentati come punti o come celle attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/*/gmd:cellGeometry/gmd:MD_CellGeometryCode```_ con riferimento a uno dei valori dell&#39;elenco di codici ISO _```MD_CellGeometryCode```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_ Georectified> [oppure <gmd:MD_Georeferenceable>]
  …
      <gmd:cellGeometry>
        <gmd:MD_CellGeometryCode codeListValue="area" codeList="https://standards.iso.org/iso/19139/resources/gmxCodelists.xml# MD_CellGeometryCode ">area</gmd:MD_DimensionNameTypeCode>
      </gmd:cellGeometry>
      …
    </gmd:MD_ Georectified> [oppure <gmd: MD_Georeferenceable>]
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.2.4 Disponibilità coefficienti della trasformazione

|  |  |
| --- | --- |
| **Nome elemento** | Disponibilità coefficienti della trasformazione |
| **Riferimento** | [LG RNDT] – tab. II-8 |
| **Molteplicità** | [1] |
| **Definizione** | Indicazione se esistono o meno i coefficienti della trasformazione affine per il passaggio da coordinate immagine a coordinate terreno. |
| **Istruzioni di implementazione** | Tipo dato booleano. |

**REQUISITO R8.8** - **```rndt/metadata/2.0/req/grid-data/transformation-parameter-availability```**

Devono essere fornite informazioni sulla disponibilità dei coefficienti della trasformazione affine attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/*/gmd:transformationParameterAvailability/gco:Boolean```_. Il valore &quot;_true_&quot; significa che sono disponibili i coefficienti della trasformazione, &quot;_false_&quot; il caso contrario.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_ Georectified> [oppure <gmd:MD_Georeferenceable>]
    …
      <gmd:transformationParameterAvailability>
        <gco:Boolean>true</gco:Boolean>
      </gmd:transformationParameterAvailability>
    …
    </gmd:MD_ Georectified> [oppure <gmd:MD_Georeferenceable>]
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```
---

> In caso di dati raster georettificati, vai a [**5.3 Rappresentazione spaziale dei dati raster georettificati**](georectified.md)

> Altrimenti, vai a [**5.4 Rappresentazione spaziale dei dati raster "georeferenziabili"**](georeferenceable.md)
