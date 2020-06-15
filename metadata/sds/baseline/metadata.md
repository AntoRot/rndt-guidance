### 4.1.1 Livello gerarchico

|  |  |
| --- | --- |
| **Nome elemento** | Livello gerarchico |
| **Riferimento** | [LG RNDT] – tab. V-5 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Tipo di risorsa |
| **Definizione** | Categoria di informazione cui vengono applicati metadati. |
| **Istruzioni di implementazione** | Fare riferimento all&#39;elenco di codici &quot;_MD\_ScopeCode_&quot; (§ 4.2.3.13 [LG RNDT]). |

**REQUISITO 3.1** - **```metadata/2.0/req/datasets-and-series/resource-type```**

Il tipo di risorsa deve essere dichiarato con il valore &quot;_service_&quot; (_servizio_), di cui all&#39;elenco di codici _```MD_ScopeCode```_, attraverso l&#39;elemento _```gmd:MD_Metadata/gmd:hierarchyLevel/gmd:MD_ScopeCode```_.

Deve essere indicato anche il nome del livello gerarchico utilizzando l&#39;elemento ```gmd:hierarchyLevelName``` che deve contenere il valore &quot;_servizio_&quot;.

La molteplicità di questi elementi è 1.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:hierarchyLevel>
    <gmd:MD_ScopeCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_ScopeCode" codeListValue="service">servizio</gmd:MD_ScopeCode>
  </gmd:hierarchyLevel>
  <gmd:hierarchyLevelName>
    <gco:CharacterString>servizio</gco:CharacterString>
  </gmd:hierarchyLevelName>
  …
</gmd:MD_Metadata>
```
---

> Vai a [**4.1.2 Identificazione dei servizi**](identification.md)
