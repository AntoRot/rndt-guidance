## 5.4 Rappresentazione spaziale dei dati raster &quot;georeferenziabili&quot;

**Elementi:**

[5.4.1 Disponibilità dei punti di controllo](#541-disponibilità-dei-punti-di-controllo)

[5.4.2 Disponibilità dei parametri di orientamento](#542-disponibilità-dei-parametri-di-orientamento)

[5.4.3 Parametri per la georeferenziazione](#543-parametri-per-la-georeferenziazione)


### 5.4.1 Disponibilità dei punti di controllo

|  |  |
| --- | --- |
| **Nome elemento** | Disponibilità dei punti di controllo |
| **Riferimento** | [LG RNDT] – tab. IV-1 |
| **Molteplicità** | [1] |
| **Definizione** | Indicazione se esistono o meno punti di controllo. |
| **Istruzioni di implementazione** | Tipo dato booleano. |

**REQUISITO R8.13** - **```rndt/metadata/2.0/req/grid-data/control-point-availability```**

Per i dati &quot;georeferenziabili&quot;, devono essere fornite le informazioni sulla disponibilità di punti di controllo attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georeferenceable/gmd:controlPointAvailability/gco:Boolean```_. Il valore &quot;_true_&quot; significa che sono disponibili i punti di controllo, &quot;_false_&quot; il caso contrario.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_Georeferenceable>
    …
      <gmd:controlPointAvailability>
        <gco:Boolean>true</gco:Boolean >
      </gmd:controlPointAvailability>
    …
    </gmd:MD_Georeferenceable>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.4.2 Disponibilità dei parametri di orientamento

|  |  |
| --- | --- |
| **Nome elemento** | Disponibilità dei parametri di orientamento |
| **Riferimento** | [LG RNDT] – tab. IV-2 |
| **Molteplicità** | [1] |
| **Definizione** | Indicazione se sono disponibili o meno i parametri di orientamento. |
| **Istruzioni di implementazione** | Tipo dato booleano. |

**REQUISITO R8.14** - **```rndt/metadata/2.0/req/grid-data/orientation-parameter-availability```**

Per i dati &quot;_georeferenziabili_&quot;, devono essere fornite le informazioni sulla disponibilità dei parametri di orientamento attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georeferenceable/gmd:orientationParameterAvailability/gco:Boolean```_. Il valore &quot;_true_&quot; significa che sono disponibili i parametri di orientamento, &quot;_false_&quot; il caso contrario.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_Georeferenceable>
    …
      <gmd:orientationParameterAvailability>
        <gco:Boolean>false</gco:Boolean>
      </gmd:orientationParameterAvailability>
    …
    </gmd:MD_Georeferenceable>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.4.3 Parametri per la georeferenziazione

|  |  |
| --- | --- |
| **Nome elemento** | Parametri per la georeferenziazione |
| **Riferimento** | [LG RNDT] – tab. IV-3 |
| **Molteplicità** | [1] |
| **Definizione** | Termini che supportano la georeferenziazione dei dati. |
| **Istruzioni di implementazione** | Indicare i coefficienti per la georeferenziazione. |

**REQUISITO R8.15** - **```rndt/metadata/2.0/req/grid-data/georeferenced-parameters```**

Per i dati &quot;_georeferenziabili_&quot;, devono essere indicati i parametri utili per la georeferenziazione attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georeferenceable/gmd:georeferencedParameters/gco:Record```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_Georeferenceable>
    …
      <gmd:georeferencedParameters>
        <gco:Record>2.4384 0.0000 0.0000 -2.4384 441794.4342 5094101.4520</gco:Record>
      </gmd:georeferencedParameters>
    …
    </gmd:MD_Georeferenceable>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```
