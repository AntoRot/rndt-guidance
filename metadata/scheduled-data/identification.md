## 6.2 Identificazione dei dati

**Elementi:**

[6.2.1 Data](#621-data)

[6.2.2 Altri dettagli](#622-altri-dettagli)

[6.2.3 Status](#623-status)

[6.2.4 Informazioni supplementari](#624-informazioni-supplementari)


### 6.2.1 Data

|  |  |
| --- | --- |
| **Nome elemento** | Data |
| **Riferimento** | [LG RNDT] – tab. VII-6 |
| **Molteplicità** | [1] |
| **Definizione** | Data probabile di disponibilità dei dati. |
| **Istruzioni di implementazione** | Formato ISO 8601. |

**REQUISITO R9.2** - **```rndt/metadata/2.0/req/scheduled-data/availability-date```**

La data, espressa conformemente allo Standard ISO 8601, deve indicare approssimativamente quando i dati potrebbero essere disponibili.

Il tipo di data deve essere indicato appropriatamente: se la data presunta di disponibilità si riferisce al rilascio si deve utilizzare il valore &quot;_creazione_&quot; (_creation_); se, invece, si riferisce alla pubblicazione si deve utilizzare il valore &quot;_pubblicazione_&quot; (_publication_); se, infine, si riferisce ad un aggiornamento si deve utilizzare il valore &quot;_revisione_&quot; (_revision_).

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

Fare riferimento all&#39;esempio [2.3.2](../common/identification.md#232-data).


### 6.2.2 Altri dettagli

|  |  |
| --- | --- |
| **Nome elemento** | Altri dettagli |
| **Riferimento** | [LG RNDT] – tab. VII-10 |
| **Molteplicità** | [0..1] |
| **Definizione** | Ulteriori informazioni di citazione. |
| **Istruzioni di implementazione** | Testo libero. |

***Raccomandazione R9.1** - **```rndt/metadata/2.0/rec/scheduled-data/services-planned```***

*L&#39;elemento può essere utilizzato per indicare gli eventuali servizi previsti e la relativa data di disponibilità attraverso l&#39;elemento ```gmd:citation/gmd:CI_Citation/gmd:otherCitationDetails```.*

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
            <gco:CharacterString>È prevista l’implementazione dei servizi WMS, WFS e Atom che saranno disponibili nel mese di marzo 2021</gco:CharacterString>
          </gmd:otherCitationDetails>
        …
        </gmd:CI_Citation>
      </gmd:citation>
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

### 6.2.3 Status

|  |  |
| --- | --- |
| **Nome elemento** | Status |
| **Riferimento** | [LG RNDT] – tab. VII-12 |
| **Molteplicità** | [1] |
| **Definizione** | Fase di programmazione/realizzazione |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_ProgressCode_&quot; (§ 4.2.7.1 [LG RNDT]). |

**REQUISITO R9.3** - **```rndt/metadata/2.0/req/scheduled-data/status```**

Deve essere indicato lo stato di produzione dei dati attraverso l&#39;elemento _```gmd:status/gmd:MD_ProgressCode```_ con riferimento a uno dei valori dell&#39;elenco di codici ISO _```MD_ProgressCode```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:status>
        <MD_ProgressCode codeListValue="underDevelopment" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_ProgressCode">in corso di sviluppo</MD_ProgressCode>
      </gmd:status>
    …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```

### 6.2.4 Informazioni supplementari

|  |  |
| --- | --- |
| **Nome elemento** | Informazioni supplementari |
| **Riferimento** | [LG RNDT] – tab. VII-18 |
| **Molteplicità** | [1] |
| **Definizione** | Informazioni descrittive supplementari sui dati. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO R9.4** - **```rndt/metadata/2.0/req/scheduled-data/schedule-information```**

Devono essere indicate le informazioni sulla programmazione delle nuove acquisizioni di dati attraverso l&#39;elemento _```gmd:supplementalInformation```_ relativamente ai seguenti aspetti:

- costo previsto;

- copertura finanziaria, se è completa, parziale o da definire;

- grado di copertura finanziaria, cioè la percentuale di copertura finanziaria rispetto al costo indicativo previsto;

- modalità di acquisizione, cioè le modalità amministrative di selezione del fornitore o di acquisizione in proprio.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:supplementalInformation>
        <gco:CharacterString>Il costo previsto è di 400.000 euro con copertura completa a carico dell’Amministrazione. La modalità di acquisizione seguita è la procedura aperta.</gco:CharacterString>
      </gmd:supplementalInformation>
    …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
---

> Vai a [**6.3 Estensione dei dati**](extent.md)
