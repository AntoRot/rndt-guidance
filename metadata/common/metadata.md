## 2.2 Informazioni sui metadati

### 2.2.1 Identificatore del file

|  |  |
| --- | --- |
| **Nome elemento** | Identificatore del file |
| **Riferimento** | [LG RNDT] – tab. I-1, tab. V-1, tab. VII-1 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Identificatore univoco del file dei metadati. |
| **Istruzioni di implementazione** | Testo libero. |

<a name=RC.3>**REQUISITO RC.3**</a> - **```rndt/metadata/2.0/req/common/file-identifier```**

L&#39;identificatore deve essere codificato utilizzando l&#39;elemento _```gmd:MD_Metadata/gmd:fileIdentifier```_.

Esso deve contenere, come prefisso,il **codice iPA** assegnato all&#39;Amministrazione in sede di accreditamento all&#39;[_Indice dei domicili digitali delle pubbliche amministrazioni e dei gestori di pubblici servizi (IPA)_](https://www.indicepa.gov.it/).

Il separatore tra il codice iPA e la restante parte dell&#39;identificatore è &quot; **:**&quot; (due punti).

L&#39;identificatore deve essere univoco a livello globale e persistente.

La molteplicità dell&#39;elemento è 1.

---

**Esempio di XML:**

``` xml
<gmd:MD_Metadata>
  <gmd:fileIdentifier>
    <gco:CharacterString>r_campan:000002:20090220:111239</gco:CharacterString>
  </gmd:fileIdentifier>
…
</gmd:MD_Metadata>
```

### 2.2.2 Lingua dei metadati


|  |  |
| --- | --- |
| **Nome elemento** | Lingua dei metadati |
| **Riferimento** | [LG RNDT] – tab. I-2, tab. V-2, tab. VII-2 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Lingua dei metadati |
| **Definizione** | Linguaggio nel quale sono espressi i metadati. |
| **Istruzioni di implementazione** | L&#39;elenco di codici per le 24 lingue ufficiali della UE, da utilizzare per valorizzare l&#39;elemento, è il seguente (elenco basato sui codici a tre lettere di ISO 639-2/B come definito all&#39;indirizzo [http://www.loc.gov/standards/iso639-2/](http://www.loc.gov/standards/iso639-2/)): Bulgaro – **bul**, Ceco – **cze**, Croato - **hrv**, Danese – **dan**, Estone – **est**, Finlandese – **fin**, Francese – **fre**, Greco – **gre**, Inglese – **eng**, Irlandese – **gle**, Italiano – **ita**, Lettone – **lav**, Lituano – **lit**, Maltese – **mlt**, Olandese – **dut**, Polacco – **pol**, Portoghese – **por**, Rumeno – **rum**, Slovacco – **slo**, Sloveno – **slv**, Spagnolo – **spa**, Svedese - **swe**, Tedesco – **ger**, Ungherese – **hun**. La lingua di default per i metadati RNDT è, ovviamente, l&#39; **italiano** ( **ita** ). L&#39;elenco di tutti i codici (compresi quelli delle lingue regionali) è disponibile all&#39;indirizzo [http://www.loc.gov/standards/iso639-2/](http://www.loc.gov/standards/iso639-2/). |

<a name=C.5>**REQUISITO C.5**</a> - **```metadata/2.0/req/common/metadata-language-code```**

La lingua del contenuto dei metadati deve essere fornita attraverso l&#39;elemento _```gmd:MD_Metadata/gmd:language/gmd:LanguageCode```_ che deve puntare a uno dei codici a tre lettere delle lingue dell&#39;elenco ISO 639-2/B.

Devono essere usati solo i valori delle lingue ufficiali dell&#39;Unione Europea.

La molteplicità dell&#39;elemento è 1.

---

<a name=RC.4>**REQUISITO RC.4**</a> - **```rndt/metadata/2.0/req/common/metadata-language-name```**

Il valore del tag dell&#39;elemento _```gmd:MD_Metadata/gmd:language/gmd:LanguageCode```_ deve riportare lo stesso codice a tre lettere presente nell&#39;attributo _```codeListValue```_.

---

**Esempio di XML:**

``` xml
<gmd:MD_Metadata>
…
  <gmd:language>
    <gmd:LanguageCode codeList="http://www.loc.gov/standards/iso639-2/" codeListValue="ita">ita</gmd:LanguageCode>
  </gmd:language>
…
</gmd:MD_Metadata>
```

### 2.2.3 Set dei caratteri dei metadati

|  |  |
| --- | --- |
| **Nome elemento** | Set dei caratteri dei metadati |
| **Riferimento** | [LG RNDT] – tab. I-3, tab. V-3 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente. |
| **Definizione** | Nome dello standard del set di caratteri utilizzato per i metadati. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_CharacterSetCode_&quot; (§ 4.2.3.7 [LG RNDT]). |

<a name=RC.5>**REQUISITO RC.5**</a> - **```rndt/metadata/2.0/req/common/metadata-character-encoding```**

La codifica dei caratteri dei metadati deve essere documentata nel caso la codifica stessa non sia basata su UTF-8 attraverso l&#39;elemento _```gmd:MD_Metadata/gmd:characterSet/gmd:MD_CharacterSetCode```_ con riferimento a uno dei valori dell&#39;elenco di codici ISO _```MD_CharacterSetCode```_.

La molteplicità di questo element è 0..1.

---

**Esempio di XML:**

``` xml
<gmd:MD_Metadata>
…
  <gmd:characterSet>
    <gmd:MD_CharacterSetCode codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_CharacterSetCode" codeListValue="utf8">utf8</gmd:MD_CharacterSetCode>
  </gmd:characterSet>
…
</gmd:MD_Metadata>
```

### 2.2.4 Id file precedente

|  |  |
| --- | --- |
| **Nome elemento** | Id file precedente |
| **Riferimento** | [LG RNDT] – tab. I-4, tab. V-4 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente. |
| **Definizione** | Identificatore univoco del file di metadati dell&#39;eventuale trasmissione precedente a cui il file corrente è relazionato. |
| **Istruzioni di implementazione** | Testo libero. Per quanto riguarda il formato e i relativi requisiti, vale anche quanto indicato al § 2.2.1. |

***Raccomandazione RC.2**  **```rndt/metadata/2.0/rec/common/parent-identifier```***

L&#39;elemento potrebbe essere utile per tracciare la &quot;storia&quot; delle trasmissioni dei file XML e quindi degli aggiornamenti dei metadati. Esso dovrebbe assumere il valore dell&#39;elemento &quot;_Identificatore del file_&quot; del file trasmesso temporalmente in precedenza e a cui il file corrente è in relazione. Nel caso di primo impianto (quindi non esiste nessun file precedente), se presente, l&#39;elemento dovrebbe assumere lo stesso valore dell&#39;elemento &quot;_Identificatore del file_&quot; del file corrente.

Se documentato, deve essere utilizzato l&#39;elemento _```gmd:MD_Metadata/gmd:parentIdentifier```_.

---

**Esempio di XML:**

``` xml
<gmd:MD_Metadata>
…
  <gmd:parentIdentifier>
    <gco:CharacterString>r_campan:000001:20090124:093213</gco:CharacterString>
  </gmd:parentIdentifier>
…
</gmd:MD_Metadata>
```

### 2.2.5 Responsabile dei metadati

|  |  |
| --- | --- |
| **Nome elemento** | Responsabile dei metadati |
| **Riferimento** | [LG RNDT] – tab. I-6, tab. V-6, tab. VII-3 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Punto di contatto dei metadati |
| **Definizione** | Organizzazione responsabile della creazione e della manutenzione dei metadati. |
| **Istruzioni di implementazione** | - **Nome dell&#39;Ente** [1] - Testo libero ; - **Ruolo** [1]– Fare riferimento all&#39;elenco di codici _CI\_RoleCode_ di cui al § 4.2.3.5 [LG RNDT]; - **Sito web** [0..1] - formato URL. Specificare obbligatoriamente anche il protocollo (es. _http_); - **Telefono** [0..1] - Testo libero; - **E-mail** [1..\*] - Testo libero. |

**REQUISITO C.6** - **```metadata/2.0/req/common/md-point-of-contact```**

Il responsabile dei metadati deve essere documentato attraverso l&#39;elemento _```gmd:MD_metadata/gmd:contact/gmd:CI_ResponsibleParty```_.

La molteplicità dell&#39;elemento è 1..N.

Devono essere fornite le seguenti informazioni:

- il **nome dell&#39;Ente** deve essere fornito come valore dell&#39;elemento _```gmd:organisationName```_;

- l&#39; **indirizzo e-mail** deve essere fornito come valore dell&#39;elemento _```gmd:contactInfo/gmd:CI_Contact/gmd:address/gmd:CI_Address/gmd:electronicMailAddress```_ contenente un indirizzo e-mail valido.

Il valore di _```gmd:role/gmd:CI_RoleCode```_ deve essere &quot; **punto di contatto**&quot; ( **pointOfContact** ) presente nell&#39;elenco di codici ISO _```CI_RoleCode```_.

---

***Raccomandazione RC.3** - **```rndt/metadata/2.0/rec/common/md-point-of-contact```***

Possono essere documentati anche il &quot;Sito web&quot; e il &quot;Telefono&quot; del responsabile dei metadati rispettivamente attraverso gli elementi:

- _```gmd:contactInfo/gmd:CI_Contact/gmd:onlineResource/gmd:CI_OnlineResource/gmd:linkage/gmd:URL```_, utilizzando un valore di testo libero contenente l&#39;URL di un sito valido;

- _```gmd:contactInfo/gmd:CI_Contact/gmd:phone/gmd:CI_Telephone/gmd:voice```_.

---

**Raccomandazione C.2**  **```metadata/2.0/rec/common/organisation-name```**

Il nome dell&#39;Ente dovrebbe essere riportato per intero, senza abbreviazioni. Si consiglia di indicare indirizzi e-mail dell&#39;organizzazione e non personali.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:contact>
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
        <gmd:CI_RoleCode codeListValue="pointOfContact" codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode">punto di contatto</gmd:CI_RoleCode>
      </gmd:role>
    </gmd:CI_ResponsibleParty>
  </gmd:contact>
…
</gmd:MD_Metadata>
```

oppure

```xml
<gmd:MD_Metadata>
…
  <gmd:contact>
    <gmd:CI_ResponsibleParty>
      <gmd:organisationName>
        <gco:CharacterString>Regione Piemonte – Settore cartografia e sistema informativo territoriale</gco:CharacterString>
      </gmd:organisationName>
      <gmd:contactInfo>
        <gmd:CI_Contact>
          <gmd:phone>
            <gmd:CI_Telephone>
              <gmd:voice>
                <gco:CharacterString>0114321428</gco:CharacterString>
              </gmd:voice>
            </gmd:CI_Telephone>
          </gmd:phone>
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
        <gmd:CI_RoleCode codeListValue="pointOfContact" codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode">punto di contatto</gmd:CI_RoleCode>
      </gmd:role>
    </gmd:CI_ResponsibleParty>
  </gmd:contact>
…
</gmd:MD_Metadata>
```
