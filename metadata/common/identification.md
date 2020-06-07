## 2.3 Identificazione dei dati e dei servizi

**Elementi:**

[2.3.1 Titolo](identification.md#231-titolo)

[2.3.2 Data](identification.md#232-data)

[2.3.3 Responsabile](identification.md#233-responsabile)

### 2.3.1 Titolo

|  |  |
| --- | --- |
| **Nome elemento** | Titolo |
| **Riferimento** | [LG RNDT] – tab. I-10, tab. V-10, tab. VII-4 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Titolo della risorsa |
| **Definizione** | Nome caratteristico e spesso unico con il quale la risorsa è conosciuta. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO C.8** - **```metadata/2.0/req/common/resource-title```**

Deve essere fornito un titolo, leggibile (human readable), del dataset o della serie di dataset documentato attraverso l&#39;elemento _```gmd:citation/gmd:CI_Citation/gmd:title```_ con un valore nella lingua dei metadati.

La molteplicità dell&#39;elemento è 1.

---

***Raccomandazione C.3**  **```metadata/2.0/rec/common/resource-title```***

*Il titolo deve essere conciso e puntuale. Esso non dovrebbe contenere acronimi o abbreviazioni incomprensibili. Si consiglia una lunghezza massima di 250 caratteri, riportando il &quot;nome ufficiale&quot; della risorsa.*

*Se i dati documentati sono parte di un progetto più ampio, si consiglia di indicare, tra parentesi, il progetto alla fine del titolo. Nel caso dei nomi dei progetti, sono consentite anche le abbreviazioni, purchè il resto del titolo segua la raccomandazione di cui sopra e l&#39;abbreviazione sia spiegata nella descrizione della risorsa.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
      <gmd:citation>
        <gmd:CI_Citation>
          <gmd:title>
            <gco:CharacterString>Database Topografico della Regione Puglia</gco:CharacterString>
          </gmd:title>
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

### 2.3.2 Data

|  |  |
| --- | --- |
| **Nome elemento** | Data |
| **Riferimento** | [LG RNDT] – tab. I-11, tab. V-11, tab. VII-6 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | A seconda del tipo di data specificato, può corrispondere a &quot;Data di pubblicazione&quot;, &quot;Data dell&#39;ultima revisione&quot; o &quot;Data di creazione&quot;. |
| **Definizione** | Data di riferimento dei dati. |
| **Istruzioni di implementazione** |- **Data** [1] - formato ISO 8601 (aaaa-mm-gg); - **Tipo data** [1] – L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]). |

**REQUISITO C.11** - **```metadata/2.0/req/common/temporal-reference```**

Deve essere documentato almeno un riferimento temporale utilizzando l&#39;elemento _```gmd:citation/gmd:CI_Citation/gmd:date/gmd:CI_Date/gmd:date```_ con uno dei seguenti tipi di data:

- _publication_ (_pubblicazione_), per la data di pubblicazione della risorsa;

- _creation_ (_creazione_), per la data di creazione della risorsa;

- _revision_ (_revisione_), per la data di ultimo aggiornamento della risorsa.

Il tipo di data deve essere indicato utilizzando l&#39;elemento _```gmd:citation/gmd:CI_Citation/gmd:date/gmd:CI_Date/gmd:dateType/gmd:CI_DateTypeCode```_ e deve riportare il valore corrispondente dell&#39;elenco di codici ISO _```CI_DateTypeCode```_ riportati innanzi.

La data deve essere espressa utilizzando il calendario Gregoriano in conformità allo Standard ISO 8601 o solo come data o come data e ora. Nel primo caso si deve utilizzare l&#39;elemento _```gmd:CI_Date/gmd:date/gco:Date```_, mentre nel secondo caso _```gmd:CI_Date/gmd:date/gco:DateTime```_.

---

**REQUISITO C.12** - **```metadata/2.0/req/common/max-1-date-of-creation```**

Nel caso venga indicata la data di creazione dei dati, questa deve essere una sola.

---

**REQUISITO C.13** - **```metadata/2.0/req/common/max-1-date-of-last-revision```**

Nel caso venga indicata la data di ultimo aggiornamento dei dati, questa deve essere una sola.

---

***Raccomandazione C.6** - **```metadata/2.0/rec/common/date-of-last-revision-dataset```***

*Nel caso di dataset o di serie di dataset, dovrebbe essere riportata almeno la data di aggiornamento del dataset stesso.*

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
          <gmd:date>
            <gmd:CI_Date>
              <gmd:date>
                <gco:Date>1998-10-01</gco:Date>
              </gmd:date>
              <gmd:dateType>
                <gmd:CI_DateTypeCode codeListValue="creation" codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode">creazione</gmd:CI_DateTypeCode>
              </gmd:dateType>
            </gmd:CI_Date>
          </gmd:date>
          …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

### 2.3.3 Responsabile

|  |  |
| --- | --- |
| **Nome elemento** | Responsabile |
| **Riferimento** | [LG RNDT] – tab. I-13, tab. V-12, tab. VII-8 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Organizzazione titolare dei dati. |
| **Istruzioni di implementazione** |- **Nome dell&#39;Ente** [1] – Testo libero; - **Ruolo** [1]– L&#39;elemento deve assumere uno dei valori della&#39;elenco di codici &quot;_CI\_RoleCode_&quot; (§ 4.2.3.5 [LG RNDT]); - **Sito web** [0..1] - formato URL. Specificare obbligatoriamente anche il protocollo (es. _http_); - **Telefono** [0..1] - Testo libero; - **E-mail** [1..\*] - Testo libero. |

**REQUISITO RC.8** - **```rndt/metadata/2.0/req/common/responsible-party```**

Il responsabile della creazione, gestione e manutenzione della risorsa deve essere documentato attraverso l&#39;elemento _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty```_.

La molteplicità dell&#39;elemento è 1..N.

L&#39;elemento _```gmd:CI_ResponsibleParty```_ deve contenere i seguenti elementi:

- il **nome dell&#39;Ente** deve essere fornito come valore dell&#39;elemento _```gmd:organisationName```_ con un contenuto a testo libero non vuoto;

- l&#39; **indirizzo e-mail** deve essere fornito come valore dell&#39;elemento _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:contactInfo/gmd:CI_Contact/gmd:address/gmd:CI_Address/gmd:electronicMailAddress```_ con un contenuto a testo libero non vuoto contenente un indirizzo e-mail valido.

Il valore di _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode```_ deve essere il valore più pertinente dell&#39;elenco di codici _```CI_RoleCode```_.

---

**Requisito RC.9**  **```rndt/metadata/2.0/req/common/responsible-party-owner```**

Una istanza dell&#39;elemento _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty```_deve contenere il nome ufficiale dell&#39;Ente come presente nell&#39;_Indice dei domicili digitali delle pubbliche amministrazioni e dei gestori di pubblici servizi (IPA)_.

In questo caso il valore dell&#39;elemento _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode```_ deve essere &quot;_proprietario_&quot; (_owner_) presente nell&#39;elenco di codici ISO _```CI_RoleCode```_.

---

***Raccomandazione RC.5** - **```rndt/metadata/2.0/rec/common/responsible-party-contact```***

*Possono essere documentati anche il &quot;Sito web&quot; e il &quot;Telefono&quot; del responsabile metadati rispettivamente attraverso gli elementi:*

_- ```gmd:contactInfo/gmd:CI_Contact/gmd:onlineResource/gmd:CI_OnlineResource/gmd:linkage/gmd:URL```, contenente l&#39;URL di un sito valido;_

_- ```gmd:contactInfo/gmd:CI_Contact/gmd:phone/gmd:CI_Telephone/gmd:voice```._

*Il nome dell&#39;Ente dovrebbe essere riportato per intero, senza abbreviazioni. Si consiglia di indicare indirizzi e-mail istituzionali e non personali.*

---

***Raccomandazione RC.6** - **```rndt/metadata/2.0/rec/common/responsible-party-role```***

*A parte il proprietario di cui alla raccomandazione [RC.9](recRC.9), scegliere i ruoli che meglio rappresentano la funzione svolta dall&#39;organizzazione responsabile.*

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
      <gmd:citation>
        <gmd:CI_Citation>
        …
          <gmd:citedResponsibleParty>
            <gmd:CI_ResponsibleParty>
              <gmd:organisationName>
                <gco:CharacterString>Regione Piemonte</gco:CharacterString>
              </gmd:organisationName>
              <gmd:contactInfo>
                <gmd:CI_Contact>
                  <gmd:address>
                    <gmd:CI_Address>
                      <gmd:electronicMailAddress>
                        <gco:CharacterString>sitad@csi.it</gco:CharacterString>
                      </gmd:electronicMailAddress>
                    </gmd:CI_Address>
                  </gmd:address>
                  <gmd:onlineResource>
                    <gmd:CI_OnlineResource>
                      <gmd:linkage>
                        <gmd:URL>https://www.regione.piemonte.it</gmd:URL>
                      </gmd:linkage>
                    </gmd:CI_OnlineResource>
                  </gmd:onlineResource>
                </gmd:CI_Contact>
              </gmd:contactInfo>
              <gmd:role>
                <gmd:CI_RoleCode codeListValue="owner" codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode">proprietario</gmd:CI_RoleCode>
              </gmd:role>
            </gmd:CI_ResponsibleParty>
          </gmd:citedResponsibleParty>
          <gmd:citedResponsibleParty>
            <gmd:CI_ResponsibleParty>
              <gmd:organisationName>
                <gco:CharacterString>Regione Piemonte – Settore cartografia e sistema informativo territoriale</gco:CharacterString>
              </gmd:organisationName>
              <gmd:contactInfo>
                <gmd:CI_Contact>
                  <gmd:address>
                    <gmd:CI_Address>
                      <gmd:electronicMailAddress>
                        <gco:CharacterString>sitad@csi.it</gco:CharacterString>
                      </gmd:electronicMailAddress>
                    </gmd:CI_Address>
                  </gmd:address>
                  <gmd:onlineResource>
                    <gmd:CI_OnlineResource>
                      <gmd:linkage>
                        <gmd:URL>http://www.sistemapiemonte.it/serviziositad/</gmd:URL>
                      </gmd:linkage>
                    </gmd:CI_OnlineResource>
                  </gmd:onlineResource>
                </gmd:CI_Contact>
              </gmd:contactInfo>
              <gmd:role>
                <gmd:CI_RoleCode codeListValue="author" codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode">autore</gmd:CI_RoleCode>
              </gmd:role>
            </gmd:CI_ResponsibleParty>
          </gmd:citedResponsibleParty>
          …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```
