## 2.3 Identificazione dei dati e dei servizi

**Elementi:**

  [2.3.1 Titolo](identification.md#231-titolo)

  [2.3.2 Data](identification.md#232-data)

  [2.3.3 Responsabile](identification.md#233-responsabile)

  [2.3.4 Identificatore](identification.md#234-identificatore)

  [2.3.5 Descrizione](identification.md#235-descrizione)

  [2.3.6 Parole chiave](identification.md#236-parole-chiave)

  [2.3.7 Punto di contatto](identification.md#237-punto-di-contatto)

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

**REQUISITO RC.9**  **```rndt/metadata/2.0/req/common/responsible-party-owner```**

Una istanza dell&#39;elemento _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty```_deve contenere il nome ufficiale dell&#39;Ente come presente nell&#39;_[Indice dei domicili digitali delle pubbliche amministrazioni e dei gestori di pubblici servizi (IPA)](https://www.indicepa.gov.it/)_.

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

### 2.3.4 Identificatore

|  |  |
| --- | --- |
| **Nome elemento** | Identificatore |
| **Riferimento** | [LG RNDT] – tab. I-14, tab. V-13, tab. VII-9 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Identificatore univoco della risorsa |
| **Definizione** | Riferimento univoco che identifica la risorsa nel livello gerarchico specificato. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO RC.10** - **```rndt/metadata/2.0/req/common/dataset-uid```**

Deve essere indicato un indicatore univoco per ciascuna risorsa documentata. Tale indicatore deve essere un URI consistente in uno spazio di nomi (_namespace_), che identifica univocamente un contesto di denominazione governato da un&#39;autorità di identificazione, e un codice univoco nell&#39;ambito dello spazio di nomi.

L&#39;identificatore deve essere documentato attraverso l&#39;elemento _```gmd:citation/gmd:CI_Citation/gmd:identifier/*/gmd:code```_.

La molteplicità di questo elemento è 1.

---

**REQUISITO RC.11** - **```rndt/metadata/2.0/req/common/uid-ipa-code```**

L&#39;identificatore deve contenere, come prefisso,il **codice iPA** assegnato all&#39;Amministrazione nel momento dell&#39;accreditamento all&#39;_[Indice dei domicili digitali delle pubbliche amministrazioni e dei gestori di pubblici servizi (IPA)](https://www.indicepa.gov.it)_ secondo le regole definite in [LG IPAGPS].

Il separatore tra il codice iPA e la restante parte dell&#39;identificatore è &quot; **:**&quot; (due punti).

---

***Raccomandazione RC.7** - **```rndt/metadata/2.0/rec/common/use-md-identifier```***

*Si raccomanda fortemente di utilizzare ```MD_Identifier``` invece di ```RS_Identifier``` e di indicare l&#39;URI completo nell&#39;elemento relativo al codice.*

---

***Raccomandazione RC.8** - **```rndt/metadata/2.0/rec/common/resolvable-uid```***

*Si raccomanda di rendere risolvibile l&#39;identificatore univoco della risorsa in un documento che fornisca informazioni sulla risorsa descritta. Nel caso di URI http/https, per la risolvibilità dovrebbero essere utilizzati il DNS pubblico e i classici meccanismi di risoluzione di URI HTTP.*

*Per altri tipi di URI, dovrebbe essere disponibile un servizio di risoluzione che implementi una analoga funzionalità.*

*Il documento ottenuto come risultato del processo di risoluzione può essere, ma non è obbligatorio che lo sia, il record di metadati della risorsa descritta. Si raccomanda inoltre che la visualizzazione del documento fornito non richieda autenticazione dell&#39;utente, autorizzazione o strumenti specializzati di visualizzazione oltre a un normale browser web.*

---

***Raccomandazione RC.9** - **```rndt/metadata/2.0/rec/common/rndt-resolvable-uid```***

*Se l&#39;identificatore della risorsa assume lo stesso valore dell&#39;identificatore del file (fileIdentifier), di cui al paragrafo 2.2.1, come da requisito delle specifiche [CSW2 AP ISO], l&#39;identificatore è risolto nel documento di metadati presente nel RNDT.*

*A tale scopo, la struttura dell&#39;URI da inserire come valore dell&#39;elemento ```gmd:code``` deve essere la seguente:*

*https://geodati.gov.it/resource/id/_{identifier}*

*dove identifier è, appunto, l&#39;identificatore univoco della risorsa (coincidente con l&#39;identificatore del file di cui al paragrafo [2.2.1](#_Identificatore)).*

---

***Raccomandazione RC.10** - **```rndt/metadata/2.0/rec/common/persistent-uid```***

*I fornitori di identificatori univoci di risorse dovrebbero fare molta attenzione nel garantire che gli identificatori emessi rimangano validi e disponibili per l&#39;intero periodo di disponibilità della risorsa identificata, e preferibilmente anche dopo che la risorsa non sia più disponibile.*

*Se un identificatore univoco pubblicato per una risorsa deve essere modificato durante il periodo di disponibilità della risorsa stessa, sia il vecchio che il nuovo identificatore dovrebbero essere risolti con lo stesso documento descritto nella Raccomandazione [RC.9](#recRC9). Se ciò non fosse possibile, il vecchio identificatore dovrebbe essere risolto con un documento che fornisca informazioni sulla modifica dell&#39;identificatore univoco e indichi il nuovo identificatore univoco della risorsa descritta.*

*È opportuno evitare l&#39;assegnazione di un identificatore di risorsa univoco pubblicato a un&#39;altra risorsa, a cui, invece, dovrebbe essere assegnato un identificatore univoco nuovo.*

*La persistenza e il processo di prevenzione dell&#39;interruzione della risolvibilità dell&#39;identificatore sono fondamentali per mantenere funzionali i collegamenti tra i servizi e i dataset forniti.*

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
          <gmd:identifier>
            <gmd: MD_Identifier>
              <gmd:code>
                <gco:CharacterString>https://geodati.gov.it/resource/id/r_piemon:00000001</gco:CharacterString>
              </gmd:code>
            </gmd:MD_Identifier>
          </gmd:identifier>
          …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
 …
</gmd:MD_Metadata>
```

### 2.3.5 Descrizione

|  |  |
| --- | --- |
| **Nome elemento** | Descrizione |
| **Riferimento** | [LG RNDT] – tab. I-17, tab. V-14, tab. VII-11 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Breve descrizione della risorsa |
| **Definizione** | Breve testo di descrizione del contenuto della risorsa. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO C.9** - **```metadata/2.0/req/common/resource-abstract```**

Deve essere fornita una breve descrizione del contenuto della risorsa documentata attraverso l&#39;elemento _```gmd:abstract```_ nella lingua dei metadati.

La molteplicità di questo elemento è 1.

---

***Raccomandazione C.4** - **```metadata/2.0/rec/common/resource-abstract```***

*La descrizione può includere:*

*- un breve riassunto con i dettagli più importanti sui dati o i servizi documentati;*

*- la copertura dei dati, ovvero la trascrizione linguistica dell&#39;estensione o localizzazione geografica in aggiunta al riquadro di delimitazione (bounding box);*

*- i principali attributi;*

*- le fonti dei dati;*

*- i riferimenti normativi (che possono essere meglio dettagliati attraverso l&#39;elemento &quot;Altri dettagli_&quot; - v. § 3.2.3);*

*- l&#39;importanza della risorsa.*

*Non utilizzare acronimi di cui non si fornisca una spiegazione.*

*Riassumere i dettagli più importanti nel primo periodo o nei primi 256 caratteri.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:abstract>
        <gco:CharacterString>Dataset dei siti italiani iscritti nella Lista del Patrimonio Mondiale UNESCO identificati dalle relative perimetrazioni (area iscritta e zona tampone), approvate dal Comitato del Patrimonio Mondiale UNESCO. I siti, in alcuni casi, sono di tipo seriale, cioè composti da più elementi identificati, denominati e individuati sul territorio. Le perimetrazioni sono state identificate su cartografie differenti secondo i casi e l'estensione geografica. Le perimetrazioni di origine fanno parte dei documenti ufficiali di ciascun sito.Attributi e loro significato:ID: Identificativo interno; COD_UNESCO: Codice internazionale associato al sito; SITO: Denominazione ufficiale del sito; SERIALE: 0 sito non seriale, 1 sito seriale; COD_COMPON: Codice della componente (è popolato solo per le componenti dei siti seriali); COMPONENTE: Denominazione ufficiale della componente; TIPO_AREA: sito per area che identifica un sito, buffer per area che identifica zona tampone di un sito; SCALA_NOMI: Fattore di scala della cartografia utilizzata per la perimetrazione del sito o area di rispetto; TIPOLOGIA: sito culturale, monumento, complesso monumentale, sito, sito naturale, formazione fisica e biologica, formazione geologica, habitat minacciato, sito di eccezionale bellezza, interesse scientifico, sito misto</gco:CharacterString>
      </gmd:abstract>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

### 2.3.6 Parole chiave

|  |  |
| --- | --- |
| **Nome elemento** | Parole chiave |
| **Riferimento** | [LG RNDT] – tab. I-18, tab. V-15 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Parola chiave (Valore della parola chiave – Vocabolario controllato di origine) |
| **Definizione** | Parola formalizzata o utilizzata comunemente per descrivere la risorsa. |
| **Istruzioni di implementazione** | - **Parola chiave** [1..\*] - Testo libero; - **Thesaurus** [0..1] : - **Titolo** [1]– Testo libero;   - **Data** [1..\*] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1..\*] **-** L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]). |

**REQUISITO C.15** - **```metadata/2.0/req/common/keyword-originating-cv```**

Se vengono utilizzate parole chiave derivanti da un vocabolario controllato, il vocabolario deve essere citato attraverso l&#39;elemento _```gmd:descriptiveKeywords/gmd:MD_Keywords/gmd:thesaurusName/gmd:CI_Citation```_.

Il titolo del vocabolario deve essere indicato attraverso l&#39;elemento _```gmd:title```_.

La data di pubblicazione del vocabolario deve essere indicata attraverso gli elementi _```gmd:date/gmd:CI_Date/gmd:date/gco:Date```_ e _```gmd:dateType/gmd:CI_DateTypeCode```_. Quest&#39;ultimo deve fare riferimento al valore &quot;pubblicazione&quot; (_publication_) presente nell&#39;elenco di codici ISO _```CI_DateTypeCode```_.

---

***Raccomandazione C.7** - **```metadata/2.0/rec/common/use-cvs```***

*Sono da preferire le parole chiave rese disponibili in una raccolta di termini specifici e ben definiti (vocabolari controllati) rispetto ai termini a testo libero.*

---

***Raccomandazione C.8** - **```metadata/2.0/rec/common/use-anchors-for-cv-keywords```***

*Se vengono utilizzate le parole chiave dei vocabolari controllati e le singole parole chiave hanno un URI canonico specificato all&#39;interno del vocabolario controllato di provenienza, queste parole chiave devono essere codificate utilizzando l&#39;elemento ```gmd:keyword/gmx:Anchor```. L&#39;attributo ```xlink:href``` dell&#39;elemento ```gmx:Anchor``` dovrebbe essere utilizzato per riferirsi all&#39;URI canonico della parola chiave.*

---

***Raccomandazione C.9** - **```metadata/2.0/rec/common/use-anchors-for-thesauri```***

*Per i riferimenti a thesauri noti o a vocabolari controllati, il titolo dovrebbe essere codificato utilizzando l&#39;elemento ```gmd:thesaurusName/gmd:CI_Citation/gmd:title/gmx:Anchor```. L&#39;attributo ```xlink:href``` dell&#39;elemento ```gmx:Anchor``` dovrebbe essere usato per riferirsi all&#39;URI del thesaurus o al vocabolario controllato.*

---

**REQUISITO C.16** - **```metadata/2.0/req/common/group-keywords-by-cv```**

Tutte le parole chiave derivanti dallo stesso vocabolario controllato, o dalla stessa sua versione, devono essere raggruppate in un unico elemento _```gmd:descriptiveKeywords/gmd:MD_Keywords```_. Un singolo elemento _```gmd:MD_Keywords```_ può contenere solo parole chiave provenienti dal vocabolario controllato citato o dalla sua versione.

---

### 2.3.7 Punto di contatto

|  |  |
| --- | --- |
| **Nome elemento** | Punto di contatto |
| **Riferimento** | [LG RNDT] – tab. I-19, tab. V-16 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Parte responsabile – Ruolo della parte responsabile |
| **Definizione** | Organizzazione che è possibile contattare per avere informazioni sulla risorsa. |
| **Istruzioni di implementazione** | - **Nome dell&#39;Ente** [1] - Testo libero; - **Ruolo** [1] – L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_RoleCode_&quot; (§4.2.3.5 [LG RNDT]); - **Sito web** [0..1] - formato URL. Specificare obbligatoriamente anche il protocollo (es. _http_); - **Telefono** [0..1] - Testo libero; - **E-mail** [1..\*] - Testo libero. |

**REQUISITO C.10** - **```metadata/2.0/req/common/responsible-organisation```**

Dovrà essere fornito il punto di contatto dell&#39;organizzazione responsabile di dati e servizi attraverso l&#39;elemento _```gmd:pointOfContact/gmd:CI_ResponsibleParty```_.

La molteplicità dell&#39;elemento è 1..N.

L&#39;elemento _```gmd:CI_ResponsibleParty```_ deve contenere le seguenti informazioni:

- il **nome dell&#39;Ente** deve essere fornito come valore dell&#39;elemento _```gmd:organisationName```_;

- l&#39; **indirizzo e-mail** deve essere fornito come valore dell&#39;elemento _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:contactInfo/gmd:CI_Contact/gmd:address/gmd:CI_Address/gmd:electronicMailAddress```_ contenente un indirizzo e-mail valido.

Il valore di _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode```_ deve essere il valore più pertinente dell&#39;elenco di codici ISO _```CI_RoleCode```_.

---

**Raccomandazione RC.11** - **```rndt/metadata/2.0/rec/common/responsible-organisation-contact```**

*Possono essere documentati anche il &quot;Sito web&quot; e il &quot;Telefono&quot; del punto di contatto rispettivamente attraverso gli elementi:*

_- ```gmd:contactInfo/gmd:CI_Contact/gmd:onlineResource/gmd:CI_OnlineResource/gmd:linkage/gmd:URL```, contenente l&#39;URL di un sito valido;_

_- ```gmd:contactInfo/gmd:CI_Contact/gmd:phone/gmd:CI_Telephone/gmd:voice```._

---

**Raccomandazione C.5** - **```metadata/2.0/rec/common/responsible-organisation```**

*Il nome dell&#39;Ente dovrebbe essere riportato per intero, senza abbreviazioni. Si consiglia di indicare indirizzi e-mail istituzionali e non personali.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:pointOfContact>
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
      </gmd:pointOfContact>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```


Prossima sezione: [2.4 Vincoli sui dati](constraints.md)
