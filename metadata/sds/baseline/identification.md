### 4.1.2 Identificazione dei servizi

**Elementi:**

[4.1.2.1 Parole chiave](#4121-parole-chiave)

[4.1.2.2 Tipo di servizio](#4122-tipo-di-servizio)

[4.1.2.3 Tipo di aggancio](#4123-tipo-di-aggancio)

[4.1.2.4 Risorsa accoppiata](#4124-risorsa-accoppiata)

[4.1.2.5 Operazioni](#4125-operazioni)


#### 4.1.2.1 Parole chiave

|  |  |
| --- | --- |
| **Nome elemento** | Parole chiave |
| **Riferimento** | [LG RNDT] – tab. V-15 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Parola chiave (Valore della parola chiave – Vocabolario controllato di origine) |
| **Definizione** | Parola formalizzata o utilizzata comunemente per descrivere la risorsa. |
| **Istruzioni di implementazione** | - **Parola chiave** [1..\*] - Testo libero; - **Thesaurus** [0..1] : - **Titolo** [1]– Testo libero;   - **Data** [1..\*] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1..\*] **-** L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]); |

**REQUISITO 3.4** - **```metadata/2.0/req/sds/sds-category```**

Deve essere indicata almeno una categoria o sottocategoria per il servizio utilizzando i valori linguisticamente neutri delle parole chiave definiti nella Parte D 4 &quot;_Classificazione dei servizi di dati territoriali_&quot; del [Regolamento 1205/2008].

---

***Raccomandazione 3.2** - **```metadata/2.0/rec/sds/sds-category-cv```***

*Per rendere chiaro il riferimento ai valori delle parole chiave della Parte D 4 del Regolamento 1205/2008/CE, queste parole chiave dovrebbero essere espresse come parole chiave derivanti da un vocabolario controllato utilizzando l&#39;elemento _gmx:Anchor_ con riferimento all&#39;elenco di codici [```Classificazione dei servizi di dati territoriali```](http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory) pubblicato nel Sistema di Registri INSPIRE. A tale scopo deve essere aggiunto l&#39;elemento ```gmd:MD_Keywords/gmd:thesaurusName``` contenente la citazione della Parte D 4 del Regolamento 1205/2008/CE e la relativa data di pubblicazione secondo quanto indicato al paragrafo [2.3.6](../common/identification.md#236-parole-chiave).*

---

***Raccomandazione 3.3**  **```metadata/2.0/rec/sds/additional-keywords```***

*Si consiglia di inserire almeno due parole chiave in aggiunta a quelle obbligatorie corrispondenti alla categoria e sottocategoria di cui alla classificazione dei servizi di dati territoriali.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword> <gco:CharacterString>infoCatalogueService</gco:CharacterString>
        </gmd:keyword>
        <gmd:keyword>
          <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory/humanCatalogueViewer">humanCatalogViewer</ gmx:Anchor>
        </gmd:keyword>
        <gmd:thesaurusName>
          <gmd:CI_Citation>
            <gmd:title>
              <gco:CharacterString>REGOLAMENTO (CE) N. 1205/2008 DELLA COMMISSIONE del 3 dicembre 2008 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda i metadati</gco:CharacterString>
            </gmd:title>
            <gmd:date>
              <gmd:CI_Date>
                <gmd:date>
                  <gco:Date>2008-12-03</gco:Date>
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
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

#### 4.1.2.2 Tipo di servizio

|  |  |
| --- | --- |
| **Nome elemento** | Tipo di servizio |
| **Riferimento** | [LG RNDT] – tab. V-17 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Tipo di servizio di dati territoriali |
| **Definizione** | Nome del tipo di servizio da un registro di servizi. |
| **Istruzioni di implementazione** | Fare riferimento all&#39;elenco di codici &quot;_ServiceType_&quot; di cui al § 4.2.5.5 [LG RNDT]. |

<a name=3.5>**REQUISITO 3.5**</a> - **```metadata/2.0/req/sds/sds-type```**

Il tipo di servizio di dati territoriali deve essere indicato attraverso l&#39;elemento _```srv:serviceType/gco:LocalName```_.

La molteplicità di questo elemento è 1.

---

***Raccomandazione R3.1** - **```rndt/metadata/2.0/rec/sds/sds-type-codelist```***

*Per rendere chiaro il riferimento all&#39;elenco di codici in cui sono definiti i tipi di servizi, può essere aggiunto l&#39;attributo ```codeSpace``` all&#39;elemento ```srv:serviceType/gco:LocalName``` contenente l&#39;URI dell&#39;[elenco di codici pubblicato nel Sistema di Registri di INSPIRE](http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType).*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <srv:serviceType>
        <gco:LocalName codeSpace="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType">view</gco:LocalName>
      </srv:serviceType>
    …
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

#### 4.1.2.3 Tipo di aggancio

|  |  |
| --- | --- |
| **Nome elemento** | Tipo di aggancio |
| **Riferimento** | [LG RNDT] – tab. V-18 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Tipo di aggancio tra il servizio e i dati associati (se esistono). |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_SV\_CouplingType_&quot; di cui al § 4.2.5.6 [LG RNDT]. |

**REQUISITO R3.1** - **```rndt/metadata/2.0/req/sds/coupling-type```**

Il tipo di aggancio tra il servizio e i dataset associati deve essere indicato attraverso l&#39;elemento _```srv:couplingType/srv: SV_CouplingType```_ facendo riferimento all&#39;elenco di codici _```SV\_CouplingType```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <srv:couplingType>
        <srv:SV_CouplingType codeListValue="loose" codeList="#SVCouplingType">svincolato</srv:SV_CouplingType>
      </srv:couplingType >
    …
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

#### 4.1.2.4 Risorsa accoppiata

|  |  |
| --- | --- |
| **Nome elemento** | Risorsa accoppiata |
| **Riferimento** | [LG RNDT] – tab. V-19 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Risorsa accoppiata |
| **Definizione** | Riferimento univoco (identificatore) del set di dati agganciato dal servizio. |
| **Istruzioni di implementazione** | L&#39;elemento serve ad indicare il link ai dataset sui quali opera il servizio. La documentazione avviene attraverso la valorizzazione dell&#39;attributo &quot;_xlink:href_&quot; come da esempio XML. |

**REQUISITO 3.6** - **```metadata/2.0/req/sds/coupled-resource```**

Devono essere indicati i link ai metadati dei dataset resi disponibili dal servizio attraverso l&#39;elemento _```srv:operatesOn```_.

La molteplicità di questo elemento è 0..N.

L&#39;attributo _```xlink:href```_ dell&#39;elemento _```srv:operatesOn```_ deve contenere un URI che punti all&#39;elemento _```gmd:MD_DataIdentification```_ del record di metadati del dataset o della serie di dataset resi disponibili dal servizio.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <srv:operatesOn xlink:href="https://geodati.gov.it/RNDT/csw?request=GetRecordById&service=CSW&version=2.0.2&id=r_liguri:D.985.2012-10-16&ELEMENTSETNAME=full&OUTPUTSCHEMA=http://www.isotc211.org/2005/gmd"/>
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

#### 4.1.2.5 Operazioni

|  |  |
| --- | --- |
| **Nome elemento** | Operazioni |
| **Riferimento** | [LG RNDT] – tab. V-20 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Informazioni sulle operazioni che compongono il servizio. |
| **Istruzioni di implementazione** | - **Nome operazione** [1] – Testo libero; - **DCP** [1..\*] – L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_DCPList_&quot; di cui al § 3.4.5.3 - all. 2 DM; - **Punto di connessione** [1..\*] – Riferimento per l&#39;accesso all&#39;interfaccia del servizio da esprimere come URL; - **Nome richiesta** [0..1] – Testo libero. |

<a name=R3.2>**REQUISITO R3.2**</a> - **```rndt/metadata/2.0/req/sds/operation-metadata```**

Per ciascuna operazione, devono essere fornite le seguenti informazioni:

- **nome operazione** attraverso l&#39;elemento _```srv:operationName```_ che deve contenere l&#39;identificatore univoco dell&#39;interfaccia. La molteplicità di questo elemento è 1;

- **DCP** attraverso l&#39;elemento _```srv:DCP/srv:DCPList```_ con un riferimento alla &quot;Distributed Computing Platform&quot; su cui l&#39;operazione è stata implementata. La molteplicità di questo elemento è 1..N;

- **nome richiesta** attraverso l&#39;elemento _```srv:invocationName```_.La molteplicità di questo elemento è 0..1;

- **punto di connessione** attraverso l&#39;elemento _```srv:connectPoint/gmd:CI_OnlineResource/gmd:URL```_ con l&#39;indicazione dell&#39;URL dell&#39;endpoint da utilizzare per accedere al servizio per eseguire l&#39;operazione. La molteplicità di questo elemento è 1..N.

---

***Raccomandazione R3.2** - **```rndt/metadata/2.0/rec/sds/operations```***

*In riferimento ai servizi previsti da INSPIRE, dovranno essere descritte almeno le operazioni che le guide tecniche sui servizi, ad oggi disponibili, prescrivono di dover implementare obbligatoriamente. In particolare:*

*- per i servizi di ricerca (discovery services): Get Discovery Service Metadata (GetCapabilities), Discovery Metadata (GetRecords) e Link Discovery Service;*

*- per i servizi di consultazione (view services): Get View Service Metadata (GetCapabilities) e Get Map (GetMap);*

*- per i servizi di scaricamento (download services): Get Download Service Metadata, Get Spatial Dataset, Describe Spatial Dataset e Link Download Service;*

*- per i servizi di conversione (transformation services): Get Transformation Service Metadata, Transform e Link Transformation Service.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <srv:containsOperations>
        <srv:SV_OperationMetadata>
          <srv:operationName>
            <gco:CharacterString>GetCapabilities</gco:CharacterString>
          </srv:operationName >
          <srv:DCP>
            <srv:DCPList codeListValue="WebServices" codeList="#DCPList">WebServices</srv:DCPList>
          </srv:DCP>
          <srv:invocationName>
            <gco:CharacterString>request=GetCapabilities&service=CSW&acceptFormats=application%2Fxml&LANGUAGE=ita</gco:CharacterString>
          </srv:invocationName>
          <srv:connectPoint>
            <gmd:CI_OnlineResource>
              <gmd:linkage>
                <gmd:URL>https://geodati.gov.it/RNDT/csw</gmd:URL>
              </gmd:linkage>
            </gmd:CI_OnlineResource>
          </srv:connectPoint>
        </srv:SV_OperationMetadata>
      </srv:containsOperations>
      …
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
