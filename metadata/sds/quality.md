### 4.1.4 Qualità

#### 4.1.4.1 Livello di qualità

|  |  |
| --- | --- |
| **Nome elemento** | Livello di qualità |
| **Riferimento** | [LG RNDT] – tab. V-28 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Livello cui sono applicate le informazioni di qualità. |
| **Istruzioni di implementazione** | Esso deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_ScopeCode_&quot; (§ 4.2.3.13 [LG RNDT]). Il valore di default è: **servizio**. |

**Requisito 3.8** - **```metadata/2.0/req/sds/only-one-dq-element```**

Deve essere presente uno ed un solo elemento _```gmd:dataQualityInfo/gmd:DQ_DataQuality```_ riferito all&#39;intera risorsa.

Il campo di applicazione delle informazioni di qualità deve essere indicato attraverso l&#39;elemento _```gmd:scope/gmd:DQ_Scope/gmd:level/gmd:MD_ScopeCode```_ con riferimento al valore &quot;_service_&quot; (_servizio_) dell&#39;elenco di codici ISO _```MD_ScopeCode```_.

Inoltre, deve essere indicato il nome del livello attraverso l&#39;elemento _```gmd:scope/gmd:DQ_Scope/gmd:levelDescription/gmd:MD_ScopeDescription/gmd:other```_ che deve contenere il termine &quot;_servizio_&quot;.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dataQualityInfo>
    <gmd:DQ_DataQuality>
      <gmd:scope>
        <gmd:DQ_Scope>
          <gmd:level>
            <gmd:MD_ScopeCode codeListValue="service" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_ScopeCode">servizio</gmd:MD_ScopeCode>
          </gmd:level>
          <gmd:levelDescription>
            <gmd:MD_ScopeDescription>
              <gmd:other>
                <gco:CharacterString>servizio</gco:CharacterString>
              </gmd:other>
            </gmd:MD_ScopeDescription>
          </gmd:levelDescription>
        </gmd:DQ_Scope>
      </gmd:scope>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```
