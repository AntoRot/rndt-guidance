### 4.3.1 Informazioni sui metadati

**Elementi:**

4.3.1.1 Tipo di servizio



#### 4.3.1.1 Tipo di servizio

|  |  |
| --- | --- |
| **Nome elemento** | Tipo di servizio |
| **Riferimento** | [LG RNDT] – tab. V-17 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Tipo di servizio di dati territoriali |
| **Definizione** | Nome del tipo di servizio da un registro di servizi. |
| **Istruzioni di implementazione** | Fare riferimento all&#39;elenco di codici &quot;_ServiceType_&quot; di cui al § 4.2.5.5 [LG RNDT]. |

**REQUISITO 5.1** - **```metadata/2.0/req/sds-invocable/sds-type```**

Per indicare il tipo di servizio di dati territoriali nel caso di servizi invocabili secondo quanto indicato nel Requisito [3.5](../baseline/identification.md#3.5), utilizzareil valore &quot;_other_&quot;.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <srv:serviceType>
        <gco:LocalName codeSpace="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType">other</gco:LocalName>
      </srv:serviceType>
    …
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
