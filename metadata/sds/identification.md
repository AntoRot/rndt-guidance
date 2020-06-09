### 4.1.2 Identificazione dei servizi

#### 4.1.2.1 Parole chiave

|  |  |
| --- | --- |
| **Nome elemento** | Parole chiave |
| **Riferimento** | [LG RNDT] – tab. V-15 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Parola chiave (Valore della parola chiave – Vocabolario controllato di origine) |
| **Definizione** | Parola formalizzata o utilizzata comunemente per descrivere la risorsa. |
| **Istruzioni di implementazione** | - **Parola chiave** [1..\*] - Testo libero; - **Thesaurus** [0..1] : - **Titolo** [1]– Testo libero;   - **Data** [1..\*] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1..\*] **-** L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]); |

**REQUISITO 3.4** - **```metadata/2.0/req/sds/sds-category```**

Deve essere indicata almeno una categoria o sottocategoria per il servizio utilizzando i valori linguisticamente neutri delle parole chiave definiti nella Parte D 4 &quot;_Classificazione dei servizi di dati territoriali_&quot; del [Regolamento 1205/2008].

---

***Raccomandazione 3.2** - **```metadata/2.0/rec/sds/sds-category-cv```***

*Per rendere chiaro il riferimento ai valori delle parole chiave della Parte D 4 del Regolamento 1205/2008/CE, queste parole chiave dovrebbero essere espresse come parole chiave derivanti da un vocabolario controllato utilizzando l&#39;elemento _gmx:Anchor_ con riferimento all&#39;elenco di codici ```Classificazione dei servizi di dati territoriali``` pubblicato nel Sistema di Registri INSPIRE. A tale scopo deve essere aggiunto l&#39;elemento ```gmd:MD_Keywords/gmd:thesaurusName``` contenente la citazione della Parte D 4 del Regolamento 1205/2008/CE e la relativa data di pubblicazione secondo quanto indicato al paragrafo [2.3.6](#_Parole_chiave).*

---

***Raccomandazione 3.3**  **```metadata/2.0/rec/sds/additional-keywords```***

*Si consiglia di inserire almeno due parole chiave in aggiunta a quelle obbligatorie corrispondenti alla categoria e sottocategoria di cui alla classificazione dei servizi di dati territoriali.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:identificationInfo>
    <srv:SV_ServiceIdentification>
    …
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword> <gco:CharacterString>infoCatalogueService</gco:CharacterString>
        </gmd:keyword>
        <gmd:keyword>
          <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory/humanCatalogueViewer">humanCatalogViewer</ gmx:Anchor>
        </gmd:keyword>
        <gmd:thesaurusName>
          <gmd:CI_Citation>
            <gmd:title>
              <gco:CharacterString>REGOLAMENTO (CE) N. 1205/2008 DELLA COMMISSIONE del 3 dicembre 2008 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda i metadati</gco:CharacterString>
            </gmd:title>
            <gmd:date>
              <gmd:CI_Date>
                <gmd:date>
                  <gco:Date>2008-12-03</gco:Date>
                </gmd:date>
                <gmd:dateType>
                  <gmd:CI_DateTypeCode codeListValue="publication" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode">pubblicazione</gmd:CI_DateTypeCode>
                </gmd:dateType>
              </gmd:CI_Date>
            </gmd:date>
          </gmd:CI_Citation>
        </gmd:thesaurusName>
      </gmd:MD_Keywords>
    </gmd:descriptiveKeywords>
    …
    </srv:SV_ServiceIdentification>
  </gmd:identificationInfo>
  …
</gmd:MD_Metadata>
```
