## 3.6 Distribuzione dei dati

**Elementi:**

[3.6.1 Formato di distribuzione](#361-formato-di-distribuzione)

[3.6.2 Distributore](#362-distributore)

[3.6.3 Risorsa on-line](#363-risorsa-on-line)


### 3.6.1 Formato di distribuzione

|  |  |
| --- | --- |
| **Nome elemento** | Formato di distribuzione |
| **Riferimento** | [LG RNDT] – tab. I-41 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Codifica |
| **Definizione** | Descrizione del concetto (o dei concetti) del linguaggio informatico che specifica la rappresentazione degli oggetti di dati in un registro, un file, un messaggio, un supporto di memorizza­ zione o un canale di trasmissione. |
| **Istruzioni di implementazione** | - **Nome formato** [1] - Testo libero; - **Versione formato** [1] - Testo libero |

**REQUISITO 2.6** - **```metadata/2.0/req/isdss/data-encoding```**

Il formato dei dati deve essere indicato attraverso l&#39;elemento _```gmd:distributionFormat/gmd:MD_Format```_.

La molteplicità di questo elemento è 1..N.

Devono essere fornite le seguenti informazioni:

**- nome formato** , attraverso l&#39;elemento _```gmd:name```_;

**- versione formato** , attraverso l&#39;elemento _```gmd:version```_.

Se la versione non è nota o se non esiste una versione, l&#39;elemento _```gmd:version```_ deve essere lasciato vuoto e deve essere utilizzato l&#39;attributo _```nil reason```_ con il valore &quot;_unknown_&quot; o il valore &quot;_inapplicable_&quot; rispettivamente.

---

**Raccomandazione R1.9** - **```rndt/metadata/2.0/rec/datasets-and-series/use-anchors-for-format```**

Il nome del formato può essere indicato anche attraverso l&#39;elemento ```gmd:distributionFormat/gmd:MD_Format/gmd:name/gmx:Anchor```, con l&#39;attributo ```xlink:href``` riferito a uno dei valori del registro [INSPIRE media-types](http://inspire.ec.europa.eu/media-types/) pubblicato nel Sistema di Registri di INSPIRE.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:distributionInfo>
    <gmd:MD_Distribution>
      <gmd:distributionFormat>
        <gmd:MD_Format>
          <gmd:name>
            <gco:CharacterString>GML</gco:CharacterString>
          </gmd:name>
          <gmd:version>
            <gco:CharacterString>3.2</gco:CharacterString>
          </gmd:version>
        </gmd:MD_Format>
      </gmd:distributionFormat>
      <gmd:distributionFormat>
        <gmd:MD_Format>
          <gmd:name>
            <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/media-types/application/x-shapefile">ESRI Shapefile</gmx:Anchor>
          </gmd:name>
          <gmd:version gco:nilReason="unknown"/>
        </gmd:MD_Format>
      </gmd:distributionFormat>
      …
    </gmd:MD_Distribution>
  </gmd:distributionInfo>
  …
</gmd:MD_Metadata>
```

### 3.6.2 Distributore

|  |  |
| --- | --- |
| **Nome elemento** | Distributore |
| **Riferimento** | [LG RNDT] – tab. I-42 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Informazioni sull&#39;organizzazione che distribuisce i dati. |
| **Istruzioni di implementazione** | - **Nome dell&#39;Ente** [1] – Testo libero; - **Ruolo** [1] – Fare riferimento all&#39;elenco di codici &quot;_CI\_RoleCode_&quot; (§ 4.2.3.5 [LG RNDT]); - **Sito web** [0..1] - formato URL. Specificare obbligatoriamente anche il protocollo (es. _http_); - **Telefono** [0..1] - Testo libero; - **E-mail** [1..\*] - Testo libero. |

**REQUISITO R1.9** - **```rndt/metadata/2.0/req/datasets-and-series/distributor```**

Il responsabile della distribuzione della risorsa deve essere documentato attraverso l&#39;elemento _```gmd:distributionInfo/gmd:MD_Distribution/gmd:distributor/gmd:MD_Distributor/gmd:distributorContact/gmd:CI_ResponsibleParty```_.

La molteplicità dell&#39;elemento è 1..N.

L&#39;elemento _```gmd:CI_ResponsibleParty```_ deve contenere le seguenti informazioni:

il **nome dell&#39;Ente** deve essere fornito come valore dell&#39;elemento _```gmd:organisationName```_;

l&#39; **indirizzo e-mail** deve essere fornito come valore dell&#39;elemento _```gmd:CI_ResponsibleParty/gmd:contactInfo/gmd:CI_Contact/gmd:address/gmd:CI_Address/gmd:electronicMailAddress```_ contenente un indirizzo e-mail valido.

Il valore di _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode```_ deve essere il valore più pertinente dell&#39;elenco di codici ISO _```CI_RoleCode```_.

---

***Raccomandazione R1.10** - **r```ndt/metadata/2.0/rec/datasets-and-series/distributor-contact```***

*Possono essere documentati anche il &quot;Sito web&quot; e il &quot;Telefono&quot; del distributore attraverso gli elementi:*

*```gmd:contactInfo/gmd:CI_Contact/gmd:onlineResource/gmd:CI_OnlineResource/gmd:linkage/gmd:URL```, contenente l&#39;URL di un sito valido;*

*```gmd:contactInfo/gmd:CI_Contact/gmd:phone/gmd:CI_Telephone/gmd:voice```.*

*Il nome dell&#39;Ente dovrebbe essere riportato per intero, senza abbreviazioni. Si consiglia di indicare indirizzi e-mail istituzionali e non personali.*

---

***Raccomandazione R1.11** - **```rndt/metadata/2.0/rec/datasets-and-series/distributor-role```***

*Il valore di default per ```gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode``` è &quot;distributore&quot; (distributor), ma, nel caso l&#39;organizzazione ricopra più ruoli, può essere indicato il valore più pertinente tra quelli presenti nell&#39;elenco di codici ISO ```CI_RoleCode```.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:distributionInfo>
    <gmd:MD_Distribution>
    …
      <gmd:distributor>
        <gmd:MD_Distributor>
          <gmd:distributorContact>
            <gmd:CI_ResponsibleParty>
              <gmd:organisationName>
                <gco:CharacterString>Agenzia per le Erogazioni in Agricoltura</gco:CharacterString>
              </gmd:organisationName>
              <gmd:contactInfo>
                <gmd:CI_Contact>
                  <gmd:address>
                    <gmd:CI_Address>
                      <gmd:electronicMailAddress>
                        <gco:CharacterString>info@agea.gov.it</gco:CharacterString>
                      </gmd:electronicMailAddress>
                    </gmd:CI_Address>
                  </gmd:address>
                  <gmd:onlineResource>
                    <gmd:CI_OnlineResource>
                      <gmd:linkage>
                        <gmd:URL>http://www.agea.gov.it</gmd:URL>
                      </gmd:linkage>
                    </gmd:CI_OnlineResource>
                  </gmd:onlineResource>
                </gmd:CI_Contact>
              </gmd:contactInfo>
              <gmd:role>
                <gmd:CI_RoleCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode" codeListValue="distributor">distributore</gmd:CI_RoleCode>
              </gmd:role>
            </gmd:CI_ResponsibleParty>
          </gmd:distributorContact>
        </gmd:MD_Distributor>
      </gmd:distributor>
       …
    </gmd:MD_Distribution>
  </gmd:distributionInfo>
  …
</gmd:MD_Metadata>
```


### 3.6.3 Risorsa on-line

|  |  |
| --- | --- |
| **Nome elemento** | Risorsa on-line |
| **Riferimento** | [LG RNDT] – tab. I-43 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Localizzatore della risorsa |
| **Definizione** | Informazioni sulle fonti online attraverso le quali la risorsa può essere ottenuta. |
| **Istruzioni di implementazione** | Formato URL. Specificare obbligatoriamente il protocollo (es. _http_). |

<a name=1.8>**REQUISITO 1.8**</a> - **```metadata/2.0/req/datasets-and-series/resource-locator```**

Se disponibile, deve essere indicato l&#39;URL con il collegamento al servizio che fornisce l&#39;accesso online al dataset o alla serie di dataset.

Se non è disponibile nessun collegamento diretto al dataset o alla serie di dataset, deve essere indicato l&#39;URL a una risorsa online disponibile pubblicamente dove è possibile reperire maggiori informazioni.

Questi collegamenti devono essere codificati utilizzando l&#39;elemento _```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource/gmd:linkage/gmd:URL```_.

La molteplicità di questo elemento è 1..N.

---

***Raccomandazione R1.12** - **```rndt/metadata/2.0/rec/datasets-and-series/resource-locator```***

*Dovrebbero essere indicati:*

*- uno o più URL con il collegamento al servizio di consultazione che fornisce l&#39;accesso online al dataset o alla serie di dataset;*

*- uno o più URL con il collegamento al servizio di scaricamento che fornisce l&#39;accesso online al dataset o alla serie di dataset.*

*Questi collegamenti devono essere codificati come indicato nel Requisito [1.8](#1.8).*

*Gli URL forniti come valori dell&#39;elemento ```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource/gmd:linkage/gmd:URL``` devono puntare alla risposta di una richiesta di GetCapabilities del servizio.*

---

**REQUISITO R1.10** - **```rndt/metadata/2.0/req/datasets-and-series/resource-locator-details```**

L&#39;elemento _```gmd:CI_OnlineResource```_ deve includere anche:

- _```gmd:protocol/gmx:Anchor```_ che deve indicare il protocollo utilizzato per il Servizio. Nel caso di servizi di rete (discovery, view, download, transformation) esso deve puntare a uno dei valori dell&#39;elenco di codici _[Protocol](http://inspire.ec.europa.eu/metadata-codelist/ProtocolValue)_ disponibile nel Sistema di Registri INSPIRE. Nel caso di altri servizi (other), deve puntare a uno dei valori del registro Protocol disponibile nel Sistema di Registri INSPIRE Italia;

- _```gmd:applicationProfile/gmx:Anchor```_ che deve puntare a uno dei valori dell&#39;elenco di codici _[Tipo di servizio di dati territoriali](https://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType)_ disponibile nel Sistema di Registri INSPIRE;

- _```gmd:description/gmx:Anchor```_ che deve puntare al valore &quot;_accessPoint_&quot; dell&#39;elenco di codici _[Online description code](http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode)_ disponibile nel Sistema di Registri INSPIRE.

---

***Raccomandazione 1.9** - **```metadata/2.0/rec/datasets-and-series/resource-locator-url```***

*L&#39;URL indicato come valore dell&#39;elemento ```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource/gmd: linkage/gmd:URL``` dovrebbe puntare a uno dei seguenti tipi di risorsa:*

*• accesso diretto per scaricare il dataset;*

*• un documento di &quot;capabilities&quot; di un servizio di dati territoriali utilizzato per rendere disponibile il dataset;*

*• un documento WSDL di un servizio di dati territoriali utilizzato per rendere disponibile il dataset (SOAP binding);*

*• una pagina web dove reperire ulteriori informazioni per accedere al dataset;*

*• un&#39;applicazione client con cui si accede direttamente al dataset.*

---

**REQUISITO R1.11** - **```rndt/metadata/2.0/req/datasets-and-series/request-parameters```**

Se come &#39;localizzatore della risorsa&#39; viene utilizzato l&#39;URL al documento di _GetCapabilities_ dei servizi di consultazione e di scaricamento, l&#39;URL deve contenere i parametri obbligatori per l&#39;operazione di GetCapabilities (_service_, _version_ e _request_).

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:distributionInfo>
    <gmd:MD_Distribution>
    …
      <gmd:transferOptions>
        <gmd:MD_DigitalTransferOptions>
          <gmd:onLine>
            <gmd:CI_OnlineResource>
              <gmd:linkage>
                <gmd:URL>http://sgi.isprambiente.it/geoserver/LC/ows?service=WFS&amp;request=GetCapabilities</gmd:URL>
              </gmd:linkage>
              <gmd:protocol>
                <gmx:Anchor xlink:href="http://www.opengis.net/def/serviceType/ogc/wfs">Web Feature Service (WFS)</gmx:Anchor>
              </gmd:protocol>
              <gmd:applicationProfile>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType/download">download</gmx:Anchor>
              </gmd:applicationProfile>
              <gmd:description>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode/accessPoint">access point</gmx:Anchor>
              </gmd:description>
            </gmd:CI_OnlineResource>
          </gmd:onLine>
        </gmd:MD_DigitalTransferOptions>
      </gmd:transferOptions>
      <gmd:transferOptions>
        <gmd:MD_DigitalTransferOptions>
          <gmd:onLine>
            <gmd:CI_OnlineResource>
              <gmd:linkage>
                <gmd:URL>http://sgi.isprambiente.it/geoserver/LC/ows?service=WFS&amp;version=2.0.0&amp;request=GetFeature&amp;typeName=LC%3AGeo_Faglie_DT000001_RN&amp;maxFeatures=50&amp;outputFormat=text%2Fxml%3B%20subtype%3Dgml%2F2.1.2</gmd:URL>
              </gmd:linkage>
              <gmd:protocol>
                <gmx:Anchor xlink:href="http://www.opengis.net/def/serviceType/ogc/wfs">OGC:WFS</gmx:Anchor>
              </gmd:protocol>
              <gmd:applicationProfile>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType/download">download</gmx:Anchor>
              </gmd:applicationProfile>
              <gmd:description>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode/accessPoint">access point</gmx:Anchor>
              </gmd:description>
            </gmd:CI_OnlineResource>
          </gmd:onLine>
        </gmd:MD_DigitalTransferOptions>
      </gmd:transferOptions>
      <gmd:transferOptions>
        <gmd:MD_DigitalTransferOptions>
          <gmd:onLine>
            <gmd:CI_OnlineResource>
              <gmd:linkage>
                <gmd:URL>http://sgi.isprambiente.it/geoserver/LC/wms?service=WMS&amp;request=GetCapabilities</gmd:URL>
              </gmd:linkage>
              <gmd:protocol>
                <gmx:Anchor xlink:href="http://www.opengis.net/def/serviceType/ogc/wms">Web Map Service (WMS)</gmx:Anchor>
              </gmd:protocol>
              <gmd:applicationProfile>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType/view">view</gmx:Anchor>
              </gmd:applicationProfile>
              <gmd:description>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode/accessPoint">access point</gmx:Anchor>
              </gmd:description>
            </gmd:CI_OnlineResource>
          </gmd:onLine>
        </gmd:MD_DigitalTransferOptions>
      </gmd:transferOptions>
    </gmd:MD_Distribution>
  </gmd:distributionInfo>
  …
</gmd:MD_Metadata>
```
