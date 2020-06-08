## 3.2 Identificazione dei dati

**Elementi:**

3.2.1 Formato di presentazione

3.2.2 ID livello superiore

3.2.3 Altri dettagli

3.2.4 Parole chiave

3.2.5 Set di caratteri

3.2.6 Tipo di rappresentazione spaziale

3.2.7 Risoluzione spaziale

3.2.8 Lingua

3.2.9 Categoria tematica

3.2.10 Informazioni supplementari


**REQUISITO 1.2** - **```metadata/2.0/req/datasets-and-series/only-one-md-data-identification```**

La prima proprietà _```gmd:identificationInfo```_ dell&#39;elemento _```gmd:MD_Metadata```_ deve contenere solo un elemento _```gmd:MD_DataIdentification```_ per identificare il dataset o la serie di dataset descritto.

---

***Raccomandazione 1.1** - **```metadata/2.0/rec/datasets-and-series/md-element-id```***

*L&#39;elemento ```gmd:MD_DataIdentification``` dovrebbe contenere un identificatore univoco dell&#39;elemento stesso per poter essere utilizzato come riferimento all&#39;interno dei metadati dei servizi per indicare la risorsa accoppiata.*

*Questo identificatore dovrebbe essere fornito come valore dell&#39;attributo ```id``` dell&#39;elemento ```gmd:MD_DataIdentification```.*

*Esso dovrebbe essere persistente per un particolare dataset o servizio e univoco fra tutti gli attributi id utilizzati nel documento di metadati e in altri documenti XML in cui potrebbe apparire (come nelle risposte GetRecords di un servizio di ricerca). La persistenza degli attributi id è importante per impedire l&#39;interruzione dei collegamenti della risorsa accoppiata tra i metadati del servizio e i metadati del dataset.*


### 3.2.1 Formato di presentazione

|  |  |
| --- | --- |
| **Nome elemento** | Formato di presentazione |
| **Riferimento** | [LG RNDT] – tab. I-12 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Modalità in cui la risorsa è rappresentata. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_PresentationFormCode_&quot; (§ 4.2.3.4 [LG RNDT]). |

***Raccomandazione R1.2** - **```rndt/metadata/2.0/rec/datasets-and-series/presentation-form```***

*Per documentare il formato di presentazione del dataset o della serie di dataset può essere utilizzato l&#39;elemento ```gmd:citation/gmd:CI\_Citation/gmd:presentationForm``` con un valore dell&#39;elenco di codici ISO ```CI_PresentationFormCode```.*

*La molteplicità dell&#39;elemento è 0..N.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
      <gmd:citation>
        <gmd:CI_Citation>
        …
          <gmd:presentationForm>
            <gmd:CI_PresentationFromCode codeListValue="mapDigital" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_PresentationFormCode">mappa digitale</gmd:CI_PresentationFormCode>
          </gmd:presentationForm>
          …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

### 3.2.2 ID livello superiore

|  |  |
| --- | --- |
| **Nome elemento** | ID livello superiore |
| **Riferimento** | [LG RNDT] – tab. I-15 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Riferimento univoco relativo alla serie di cui il dataset è parte. |
| **Istruzioni di implementazione** | Testo libero. Per quanto riguarda il formato, vale quanto indicato al § 2.3.4. |

**REQUISITO R1.1** - **```rndt/metadata/2.0/req/datasets-and-series/series```**

L&#39;elemento deve essere utilizzato per gestire le relazioni tra i livelli gerarchici. Per il dataset, esso assume il valore dell&#39;elemento &quot;[Identificatore](../common/identification.md#234-identificatore)&quot; della serie a cui il dataset è relazionato. Nel caso di serie o dataset &quot;flat&quot;, per cui non esiste un livello gerarchico di rango superiore, l&#39;elemento deve assumere il valore dell&#39;elemento &quot;[Identificatore](../common/identification.md#234-identificatore)&quot; del livello corrente.

L&#39;ID di livello superiore deve essere documentato attraverso l&#39;elemento _```gmd:citation/gmd:CI_Citation/gmd:series/gmd:CI_Series/gmd:issueIdentification```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
      <gmd:citation>
        <gmd:CI_Citation>
        …
          <gmd:series>
            <gmd:CI_Series>
              <gmd:issueIdentification>
                <gco:CharacterString>https://geodati.gov.it/resource/id/r_piemon:00000001</gco:CharacterString>
              </gmd:issueIdentification>
            </gmd:CI_Series>
          </gmd:series>
          …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
    …
 </gmd:MD_Metadata>
```
