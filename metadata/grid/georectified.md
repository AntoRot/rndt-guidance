## 5.3 Rappresentazione spaziale dei dati raster georettificati

**Elementi:**

[5.3.1 Disponibilità dei check-points](#531-disponibilità-dei-check-points)

[5.3.2 Descrizione check-points](#532-descrizione-check-points)

[5.3.3 Coordinate dei vertici](#533-coordinate-dei-vertici)

[5.3.4 Punto del pixel](#534-punto-del-pixel)


### 5.3.1 Disponibilità dei check-points

|  |  |
| --- | --- |
| **Nome elemento** | Disponibilità dei check-points |
| **Riferimento** | [LG RNDT] – tab. III-1 |
| **Molteplicità** | [1] |
| **Definizione** | Indicazione sulla disponibilità dei check-points. |
| **Istruzioni di implementazione** | Tipo dato booleano. |

**REQUISITO R8.9** - **```rndt/metadata/2.0/req/grid-data/check-point-availability```**

Per i dati georettificati, devono essere fornite informazioni sulla disponibilità dei check point attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georectified/gmd:checkPointAvailability/gco:Boolean```_. Il valore &quot;_true_&quot; significa che sono disponibili i check-points, &quot;_false_&quot; il caso contrario.

La molteplicità di questo elemento è 1.+

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_ Georectified>
    …
      <gmd:checkPointAvailability>
        <gco:Boolean>false</gco:Boolean>
      </gmd:checkPointAvailability>
      …
    </gmd:MD_ Georectified>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.3.2 Descrizione check-points

|  |  |
| --- | --- |
| **Nome elemento** | Descrizione check-points |
| **Riferimento** | [LG RNDT] – tab. III-2 |
| **Molteplicità** | [0..1] |
| **Definizione** | Breve descrizione dei check-points disponibili. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO R8.10** - **```rndt/metadata/2.0/req/grid-data/check-point-description```**

Per i dati georettificati, se si è dichiarata la disponibilità dei check point come da Requisito [R8.9](#reqR89), deve essere fornita una descrizione testuale dei check point stessi attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georectified/gmd:checkPointDescription```_.

La molteplicità di questo elemento è 0..1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_ Georectified>
    …
      <gmd:checkPointDescription>
        <gco:CharacterString>I Check Points hanno le medesime caratteristiche dei GCP relativamente a distribuzione e posizionamento; la loro dislocazione è complementare a quella dei GCP ...</ gco:CharacterString >
      </gmd:checkPointDescription>
      …
    </gmd:MD_ Georectified>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.3.3 Coordinate dei vertici

|  |  |
| --- | --- |
| **Nome elemento** | Coordinate dei vertici |
| **Riferimento** | [LG RNDT] – tab. III-3 |
| **Molteplicità** | [1..\*] |
| **Definizione** | Coordinate dei vertici della griglia espresse nel proprio sistema di riferimento spaziale. Sono richiesti almeno il vertice origine della griglia e quello opposto lungo la diagonale. |
| **Istruzioni di implementazione** | Per ogni punto indicare la coppia delle coordinate. |

**REQUISITO R8.11** - **```rndt/metadata/2.0/req/grid-data/corner-points```**

Per i dati georettificati, devono essere fornite le informazioni relativamente alle coordinate dei vertici attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georectified/gmd:cornerPoints```_. La molteplicità di questo elemento è 1..N.

Per ogni vertice devono essere indicati i seguenti elementi:

- _```gml:Point/gml:name```_ con l&#39;indicazione del nome del vertice considerato. Sono richiesti almeno il &quot;Vertice alto a sinistra&quot; e il &quot;Vertice basso a destro&quot;. L&#39;attributo _```gml:id```_ dell&#39;elemento _```gml:Point```_ deve essere obbligatoriamente presente e deve essere univoco nel file. La molteplicità di questo elemento è 0..1;

- _```gml:Point/gml:coordinates```_ con l&#39;indicazione della coppia di coordinate del vertice considerato. L&#39;elemento include gli attributi decimal per l&#39;indicazione del segno separatore dei decimali (valore di default&quot; **.**&quot;) e cs per l&#39;indicazione del segno separatore delle due coordinate (valore di default &quot; **,**&quot;). La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_ Georectified>
    …
      <gmd:cornerPoints>
        <gml:Point gml:id="PNT_1">
          <gml:name>Vertice alto a sinistra</gml:name>
          <gml:coordinates decimal="." cs=",">1510560,4910680</gml:coordinates>
        </gml:Point>
      </gmd:cornerPoints>
      <gmd:cornerPoints>
        <gml:Point gml:id="PNT_2">
          <gml:name>Vertice basso a destra</gml:name>
          <gml:coordinates decimal="." cs=",">1518560,4905040</gml:coordinates>
        </gml:Point>
      </gmd:cornerPoints>
    …
    </gmd:MD_ Georectified>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```

### 5.3.4 Punto del pixel

|  |  |
| --- | --- |
| **Nome elemento** | Punto del pixel |
| **Riferimento** | [LG RNDT] – tab. III-4 |
| **Molteplicità** | [1] |
| **Definizione** | Punto del pixel a cui si riferiscono le coordinate. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_PixelOrientationCode_&quot; (§ 4.2.3.1 [LG RNDT]). |

**REQUISITO R8.12** - **```rndt/metadata/2.0/req/grid-data/point-in-pixel```**

Per i dati georettificati, deve essere indicato il punto del pixel di base a cui si riferiscono le coordinate attraverso l&#39;elemento _```gmd:spatialRepresentationInfo/gmd:MD_Georectified/gmd:pointInPixel/gmd:MD_PixelOrientationCode```_ con riferimento a uno dei valori dell&#39;enumerazione ISO _```MD_PixelOrientationCode```_.

La molteplicità di questo elemento è 1.

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:spatialRepresentationInfo>
    <gmd:MD_ Georectified>
    …
      <gmd:pointInPixel>
        <gmd:MD_PixelOrientationCode>upperLeft</gmd:MD_PixelOrientationCode>
      </gmd:pointInPixel>
    …
    </gmd:MD_ Georectified>
  </gmd:spatialRepresentationInfo>
  …
</gmd:MD_Metadata>
```
