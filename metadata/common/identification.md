## 2.3 Identificazione dei dati e dei servizi

**Elementi:**

2.3.1 Titolo

2.3.2 Data

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

*Il titolo deve essere conciso e puntuale. Esso non dovrebbe contenere acronimi o abbreviazioni incomprensibili. Si consiglia una lunghezza massima di 250 caratteri, riportando il &quot;nome ufficiale&quot; della risorsa.

Se i dati documentati sono parte di un progetto più ampio, si consiglia di indicare, tra parentesi, il progetto alla fine del titolo. Nel caso dei nomi dei progetti, sono consentite anche le abbreviazioni, purchè il resto del titolo segua la raccomandazione di cui sopra e l&#39;abbreviazione sia spiegata nella descrizione della risorsa.*

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
