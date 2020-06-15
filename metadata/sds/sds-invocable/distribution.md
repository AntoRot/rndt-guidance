### 4.3.2 Distribuzione

#### 4.3.2.1 Risorsa on-line

|  |  |
| --- | --- |
| **Nome elemento** | Risorsa on-line |
| **Riferimento** | [LG RNDT] – tab. V-21 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Localizzatore della risorsa |
| **Definizione** | Indirizzo per l&#39;accesso online al servizio. |
| **Istruzioni di implementazione** | Formato URL. Specificare obbligatoriamente il protocollo (es. _http_). |

**REQUISITO 5.2** - **```metadata/2.0/req/sds-invocable/access-point```**

Deve essere descritto ogni punto di accesso del servizio di dati territoriali invocabile utilizzando l&#39;elemento _```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource```_.

L&#39;elemento _```gmd:linkage/gmd:URL```_ deve riportare l&#39;URL del punto di accesso descritto che contenga una descrizione dettagliata del servizio di dati territoriali, incluso l&#39;elenco degli endpoint per l&#39;esecuzione del servizio stesso.

L&#39;elemento _```gmd:linkage/gmd:description```_ deve contenere _```gmx:Anchor```_ che punti al valore &quot;_accessPoint_&quot; dell&#39;elenco di codici [_OnLineDescriptionCode_](http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode) pubblicato nel Sistema di Registri INSPIRE.

La molteplicità dell&#39;elemento _```gmd:transferOptions/gmd:MD_DigitalTransferOptions/gmd:onLine/gmd:CI_OnlineResource```_ utilizzato per lo scopo di cui sopra è 1..N.

---

***Raccomandazione 5.4** - **```metadata/2.0/rec/sds-invocable/access-point-additional-info```***

*Si consiglia che, in aggiunta agli elementi obbligatori ```gmd:linkage``` e ```gmd:description```, si utilizzino anche gli elementi ```gmd:name``` e ```gmd:function/gmd:CI_OnLineFunctionCode``` per indicare maggiori informazioni riguardo al collegamento URL riportato.*

*Se fornito, l&#39;elemento _```gmd:CI_OnLineFunctionCode```_ deve fare riferimento al valore &quot;_information_&quot; dell&#39;elenco di codici ISO ```CI_OnLineFunctionCode```.*

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
                <gmd:URL>https://geodati.gov.it/geodcat-ap_it/</gmd:URL>
              </gmd:linkage>
              <gmd:description>
                <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/OnLineDescriptionCode/accessPoint">access point</gmx:Anchor>
              </gmd:description>
              <gmd:function>
                <gmd:CI_OnLineFunctionCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_OnLineFunctionCode" codeListValue="information">information</gmd:CI_OnLineFunctionCode>
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

> In caso di servizi di dati territoriali interoperabili, vai a [**4.4 Metadati per i servizi di dati territoriali interoperabili**](../sds-interoperable)
