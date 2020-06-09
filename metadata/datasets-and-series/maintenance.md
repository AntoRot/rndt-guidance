## 3.7 Gestione dei dati

### 3.7.1 Frequenza di aggiornamento

|  |  |
| --- | --- |
| **Nome elemento** | Frequenza di aggiornamento |
| **Riferimento** | [LG RNDT] – tab. I-44 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Frequenza con la quale sono registrati gli aggiornamenti dei dati. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_MaintenanceFrequencyCode_&quot; (§ 4.2.3.10 [LG RNDT]). |

***Raccomandazione R1.13** - **```rndt/metadata/2.0/rec/datasets-and-series/resource-maintenance```***

*Per fornire informazioni sulla frequenza di aggiornamento del dataset o della serie di dataset può essere utilizzato l&#39;elemento ```gmd:resourceMaintenance/gmd:MD\_MaintenanceInformation/gmd:maintenanceAndUpdateFrequency/gmd:MD\_MaintenanceFrequencyCode``` con il valore più pertinente dell&#39;elenco di codici ISO ```MD_MaintenanceFrequencyCode```.*

*La molteplicità di questo elemento è 0..N.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:resourceMaintenance>
        <gmd:MD_MaintenanceInformation>
          <gmd:maintenanceAndUpdateFrequency>
            <gmd:MD_MaintenanceFrequencyCode codeListValue="asNeeded" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_MaintenanceFrequencyCode">quando necessario</gmd:MD_MaintenanceFrequencyCode>
          </gmd:maintenanceAndUpdateFrequency>
        </gmd:MD_MaintenanceInformation>
      </gmd:resourceMaintenance>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
