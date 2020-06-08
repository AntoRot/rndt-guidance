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


### 3.2.3 Altri dettagli

|  |  |
| --- | --- |
| **Nome elemento** | Altri dettagli |
| **Riferimento** | [LG RNDT] – tab. I-16 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Ulteriori informazioni di citazione. |
| **Istruzioni di implementazione** | Testo libero. |

**Raccomandazione R1.3** - **```rndt/metadata/2.0/rec/datasets-and-series/other-details```**

*Per fornire ulteriori dettagli sul dataset o sulla serie di dataset, si può utilizzare l&#39;elemento ```gmd:citation/gmd:CI\_Citation/gmd:otherCitationDetails```.*

*Si consiglia di utilizzare questo elemento per indicare, se disponibile, il riferimento, attraverso un URL, alle norme (legge nazionale o regionale, delibera, atto amministrativo, …) relative alla produzione e/o trattamento dei dati.*

*La molteplicità di questo elemento è 0..1.*

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
          <gmd:otherCitationDetails>
            <gco:CharacterString>http://www.regione.emilia-romagna.it/temi/territorio/cartografia-regionale/vedi-anche/database-topografico-regionale/le-norme-e-gli-atti-in-vigore/atto-di-indirizzo-e-coordinamento-tecnico-per/at_download/file</gco:CharacterString>
          </gmd:otherCitationDetails>
          …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

### 3.2.4 Parole chiave

|  |  |
| --- | --- |
| **Nome elemento** | Parole chiave |
| **Riferimento** | [LG RNDT] – tab. I-18 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Parola chiave (Valore della parola chiave – Vocabolario controllato di origine) |
| **Definizione** | Parola formalizzata o utilizzata comunemente per descrivere la risorsa. |
| **Istruzioni di implementazione** | - **Parola chiave** [1..\*] - Testo libero; - **Thesaurus** [0..1] : - **Titolo** [1]– Testo libero; - **Data** [1..\*] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_ oppure _aaaammgg_; - **Tipo data** [1..\*] - L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]). |

#### 3.2.4.1 Parole chiave per le categorie tematiche INSPIRE

**REQUISITO 1.4** - **```metadata/2.0/req/datasets-and-series/inspire-theme-keyword```**

Le categorie tematiche INSPIRE, a cui il dataset o la serie di dataset appartengono, devono essere dichiarate utilizzando almeno una parola chiave dal vocabolario _INSPIRE Spatial Data Themes_ del GEMET. I valori delle parole chiave devono corrispondere esattamente ai termini presenti nel vocabolario citato.

Le parole chiave devono essere codificate utilizzando l&#39;elemento _```gmd:descriptiveKeywords/gmd:MD_Keywords```_ con riferimento al vocabolario controllato GEMET dei temi di INSPIRE secondo le indicazioni fornite nel paragrafo [2.3.6](#_Parole_chiave). L&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:title```_ deve contenere il valore &quot;_GEMET - INSPIRE themes, version 1.0_&quot;.

Per ogni categoria tematica INSPIRE, deve essere incluso un elemento _```gmd:keyword```_ con il nome della categoria tematica nella lingua dei metadati.

---

***Raccomandazione 1.4** - **```metadata/2.0/rec/datasets-and-series/use-anchors-for-gemet```***

*Per il riferimento al vocabolario controllato GEMET delle categorie tematiche di INSPIRE, il titolo può essere codificato attraverso l&#39;elemento ```gmd:thesaurusName/gmd:CI_Citation/gmd:title/gmx:Anchor``` con l&#39;attributo ```xlink:href``` che fa riferimento a [http://www.eionet.europa.eu/gemet/inspire\_themes](http://www.eionet.europa.eu/gemet/inspire_themes).

Le parole chiave delle categorie tematiche INSPIRE devono essere codificate attraverso l&#39;elemento ```gmd:keyword/gmx:Anchor```, con l&#39;attributo ```xlink:href``` riferito all&#39;URI della categoria tematica definito nel vocabolario controllato GEMET - INSPIRE.

---

***Raccomandazione 1.5** - **```metadata/2.0/rec/datasets-and-series/additional-keywords```***

*Si raccomanda di inserire almeno altre due parole chiave in aggiunta a quelle tratte dal vocabolario delle categorie tematiche GEMET - INSPIRE.*

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword>
            <gco:CharacterString>Orto immagini</gco:CharacterString>
          </gmd:keyword>
          <gmd:thesaurusName>
            <gmd:CI_Citation>
              <gmd:title>
                <gco:CharacterString>GEMET - INSPIRE themes, version 1.0</gco:CharacterString>
              </gmd:title>
              <gmd:date>
                <gmd:CI_Date>
                  <gmd:date>
                    <gco:Date>2008-06-01</gco:Date>
                  </gmd:date>
                  <gmd:dateType>
                    <gmd:CI_DateTypeCode codeListValue="publication" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode">pubblicazione</gmd:CI_DateTypeCode>
                  </gmd:dateType>
                </gmd:CI_Date>
              </gmd:date>
             </gmd:CI_Citation>
          </gmd:thesaurusName>
        </gmd:MD_Keywords>
      </gmd:descriptiveKeywords>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword>
            <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/theme/lu">Utilizzo del territorio</gmx:Anchor>
          </gmd:keyword>
          <gmd:keyword>
            <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/theme/bu">Edifici</gmx:Anchor>
          </gmd:keyword>
          <gmd:thesaurusName>
            <gmd:CI_Citation>
              <gmd:title>
                <gmx:Anchor xlink:href="http://www.eionet.europa.eu/gemet/inspire_themes">GEMET - INSPIRE themes, version 1.0</gmx:Anchor>
              </gmd:title>
              <gmd:date>
                <gmd:CI_Date>
                  <gmd:date>
                    <gco:Date>2008-06-01</gco:Date>
                  </gmd:date>
                  <gmd:dateType>
                    <gmd:CI_DateTypeCode codeListValue="publication" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode">pubblicazione</gmd:CI_DateTypeCode>
                  </gmd:dateType>
                </gmd:CI_Date>
              </gmd:date>
            </gmd:CI_Citation>
          </gmd:thesaurusName>
        </gmd:MD_Keywords>
      </gmd:descriptiveKeywords>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
