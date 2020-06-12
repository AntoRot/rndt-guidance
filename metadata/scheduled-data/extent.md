## 6.3 Estensione dei dati

### 6.3.1 Limite amministrativo

|  |  |
| --- | --- |
| **Nome elemento** | Limite amministrativo |
| **Riferimento** | [LG RNDT] – tab. VII-17 |
| **Molteplicità** | [1] |
| **Definizione** | Area geografica interessata dai dati. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO R9.5** - **```rndt/metadata/2.0/req/scheduled-data/geographic-identifier```**

Deve essere specificata l&#39;area geografica interessata dai dati che si intendono acquisire attraverso l&#39;elemento _```gmd:extent/gmd:EX_Extent/gmd:geographicElement/gmd:EX_GeographicDescription/gmd:geographicIdentifier/gmd:MD_Identifier/gmd:code```_.

La molteplicità di questo elemento è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:extent>
        <gmd:EX_Extent>
          <gmd:geographicElement>
            <gmd:EX_GeographicDescription>
              <gmd:geographicIdentifier>
                <gmd:MD_Identifier>
                  <gmd:code>
                    <gco:CharacterString>Regione Abruzzo</gco:CharacterString>
                  </gmd:code>
                </gmd:MD_Identifier>
              </gmd:geographicIdentifier>
            </gmd:EX_GeographicDescription>
          </gmd:geographicElement>
        </gmd:EX_Extent>
      </gmd:extent>
    …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
