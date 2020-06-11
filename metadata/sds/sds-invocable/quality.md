### 4.3.3 Qualità dei servizi


#### 4.3.3.1 Conformità: specifiche

|  |  |
| --- | --- |
| **Nome elemento** | Conformità: specifiche |
| **Riferimento** | [LG RNDT] – tab. V-29 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Conformità - specifica |
| **Definizione** | Citazione delle specifiche INSPIRE cui la risorsa si conforma. |
| **Istruzioni di implementazione** | - **Titolo** [1] – Testo libero; - **Data** [1] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1] – Il valore da inserire, tratto dall&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]), è &quot;_pubblicazione_&quot; (_publication_). Nel tracciato XML è presente anche un ulteriore elemento (che è obbligatorio per gli schemi XSD ma che non è richiesto nè da INSPIRE nè dal RNDT): &quot;_explanation_&quot;. Valorizzare tale elemento come da esempi XML. |

**REQUISITO 5.3** - **```metadata/2.0/req/sds-invocable/conformity```**

I metadati dei servizi invocabili devono includere la dichiarazione della conformità alle disposizioni di esecuzione (_implementing rules_) sull&#39;interoperabilità di dataset e servizi di rete attraverso l&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_, come indicato nel Requisito [C.20](../../common/data-quality.md#C.20). Questo elemento deve contenere la citazione del Regolamento n. 1089/2010 indicato secondo il Requisito [C.21](../../common/data-quality.md#C.21).

Il grado di conformità deve essere indicato secondo quanto indicato nel Requisito [C.22](../../common/data-quality.md#C.22).

La molteplicità dell&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_ utilizzato per lo scopo di cui sopra è 1.

---

**REQUISITO R5.1** - **```rndt/metadata/2.0/req/ sds-invocable/regulation-citation```**

Le informazioni relative al [Regolamento 1089/2010] da inserire sono le seguenti:

**Titolo** : _REGOLAMENTO (UE) N. 1089/2010 DELLA COMMISSIONE del 23 novembre 2010 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda l&#39;interoperabilità dei set di dati territoriali e dei servizi di dati territoriali_

**Data** : _2010-12-08_

**Tipo data** : _pubblicazione_.

---

***Raccomandazione 5.5** - **```metadata/2.0/rec/sds-invocable/uri-for-regulation-1089-2010```***

*Se il titolo delle specifiche è indicato come un elemento ```gmx:Anchor```, per indicare il [Regolamento 1089/2010] dovrebbe essere utilizzato il seguente URI: [http://data.europa.eu/eli/reg/2010/1089](http://data.europa.eu/eli/reg/2010/1089).*

---

***Raccomandazione 5.6** - **```metadata/2.0/rec/sds-invocable/uris-for-ats-and-cc```***

*Se si vuole dichiarare la conformità a un ATS (Abstract Test Suite) o a una classe di conformità utilizzando un elemento ```gmx:Anchor```, l&#39;URI che identifica l&#39;ATS o la classe di conformità dovrebbe essere utilizzato nell&#39;attributo ```xlink:href``` dell&#39;elemento relativo al titolo delle specifiche.*

---

**REQUISITO 5.5** - **```metadata/2.0/req/sds-invocable/conformity-to-technical-specification```**

Un servizio di dati territoriali invocabile deve dichiarare la piena conformità con almeno una specifica tecnica che fornisca tutti gli elementi tecnici necessari per invocare effettivamente il servizio e consentirne l&#39;utilizzo.

Questa dichiarazione deve essere indicata attraverso l&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_, come indicato nel Requisito [C.20](../../common/data-quality.md#C.20). Questo elemento deve contenere la citazione delle specifiche tecniche da indicare secondo il Requisito [C.21](../../common/data-quality.md#C.21).

Il grado di conformità, da specificare secondo quanto indicato nel Requisito [C.22](../../common/data-quality.md#C.22), deve indicare che il servizio è pienamente conforme con le specifiche e quindi l&#39;elemento _```gmd:DQ_ConformanceResult/gmd:pass/gco:Boolean```_ deve riportare il valore &quot;_true_&quot;.

La molteplicità dell&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_ utilizzato per lo scopo di cui sopra è 1.

---

***Raccomandazione 5.7** - **```metadata/2.0/rec/sds-invocable/specification-title-anchor```***

*Per essere interpretabile automaticamente (machine readable), l&#39;elemento relativo al titolo delle specifiche dovrebbe essere indicato attraverso l&#39;elemento ```gmx:Anchor``` con riferimento ad un indirizzo URL di pubblicazione ufficiale della specifica. Il contenuto testuale di questo elemento dovrebbe contenere il titolo ufficiale della specifica tecnica indicata.*

---

**Esempio di XML:**

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
                    <gmx:Anchor xlink:href="http://data.europa.eu/eli/reg/2010/1089">REGOLAMENTO (UE) N. 1089/2010 DELLA COMMISSIONE del 23 novembre 2010 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda l'interoperabilità dei set di dati territoriali e dei servizi di dati territoriali</gmx:Anchor>
                  </gmd:title>
                  <gmd:date>
                    <gmd:CI_Date>
                      <gmd:date>
                        <gco:Date>2010-12-08</gco:Date>
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
              <gmd:pass>
                <gco:Boolean>true</gco:Boolean>
              </gmd:pass>
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

#### 4.3.3.2 Categoria

|  |  |
| --- | --- |
| **Nome elemento** | Categoria |
| **Riferimento** | [LG RNDT] – tab. VI-1 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Categoria |
| **Definizione** | Questa è una citazione dello stato del servizio di dati spaziali rispetto all&#39;invocabilità. |
| **Istruzioni di implementazione** | - **Titolo** [1] – Testo libero; - **Data** [1] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1] **–** Il valore da inserire, tratto dall&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]), è &quot;_pubblicazione_&quot; (_publication_). Nel tracciato XML è presente anche un ulteriore elemento (che è obbligatorio per gli schemi XSD ma che non è richiesto nè da INSPIRE nè dal RNDT): &quot;_explanation_&quot;. Valorizzare tale elemento come da esempi XML modificando solo la tipologia del servizio. |

**REQUISITO 5.4** - **```metadata/2.0/req/sds-invocable/sds-category```**

Deve essere indicata la categoria del servizio di dati territoriali attraverso l&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_ come indicato nel Requisito [C.20](../../common/data-quality.md#C.20). Questo elemento deve contenere la citazione di una delle tre classi di conformità per le categorie dei servizi di dati territoriali indicata secondo il Requisito [C.21](../../common/data-quality.md#C.21).

Il titolo della citata classe di conformità deve essere riportato attraverso l&#39;elemento _```gmd:DQ_ConformanceResult/gmd:specification/gmd:CI_Citation/gmd:title/gmx:Anchor```_. L&#39;attributo _```xlink:href```_ di questo elemento deve contenere l&#39;identificatore univoco permanente della classe di conformità e il contenuto testuale dell&#39;elemento _```gmx:Anchor```_ deve contenere il corrispondente nome della categoria linguisticamente neutro. I nomi linguisticamente neutri e gli identificatori univoci permanenti sono riportati al § [A.2](#_A.2_Categorie_per) dell&#39;allegato A.

Il grado di conformità, da specificare secondo quanto indicato nel Requisito [C.22](../../common/data-quality.md#C.22), deve indicare che il servizio è pienamente conforme con la citata classe di conformità e quindi l&#39;elemento _```gmd:DQ_ConformanceResult/gmd:pass/gco:Boolean```_ deve riportare il valore &quot;_true_&quot;.

La molteplicità dell&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_ utilizzato per lo scopo di cui sopra è 1.

---

**REQUISITO R5.2** - **```rndt/metadata/2.0/req/sds-invocable/sds-category-citation```**

Le informazioni relative al tipo di servizio da inserire sono le seguenti:

**Titolo** : _invocable_ (per i servizi invocabili), _interoperable_ (per i servizi interoperabili), _harmonised_ (per i servizi di dati armonizzati)

**Data** : _2016-05-01_

**Tipo data** : _pubblicazione_.

---

**Esempio di XML:**

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
                    <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/id/ats/metadata/2.0/sds-invocable" xlink:title="INSPIRE Invocable Spatial Data Services metadata">invocable</gmx:Anchor>
                  </gmd:title>
                  <gmd:date>
                    <gmd:CI_Date>
                      <gmd:date>
                        <gco:Date>2016-05-01</gco:Date>
                      </gmd:date>
                      <gmd:dateType>
                        <gmd:CI_DateTypeCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode" codeListValue="publication">pubblicazione</gmd:CI_DateTypeCode>
                      </gmd:dateType>
                    </gmd:CI_Date>
                  </gmd:date>
                </gmd:CI_Citation>
              </gmd:specification>
              <gmd:explanation>
                <gco:CharacterString>Questo servizio di dati territoriali è conforme ai requisiti INSPIRE per i Servizi di Dati Territoriali Invocabili</gco:CharacterString>
              </gmd:explanation>
              <gmd:pass>
                <gco:Boolean>true</gco:Boolean>
              </gmd:pass>
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
