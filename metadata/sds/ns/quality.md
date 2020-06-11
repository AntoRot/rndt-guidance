### 4.2.2 Qualità dei servizi

#### 4.2.2.1 Conformità: specifiche

|  |  |
| --- | --- |
| **Nome elemento** | Conformità: specifiche |
| **Riferimento** | [LG RNDT] – tab. V-29 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Conformità - specifica |
| **Definizione** | Citazione delle specifiche INSPIRE cui la risorsa si conforma. |
| **Istruzioni di implementazione** | - **Titolo** [1] – Testo libero; - **Data** [1] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1] **–** Il valore da inserire, tratto dall&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]), è &quot;_pubblicazione_&quot; (_publication_). Nel tracciato XML è presente anche un ulteriore elemento (che è obbligatorio per gli schemi XSD ma che non è richiesto nè da INSPIRE nè dal RNDT): &quot;_explanation_&quot;. Valorizzare tale elemento come da esempi XML. |

<a name=rec4.1>***Raccomandazione 4.1**</a> - **```metadata/2.0/rec/ns/conformity```***

*I metadati dei servizi di rete dovrebbero includere la dichiarazione della conformità alle disposizioni di esecuzione (implementing rules) sui servizi di rete attraverso l&#39;elemento ```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```, come indicato nel Requisito [C.20](../../common/data-quality.md#C.20). Questo elemento dovrebbe contenere la citazione del Regolamento n. 976/2009 indicato secondo il Requisito [C.21](../../common/data-quality.md#C.21).*

*Il grado di conformità dovrebbe essere indicato secondo quanto indicato nel Requisito [C.22](../../common/data-quality.md#C.22).*

*La molteplicità dell&#39;elemento ```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult``` utilizzato per lo scopo di cui sopra è 1.*

---

***Raccomandazione R4.1** - **```rndt/metadata/2.0/rec/ns/regulation-citation```***

*Le informazioni di citazione da inserire per gli scopi della Raccomandazione [4.1](#rec4.1) sono le seguenti:*

***Titolo** : &quot;REGOLAMENTO (CE) N. 976/2009 DELLA COMMISSIONE del 19 ottobre 2009 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda i servizi di rete&quot;;*

***Data** : 2009-10-19;*

***Tipo data** : &quot;pubblicazione&quot;.*

---

***Raccomandazione 4.2** - **```metadata/2.0/rec/ns/uri-for-regulation-976-2009```***

*Se il titolo delle specifiche è indicato come un elemento ```gmx:Anchor```, per indicare il Regolamento n. 976/2009 dovrebbe essere utilizzato il seguente URI: [_http://data.europa.eu/eli/reg/2009/976_](http://data.europa.eu/eli/reg/2009/976).*

---

**NOTA** – Le raccomandazioni di cui sopra si applicano a qualsiasi specifica tecnica (non solo INSPIRE) rispetto alla quale i servizi sono testati. Cioè, se un servizio è sviluppato secondo una data specifica che include procedure di valutazione della qualità, allora la conformità a detta specifica dovrebbe essere documentata utilizzando i metadati &quot;Conformità&quot; previsti dal RNDT.

***Raccomandazione 4.3** - **```metadata/2.0/rec/ns/uris-for-ats-and-cc```***

*Se si vuole dichiarare la conformità a un ATS (Abstract Test Suite) o a una classe di conformità utilizzando un elemento ```gmx:Anchor```, l&#39;URI che identifica l&#39;ATS o la classe di conformità dovrebbe essere utilizzato nell&#39;attributo ```xlink:href``` dell&#39;elemento relativo al titolo delle specifiche.*

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dtataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_DomainConsistency>
          <gmd:result>
            <gmd:DQ_ConformanceResult>
              <gmd:specification>
                <gmd:CI_Citation>
                  <gmd:title>
                    <gmx:Anchor xlink:href="http://data.europa.eu/eli/reg/2009/976">REGOLAMENTO (CE) N. 976/2009 DELLA COMMISSIONE del 19 ottobre 2009 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda i servizi di rete</gmx:Anchor>
                  </gmd:title>
                  <gmd:date>
                    <gmd:CI_Date>
                      <gmd:date>
                        <gco:Date>2009-10-19</gco:Date>
                      </gmd:date>
                      <gmd:dateType>
                        <gmd:CI_DateTypeCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode" codeListValue="publication">pubblicazione</gmd:CI_DateTypeCode>
                      </gmd:dateType>
                    </gmd:CI_Date>
                  </gmd:date>
                </gmd:CI_Citation>
              </gmd:specification>
              <gmd:explanation>
                <gco:CharacterString>Fare riferimento alle specifiche indicate</gco:CharacterString>
              </gmd:explanation>
              …
            </gmd:DQ_ConformanceResult>
          </gmd:result>
        </gmd:DQ_DomainConsistency>
      </gmd:report>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```

```xml
<gmd:MD_Metadata>
  …
  <gmd:dtataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_DomainConsistency>
          <gmd:result>
            <gmd:DQ_ConformanceResult>
              <gmd:specification>
                <gmd:CI_Citation>
                  <gmd:title>
                    <gco:CharacterString>Technical Guidance for the implementation of INSPIRE View Services</gco:CharacterString>
                  </gmd:title>
                  <gmd:date>
                    <gmd:CI_Date>
                      <gmd:date>
                        <gco:Date>2013-04-04</gco:Date>
                      </gmd:date>
                      <gmd:dateType>
                        <gmd:CI_DateTypeCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode" codeListValue="publication">pubblicazione</gmd:CI_DateTypeCode>
                      </gmd:dateType>
                    </gmd:CI_Date>
                  </gmd:date>
                </gmd:CI_Citation>
              </gmd:specification>
              <gmd:explanation>
                <gco:CharacterString>Fare riferimento alle specifiche indicate</gco:CharacterString>
              </gmd:explanation>
              …
            </gmd:DQ_ConformanceResult>
          </gmd:result>
        </gmd:DQ_DomainConsistency>
      </gmd:report>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```
