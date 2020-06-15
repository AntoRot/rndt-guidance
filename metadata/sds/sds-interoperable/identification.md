### 4.4.1 Identificazione dei servizi


#### 4.4.1.1 Punto di contatto

|  |  |
| --- | --- |
| **Nome elemento** | Punto di contatto |
| **Riferimento** | [LG RNDT] – tab. V-16 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Parte responsabile – Ruolo della parte responsabile |
| **Definizione** | Organizzazione custode responsabile. |
| **Istruzioni di implementazione** | - **Nome dell&#39;Ente** [1] - Testo libero; - **Ruolo** [1] – L&#39;elemento deve assumere il valore &quot;_custodian_&quot; (_custode_) dell&#39;elenco di codici &quot;_CI\_RoleCode_&quot; (§4.2.3.5 [LG RNDT]); - **Sito web** [0..1] - formato URL. Specificare obbligatoriamente anche il protocollo (es. _http_); - **Telefono** [0..1] - Testo libero; - **E-mail** [1..\*] - Testo libero. |

**REQUISITO 6.4** - **```metadata/2.0/req/sds-interoperable/responsible-party```**

Dovrà essere indicata l&#39;organizzazione responsabile del servizio di dati territoriali interoperabile con il ruolo di custode seguendo le indicazioni del Requisito [C.10](../../common/identification.md#C.10).

La molteplicità dell&#39;elemento _```gmd:pointOfContact/gmd:CI_ResponsibleParty```_ per lo scopo di cui sopra è 1..N.

Il valore di _```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode```_ deve essere &quot;_custodian_&quot; (custode) presente nell&#39;elenco di codici ISO _```CI_RoleCode```_.

---

**Raccomandazione C.4**  **```metadata/2.0/rec/common/resource-abstract```**

Per l&#39;elemento ```gmd:citedResponsibleParty/gmd:CI_ResponsibleParty/gmd:role/gmd:CI_RoleCode``` del Punto di contatto si può scegliere il ruolo più pertinente, come indicato nel Requisito [C.10](../../common/identification.md#C.10).

Nel caso in cui l&#39;Ente responsabile della produzione, gestione e manutenzione del servizio coincida con l&#39;Ente che ha anche la funzione di custode, può essere sufficiente utilizzare la stessa istanza dell&#39;elemento &quot;Punto di contatto&quot; con il ruolo impostato a &quot;custode&quot;.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:pointOfContact>
        <gmd:CI_ResponsibleParty>
          <gmd:organisationName>
            <gco:CharacterString>Regione Piemonte – Settore cartografia e sistema informativo territoriale</gco:CharacterString>
          </gmd:organisationName>
          <gmd:contactInfo>
            <gmd:CI_Contact>
              <gmd:address>
                <gmd:CI_Address>
                  <gmd:electronicMailAddress>
                    <gco:CharacterString>sitad@csi.it</gco:CharacterString>
                  </gmd:electronicMailAddress>
                </gmd:CI_Address>
              </gmd:address>
              <gmd:onlineResource>
                <gmd:CI_OnlineResource>
                  <gmd:linkage>
                    <gmd:URL>http://www.sistemapiemonte.it/serviziositad/</gmd:URL>
                  </gmd:linkage>
                </gmd:CI_OnlineResource>
              </gmd:onlineResource>
            </gmd:CI_Contact>
          </gmd:contactInfo>
          <gmd:role>
            <gmd:CI_RoleCode codeListValue="custodian" codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode">custode</gmd:CI_RoleCode>
          </gmd:role>
        </gmd:CI_ResponsibleParty>
      </gmd:pointOfContact>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
---

> Vai a [**4.4.2 Vincoli**](constraints)
