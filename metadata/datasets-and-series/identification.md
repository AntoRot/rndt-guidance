## 3.2 Identificazione dei dati

**Elementi:**

[3.2.1 Formato di presentazione](#321-formato-di-presentazione)

[3.2.2 ID livello superiore](#322-id-livello-superiore)

[3.2.3 Altri dettagli](323-altri-dettagli)

[3.2.4 Parole chiave](324-parole-chiave)

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

#### 3.2.4.2 Parole chiave per i dataset prioritari

La Commissione Europea e l&#39;Agenzia Europea dell&#39;Ambiente hanno individuato, nell&#39;ambito di INSPIRE, un elenco di dataset prodotti e gestiti in funzione degli obblighi di reportistica ambientale stabiliti da diverse Direttive europee. Tali dataset sono definiti come &quot;_dataset prioritari_&quot; che gli Stati Membri devono rendere prioritariamente disponibili attraverso i servizi di rete, armonizzandoli, sulla base delle specifiche tecniche sui dati, secondo la relativa _roadmap_.

Gli obblighi di cui sopra sono stati raggruppati in 6 domini tematici:

- Aria e Rumore;
- Industria;
- Rifiuti;
- Natura e biodiversità;
- Acqua;
- Mare.

Le Direttive da considerare per ciascuno dei domini tematici sono riportate nel documento disponibile al link [https://ies-svn.jrc.ec.europa.eu/attachments/download/2469/eReporting\_PriorityDataList\_V2.0.pdf](https://ies-svn.jrc.ec.europa.eu/attachments/download/2469/eReporting_PriorityDataList_V2.0.pdf).

Per identificare i dataset di cui sopra, è richiesto che sia aggiunta una o più opportune parole chiave con relativo thesaurus.

**Requisito R1.2** - **```rndt/metadata/2.0/req/datasets-and-series/priority-ds-keyword```**

Se il dataset o la serie di dataset è un dataset prioritario, cioè prodotto e gestito in funzione degli obblighi di reportistica ambientale stabiliti dalle Direttive europee, ciò deve essere dichiarato utilizzando almeno una parola chiave dal registro _[INSPIRE priority data set](http://inspire.ec.europa.eu/metadata-codelist/PriorityDataset)_ pubblicato nel Sistema di Registri di INSPIRE. I valori delle parole chiave devono corrispondere esattamente ai termini presenti nel registro citato, nella lingua dei metadati, se disponibile nel registro stesso.

Le parole chiave devono essere codificate utilizzando l&#39;elemento _gmd:descriptiveKeywords/gmd:MD\_Keywords_ con riferimento al registro citato secondo le indicazioni fornite nel paragrafo [2.3.6](#_Parole_chiave).

L&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:title```_ deve contenere il valore &quot;_INSPIRE priority data set_&quot;. La data di pubblicazione del registro da utilizzare nell&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:date/gmd:CI_Date/gmd:date/gco:Date```_ è &quot;_2018-04-04_&quot;. L&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:date/gmd:CI_Date/gmd:dateType/gmd:CI_DateTypeCode```_ deve avere il valore &quot;_pubblicazione_&quot; (_publication_) presente nell&#39;elenco di codici ISO _```CI_DateTypeCode```_.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword>
            <gco:CharacterString>Agglomerations (Noise Directive)</gco:CharacterString>
          </gmd:keyword>
          <gmd:thesaurusName>
            <gmd:CI_Citation>
              <gmd:title>
                <gco:CharacterString>INSPIRE priority data set</gco:CharacterString>
              </gmd:title>
              <gmd:date>
                <gmd:CI_Date>
                  <gmd:date>
                    <gco:Date>2018-04-04</gco:Date>
                  </gmd:date>
                  <gmd:dateType>
                    <gmd:CI_DateTypeCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode" codeListValue="publication">pubblicazione</gmd:CI_DateTypeCode>
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

#### 3.2.4.3 Parole chiave per l&#39;ambito di applicazione territoriale

La Decisione di esecuzione (UE) 2019/1372 della Commissione, che ha sostituito la Decisione 2009/442/CE, ha modificato le disposizioni per il monitoraggio e la comunicazione relativi all&#39;attuazione della Direttiva INSPIRE. In particolare, sono stati aggiunti due nuovi indicatori per misurare il numero di dataset che coprono il territorio regionale o nazionale.

Per identificare i dataset di cui sopra, è richiesto che sia aggiunta una o più opportune parole chiave con relativo thesaurus.

<a name=R1.3>**REQUISITO R1.3**</a> - **```rndt/metadata/2.0/req/datasets-and-series/spatial-scope```**

Se il dataset o la serie di dataset è riferito ad un ambito di applicazione territoriale regionale o nazionale deve essere dichiarato utilizzando una parola chiave dall&#39;elenco di codici _[Spatial scope](http://inspire.ec.europa.eu/metadata-codelist/SpatialScope)_ pubblicato nel registro _INSPIRE metadata code list register_ del Sistema di Registri di INSPIRE. I valori delle parole chiave devono corrispondere esattamente ai termini presenti nel registro citato, nella lingua dei metadati.

Le parole chiave devono essere codificate utilizzando l&#39;elemento _```gmd:descriptiveKeywords/gmd:MD_Keywords```_ con riferimento al registro citato secondo le indicazioni fornite nel paragrafo 2.3.6.

L&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:title```_ deve contenere il valore &quot;_Spatial scope_&quot;. La data di pubblicazione del registro da utilizzare nell&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:date/gmd:CI_Date/gmd:date/gco:Date```_ è &quot;_2019-05-22_&quot;. L&#39;elemento _```gmd:thesaurusName/gmd:CI_Citation/gmd:date/gmd:CI_Date/gmd:dateType/gmd:CI_DateTypeCode```_ deve avere il valore &quot;_pubblicazione_&quot; (_publication_) presente nell&#39;elenco di codici ISO _```CI_DateTypeCode```_.

---

***Raccomandazione R1.4** - **```rndt/metadata/2.0/rec/datasets-and-series/spatial-scope```***

*Se l&#39;ambito di applicazione territoriale di riferimento per il dataset o la serie di dataset è diverso da &#39;regionale&#39; o &#39;nazionale&#39;, si raccomanda di utilizzare comunque una parola chiave pertinente dall&#39;elenco di codici _[Spatial scope](http://inspire.ec.europa.eu/metadata-codelist/SpatialScope)_ pubblicato nel registro _INSPIRE metadata code list register_ del Sistema di Registri di INSPIRE, secondo le indicazioni del Requisito [R1.3](#R1.3).*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword>
            <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialScope/regional">Regionale</gmx:Anchor>
          </gmd:keyword>
          <gmd:thesaurusName>
            <gmd:CI_Citation>
              <gmd:title>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialScope">Spatial scope</gmx:Anchor>
              </gmd:title>
              <gmd:date>
                <gmd:CI_Date>
                  <gmd:date>
                    <gco:Date>2019-05-22</gco:Date>
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

#### 3.2.4.4 Parole chiave per i dati aperti

Nell&#39;ambito delle attività di coordinamento tra RNDT e il portale nazionale degli open data, AgID ha definito le **[linee guida per l&#39;implementazione della specifica europea GeoDCAT-AP](http://geodati.gov.it/geoportale/documenti/12-documenti/277-linee-guida-nazionali-geodcat-ap)** che consentono di rappresentare i metadati dei dati geografici anche negli standard utilizzati per i dati aperti, nello specifico DCAT-AP/DCAT-AP\_IT.

Anche allo scopo di limitare l&#39;onere delle PA di documentare dati geografici che sono anche dati aperti in entrambi i cataloghi, tali dati, come previsto dalle citate linee guida, vanno documentati solo nel RNDT che provvederà a rendere disponibili i relativi metadati anche in _dati.gov.it_.

Per i dati aperti, è richiesto di indicare una opportuna licenza attraverso i [metadati relativi alle condizioni d&#39;uso](../common/constraints.md#243-vincoli-di-fruibilità).

In aggiunta a ciò, per poter individuare i dati aperti nell&#39;ambito di tutte le risorse documentate nel RNDT, deve essere aggiunta una specifica parola chiave.

**Requisito R1.4** - **```rndt/metadata/2.0/req/datasets-and-series/open-data```**

Se il dataset o la serie di dataset è anche di tipo aperto deve essere dichiarato utilizzando le parole chiave &quot;_open data_&quot; o &quot;_opendata_&quot;.

Le parole chiave devono essere codificate utilizzando l&#39;elemento _```gmd:descriptiveKeywords/gmd:MD_Keywords/gmd:keyword```_.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword>
            <gco:CharacterString>open data</gco:CharacterString>
          </gmd:keyword>
        </gmd:MD_Keywords>
      </gmd:descriptiveKeywords>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```
