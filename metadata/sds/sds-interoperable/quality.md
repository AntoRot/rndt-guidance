### 4.4.3 Informazioni sulla qualità dei servizi

#### 4.4.3.1 Qualità del servizio

|  |  |
| --- | --- |
| **Nome elemento** | Qualità del servizio |
| **Riferimento** | [LG RNDT] – tab. VI-2, tab. VI-3 |
| **Molteplicità** | [3..N] |
| **Elemento INSPIRE** | Qualità del servizio |
| **Definizione** | Qualità minima del servizio stimata dalla parte responsabile del servizio di dati territoriali e che dovrebbe essere valida per un periodo di tempo. |
| **Istruzioni di implementazione** | Per ciascun criterio (disponibilità, prestazione, capacità): - **Nome della misura** [1] – L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici _Criteri_ al § 4.2.5.3 delle [LG RNDT]; - **Unità di misura** [1] - utilizzare l&#39;unità di misura pertinente come riportato al § [A.3](#_A.3_Criteri_di) dell&#39;allegato A; - **Valore** [1] – testo libero. |

**REQUISITO 6.5** - **```metadata/2.0/req/sds-interoperable/quality-of-service```**

Devono essere indicati i valori minimi di ciascuno dei criteri di qualità del servizio di cui al paragrafo 4.2.5.3 delle [LG RNDT] (riportati anche al § [A.3](#_A.3_Criteri_di) dell&#39;allegato A) attraverso l&#39;elemento _```gmd:report/gmd:DQ_ConceptualConsistency```_.

Il valore di _```gmd:DQ_ConceptualConsistency/gmd:nameOfMeasure```_ deve essere un elemento _```gmx:Anchor```_ con riferimento al valore dell&#39;elenco di codici _QualityOfServiceCriteriaCode_ pubblicato nel Sistema di Registri INSPIRE e con l&#39;espressione del nome del criterio in italiano.

La descrizione della misura del criterio deve essere riportata attraverso l&#39;elemento _```gmd:DQ_ConceptualConsistency/gmd:measureDescription```_.

Il valore della misura del criterio deve essere riportato attraverso l&#39;elemento _```gmd:DQ_ConceptualConsistency/gmd:result/gmd:DQ_QuantitativeResult```_ con le seguenti informazioni:

- l&#39;unità di misura del criterio, come indicata al § [A.3](#_A.3_Criteri_di) dell&#39;allegato A, attraverso l&#39;elemento _```gmd:valueUnit```_;

- il valore numerico del criterio attraverso l&#39;elemento _```gmd:value/gco:Record```_.

Il tipo di valore deve essere dichiarato attraverso l&#39;attributo _```xsi:type```_ dell&#39;elemento _```gco:Record```_ come indicato al § [A.3](#_A.3_Criteri_di) dell&#39;allegato A.

---

**Esempio di XML:**
