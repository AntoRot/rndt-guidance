## 2.4 Vincoli si dati

2.4.1 Limitazione d'uso

### 2.4.1 Limitazione d&#39;uso

|  |  |
| --- | --- |
| **Nome elemento** | Limitazione d&#39;uso |
| **Riferimento** | [LG RNDT] – tab. I-26, tab. V-22, tab. VII-19 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Restrizioni di utilizzo dei dati. |
| **Istruzioni di implementazione** | Testo libero. |

***Raccomandazione RC.12** - **```rndt/metadata/2.0/rec/common/use-limitation```***

*L&#39;elemento ```gmd:resourceConstraints/gmd:MD_Constraints/gmd:useLimitation``` può essere utilizzato per indicare eventuali limitazioni che incidono sull&#39;idoneità all&#39;uso della risorsa documentata.*

*La molteplicità dell&#39;elemento è 0..1.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:resourceConstraints>
        <gmd:MD_Constraints>
          <gmd:useLimitation>
            <gco:CharacterString>L’utilizzo è limitato solo ai Comuni</gco:CharacterString>
          </gmd:useLimitation>
          …
        </gmd:MD_Constraints>
      </gmd:resourceConstraints>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```
