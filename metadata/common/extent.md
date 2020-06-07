## 2.5 Estensione dei dati

**Elementi:**

[2.5.1 Localizzazione geografica](extent.md#251-localizzazione-geografica)

[2.5.2 Estensione temporale](extent.md#252-estensione-temporale)

### 2.5.1 Localizzazione geografica

|  |  |
| --- | --- |
| **Nome elemento** | Localizzazione geografica |
| **Riferimento** | [LG RNDT] – tab. I-30, tab. V-26, tab. VII-16 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Riquadro di delimitazione geografica |
| **Definizione** | Estensione della risorsa nello spazio geografico fornita sotto forma di un riquadro di delimitazione. |
| **Istruzioni di implementazione** | - **Longitudine ovest** [1] - Utilizzare il tipo _gco:Decimal_; - **Longitudine est** [1] - Utilizzare il tipo _gco:Decimal_; - **Latitudine sud** [1] - Utilizzare il tipo _gco:Decimal_; - **Latitudine nord** [1] - Utilizzare il tipo _gco:Decimal_ |

**REQUISITO C.19** - **```metadata/2.0/req/common/bounding-box```**

Deve essere indicato il più piccolo riquadro di delimitazione geografica (bounding box) che copre il dataset o la serie di dataset attraverso l&#39;elemento _```gmd:extent/gmd:EX_Extent/gmd:geographicElement/gmd:EX_GeographicBoundingBox```_.

La molteplicità di questo elemento è 1.

Le coordinate della longitudine est e ovest e della latitudine nord e sud devono essere espresse in gradi decimali con una precisione di almeno due cifre decimali nel sistema di riferimento WGS84.

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
          <gmd:geographicElement>
            <gmd:EX_GeographicBoundingBox>
              <gmd:westBoundLongitude>
                <gco:Decimal>14.34879</gco:Decimal>
              </gmd:westBoundLongitude>
              <gmd:eastBoundLongitude>
                <gco:Decimal>15.14967</gco:Decimal>
              </gmd:eastBoundLongitude>
              <gmd:southBoundLatitude>
                <gco:Decimal>40.973</gco:Decimal>
              </gmd:southBoundLatitude>
              <gmd:northBoundLatitude>
                <gco:Decimal>41.48564</gco:Decimal>
              </gmd:northBoundLatitude>
            </gmd:EX_GeographicBoundingBox>
          </gmd:geographicElement>
        </gmd:EX_Extent>
      </gmd:extent>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

### Estensione temporale

|  |  |
| --- | --- |
| **Nome elemento** | Estensione temporale |
| **Riferimento** | [LG RNDT] – tab. I-31, tab. V-27 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Estensione temporale |
| **Definizione** | Periodo di tempo coperto dal contenuto della risorsa. |
| **Istruzioni di implementazione** | - **Data inizio** [1] - formato ISO 8601 (aaaa-mm-gg); - **Data fine** [1] - formato ISO 8601 (aaaa-mm-gg) |

**REQUISITO C.14** - **```metadata/2.0/req/common/temporal-extent```**

Se, oltre alla data (v. paragrafo 2.3.2), il riferimento temporale viene fornito anche con l&#39;_estensione temporale_, deve essere utilizzato l&#39;elemento _```gmd:temporalElement/gmd:EX_TemporalExtent/gmd:extent```_.

La molteplicità dell&#39;elemento è 0..N.

L&#39;estensione temporale dovrà essere documentata attraverso l&#39;elemento _```gml:TimePeriod```_ che deve contenere le date di inizio e di fine di un intervallo temporale. Nel caso in cui una delle date sia sconosciuta, i tag relativi all&#39;elemento _```gml:beginPosition```_ o _```gml:endPosition```_ può essere lasciato vuoto e può essere utilizzato l&#39;attributo _```indeterminatePosition```_ con il valore &quot;_unknown_&quot;. Se, invece, l&#39;intervallo temporale è in corso, allora il tag relativo all&#39;elemento _```gml:beginPosition```_ o _```gml:endPosition```_ può essere lasciato vuoto e può essere utilizzato l&#39;attributo _```indeterminatePosition```_ con il valore &quot;_now_&quot;.

Più intervalli temporali possono essere combinati per formare un&#39;estensione temporale complessa utilizzando più elementi _```gmd:temporalElement/gmd:EX_TemporalExtent/gmd:extent```_.

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
          <gmd:temporalElement>
            <gmd:EX_TemporalExtent>
              <gmd:extent>
                <gml:TimePeriod gml:id="TP1">
                  <gml:beginPosition>2005-12-04</gml:beginPosition>
                  <gml:endPosition>2007-01-30</gml:endPosition>
                </gml:TimePeriod>
              </gmd:extent>
            </gmd:EX_TemporalExtent>
          </gmd:temporalElement>
          …
        </gmd:EX_Extent>
      </gmd:extent>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```
