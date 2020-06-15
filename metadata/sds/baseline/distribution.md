### 4.1.3 Distribuzione

#### 4.1.3.1 Risorsa on-line

|  |  |
| --- | --- |
| **Nome elemento** | Risorsa on-line |
| **Riferimento** | [LG RNDT] – tab. V-21 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Localizzatore della risorsa |
| **Definizione** | Indirizzo per l&#39;accesso online al servizio. |
| **Istruzioni di implementazione** | Formato URL. Specificare obbligatoriamente il protocollo (es. _http_). |

**REQUISITO 3.7** - **```metadata/2.0/req/sds/resource-locator```**

Se è disponibile l&#39;accesso al servizio, deve essere indicato il relativo link.

Se non è disponibile nessun accesso online al servizio, deve essere indicato l&#39;URL a una risorsa online disponibile pubblicamente dove è possibile reperire maggiori informazioni.

Questi collegamenti devono essere codificati utilizzando l&#39;elemento _```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource/gmd:linkage/gmd:URL```_.

La molteplicità di questo elemento è 0..N.

---

<a name=rec3.4>***Raccomandazione 3.4**</a> - **```metadata/2.0/rec/sds/resource-locator-additional-info```***

*Se possibile, oltre all&#39;elemento _```gmd:linkage```_, dovrebbero essere utilizzati anche gli elementi ```gmd:name```, ```gmd:description``` e ```gmd:function/gmd:CI_OnLineFunctionCode``` per fornire maggiori informazioni riguardo al collegamento URL riportato.*

*Se fornito, l&#39;elemento ```gmd:CI\_OnLineFunctionCode``` deve fare riferimento a uno dei valori dell&#39;elenco di codici ISO ```CI_OnLineFunctionCode```.*

---

***Raccomandazione R3.3** - **```rndt/metadata/2.0/rec/sds/resource-locator-additional-info```***

*Se possibile, oltre all&#39;elemento ```gmd:linkage``` e agli elementi di cui alla Raccomandazione [3.4](#rec3.4), dovrebbe essere utilizzato anche l&#39;elemento ```gmd:protocol``` da documentare secondo quanto indicato nel Requisito [R1.10](../../datasets-and-series/distribution.md#R1.10).*

---

***Raccomandazione 3.5** - **```metadata/2.0/rec/sds/resource-type-url-target```***

*L&#39;URL indicato come valore dell&#39;elemento ```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource/gmd: linkage/gmd:URL``` dovrebbe puntare a uno dei seguenti tipi di risorsa:*

*• un documento di &quot;capabilities&quot; del servizio di dati territoriali descritto;*

*• un documento WSDL del servizio di dati territoriali descritto (SOAP binding);*

*• una pagina web dove reperire ulteriori informazioni per il servizio descritto.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:distributionInfo>
    <gmd:MD_Distribution>
    …
      <gmd:transferOptions>
        <gmd:MD_DigitalTransferOptions>
          <gmd:onLine>
            <gmd:CI_OnlineResource>
              <gmd:linkage>
                <gmd:URL>http://sgi.isprambiente.it/geoserver/LC/ows?service=WFS&amp;request=GetCapabilities</gmd:URL>
              </gmd:linkage>
              <gmd:name>
                <gco:CharacterString>Richiesta GetCapabilities del servizio WFS</gco:CharacterString>
              </gmd:name>
              <gmd:protocol>
                <gmx:Anchor xlink:href="http://www.opengis.net/def/serviceType/ogc/wfs">OGC:WFS</gmx:Anchor>
              </gmd:protocol>
              <gmd:description>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode/accessPoint">access point</gmx:Anchor>
              </gmd:description>
            <gmd:function>
              <gmd:CI_OnLineFunctionCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_OnLineFunctionCode" codeListValue="download">download</gmd:CI_OnLineFunctionCode>
            </gmd:function>
           </gmd:CI_OnlineResource>
          </gmd:onLine>
        </gmd:MD_DigitalTransferOptions>
      </gmd:transferOptions>
    </gmd:MD_Distribution>
  </gmd:distributionInfo>
…
</gmd:MD_Metadata>
```
---

> Vai a [**4.1.4 Qualità dei servizi**](quality.md)
