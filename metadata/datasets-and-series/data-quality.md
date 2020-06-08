## 3.4 Qualità dei dati

**Elementi:**

[3.4.1 Livello di qualità](#341-livello-di-qualità)

[3.4.2 Accuratezza posizionale](#342-accuratezza-posizionale)

[3.4.3 Coerenza topologica](#343-coerenza-topologica)

[3.4.4 Genealogia](#344-genealogia)

[3.4.5 Conformità: specifiche](#345-conformità-specifiche)


### 3.4.1 Livello di qualità

|  |  |
| --- | --- |
| **Nome elemento** | Livello di qualità |
| **Riferimento** | [LG RNDT] – tab. I-33 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Livello cui sono applicate le informazioni di qualità. |
| **Istruzioni di implementazione** | L&#39;elemento deve assumere uno dei valori dell&#39;elenco di codici &quot;_MD\_ScopeCode_&quot; (§ 4.2.3.13 [LG RNDT]). |

<a name=1.9>**REQUISITO 1.9**</a> - **```metadata/2.0/req/datasets-and-series/one-data-quality-element```**

Deve esserci un solo elemento _```gmd:dataQualityInfo/gmd:DQ_DataQuality```_ con riferimento all&#39;intero dataset o serie di dataset descritto.

Il campo di applicazione della qualità deve essere codificato attraverso l&#39;elemento _```gmd:scope/gmd:DQ_Scope/gmd:level/gmd:MD_ScopeCode```_ con il valore &quot;dataset&quot; o &quot;series&quot; presente nell&#39;elenco di codici ISO _```MD_ScopeCode```_.

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dtataQualityInfo>
    <gmd:DQ_DataQuality>
      <gmd:scope>
        <gmd:DQ_Scope>
          <gmd:level>
            <gmd:MD_ScopeCode codeListValue="dataset" codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_ScopeCode">dataset</gmd:MD_ScopeCode>
          </gmd:level>
        </gmd:DQ_Scope>
      </gmd:scope>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```

### 3.4.2 Accuratezza posizionale

|  |  |
| --- | --- |
| **Nome elemento** | Accuratezza posizionale |
| **Riferimento** | [LG RNDT] – tab. I-34 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Informazioni per la descrizione dell&#39;accuratezza posizionale dei dati. |
| **Istruzioni di implementazione** | - **Unità di misura** [1] - utilizzare il metro (m); - **Valore** [1] - utilizzare il tipo _gco:Real_. |

**REQUISITO R1.7** - **```rndt/metadata/2.0/rec/datasets-and-series/positional-accuracy```**

L&#39;accuratezza posizionale del dataset o della serie di dataset deve essere indicata attraverso l&#39;elemento _```gmd:dataQualityInfo/gmd:DQ_DataQuality/gmd:report/gmd:DQ_AbsoluteExternalPositionalAccuracy```_.

Devono essere fornite le seguenti informazioni:

- **unità di misura** , attraverso l&#39;elemento _```gmd:result/gmd:DQ_QuantitativeResult/gmd:valueUnit```_;

- **valore** , attraverso l&#39;elemento _```gmd:result/gmd:DQ_QuantitativeResult/gmd:value/gco:Record/gco:Real```_.

L&#39;unità di misura da utilizzare deve essere il metro (m). Per documentare questo elemento, è necessario valorizzare gli attributi:

- &#39;_```gml:id```_&#39; dell&#39;elemento _```gml:BaseUnit```_,

- &#39;_```codeSpace```_&#39; dell&#39;elemento _```gml:identifier```_. Il valore dell&#39;attributo deve essere [_http://www.bipm.org/en/si/base\_units_](http://www.bipm.org/en/si/base_units), mentre il valore del tag deve riportare il simbolo dell&#39;inità di misura &quot;_m_&quot;;

- &#39;_```xlink:href```_&#39; dell&#39;elemento _```gml:unitsSystem```_. Il valore dell&#39;attributo deve essere [_http://www.bipm.org/en/si_](http://www.bipm.org/en/si).

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dtataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_AbsoluteExternalPositionalAccuracy>
          <gmd:result>
            <gmd:DQ_QuantitativeResult>
              <gmd:valueUnit>
                <gml:BaseUnit gml:id="m">
                  <gml:identifier codeSpace="http://www.bipm.org/en/si/base_units">m</gml:identifier>
                  <gml:unitsSystem xlink:href="http://www.bipm.org/en/si"/>
                </gml:BaseUnit>
              </gmd:valueUnit>
              <gmd:value>
                <gco:Record>
                  <gco:Real>0.30</gco:Real>
                </gco:Record>
              </gmd:value>
            </gmd:DQ_QuantitativeResult>
          </gmd:result>
        </gmd:DQ_AbsoluteExternalPositionalAccuracy>
      </gmd:report>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```

### 3.4.3 Coerenza topologica

|  |  |
| --- | --- |
| **Nome elemento** | Coerenza topologica |
| **Riferimento** | [LG RNDT] – tab. I-35 |
| **Molteplicità** | [0..\*] |
| **Elemento INSPIRE** | Coerenza topologica |
| **Definizione** | Esattezza delle caratteristiche topologiche esplicitamente codificate del set di dati, come descritte nel campo di applicazione. |
| **Istruzioni di implementazione** | Questo elemento è obbligatorio solo se il set di dati comprende tipi del modello generico di rete (Generic Network Model) e non assicura la topologia delle linee di mezzeria (ossia la connettività delle linee di mezzeria).La coerenza topologica può essere riportata attraverso i risultati delle verifiche fatte sui dati che possono essere o quantitativi o descrittivi. |

**REQUISITO 2.7** - **```metadata/2.0/req/isdss/topological-consistency-quantitative-results```**

I risultati quantitativi delle misure di coerenza topologica devono essere riportati utilizzando l&#39;elemento _```gmd:report/gmd:DQ_TopologicalConsistency/gmd:result/gmd:DQ_QuantitativeResult```_.

La molteplicità di questo elemento è 0..N.

Il valore numerico o comunque quantitativo della misura di coerenza topologica deve essere fornito come:

- **unità di misura** , attraverso l&#39;elemento _```gmd:valueUnit```_;

- **valore** , attraverso l&#39;elemento _```gmd:value/gco:Record```_.

Il tipo dell&#39;elemento _```gmd:value/gco:Record```_ deve essere scelto sulla base del tipo di risultato della specifica misura e deve essere dichiarato attraverso l&#39;attributo _```xsi:type```_ dell&#39;elemento _```gco:Record```_.

---

***Raccomandazione 2.2** - **```metadata/2.0/rec/isdss/topological-consistency-measure-name```***

*Il nome della misura della coerenza topologica dovrebbe essere indicato attraverso l&#39;elemento ```gmd:DQ_TopologicalConsistency/gmd:nameOfMeasure```.*

*Nel caso in cui il risultato è relativo a più di una misura, dovrebbe essere indicato un elemento ```gmd:nameOfMeasure``` separato per ogni misura inclusa.*

---

***Raccomandazione 2.3** - **```metadata/2.0/rec/isdss/topological-consistency-evaluation-method```***

*Si raccomanda di fornire una breve descrizione del metodo di valutazione utilizzato per la verifica della coerenza topologica attraverso l&#39;elemento ```gmd:DQ_TopologicalConsistency/gmd:evaluationMethodDescription```.*

*Qualora applicabile, il tipo di metodo di valutazione dovrebbe essere dichiarato utilizzando l&#39;elemento ```gmd:DQ_TopologicalConsistency/gmd:evaluationMethodType/gmd:DQ_EvaluationMethodTypeCode``` con riferimento a uno dei valori dell&#39;elenco di codici ISO ```DQ_EvaluationMethodTypeCode```.*

---

***Raccomandazione 2.4** - **```metadata/2.0/rec/isdss/topological-consistency/date```***

*Si raccomanda di fornire la data della valutazione della coerenza topologica attraverso l&#39;elemento ```gmd:DQ_TopologicalConsistency/gmd:dateTime/gco:DateTime```.*

*Il valore deve essere espresso utilizzando il calendario Gregoriano e in conformità allo Standard ISO 8601.*

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_TopologicalConsistency>
          <gmd:nameOfMeasure>
            <gco:CharacterString>numero di connessioni punto-curva con errori</gco:CharacterString>
          </gmd:nameOfMeasure>
          <gmd:evaluationMethodType>
            <gmd:DQ_EvaluationMethodTypeCode codeList="http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#DQ_EvaluationMethodTypeCode" codeListValue="indirect">Indiretto</gmd:DQ_EvaluationMethodTypeCode>
          </gmd:evaluationMethodType>
          <gmd:evaluationMethodDescription>
            <gco:CharacterString>Esiste una connessione punto-curva dove si toccano diverse curve. Queste curve hanno una relazione topologica intrinseca che deve riflettere la vera costellazione di punti. Se non è così, la connessione punto-curva presenta errori rispetto alla misura della qualità dei dati. Tale misura tiene conto del numero di errori di questo tipo.</gco:CharacterString>
          </gmd:evaluationMethodDescription>
          <gmd:dateTime>
            <gco:DateTime>2015-04-01T16:20:00</gco:DateTime>
          </gmd:dateTime>
          <gmd:result>
            <gmd:DQ_QuantitativeResult>
              <gmd:valueUnit xlink:href="http://www.opengis.net/def/uom/OGC/1.0/unity"/>
              <gmd:value>
                  <gco:Record xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:integer">12</gco:Record>
              </gmd:value>
            </gmd:DQ_QuantitativeResult>
          </gmd:result>
        </gmd:DQ_TopologicalConsistency>
      </gmd:report>
      …
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```

### 3.4.4 Genealogia

|  |  |
| --- | --- |
| **Nome elemento** | Genealogia |
| **Riferimento** | [LG RNDT] – tab. I-36 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Genealogia |
| **Definizione** | Testo descrittivo sulla storia del processo e/o la qualità generale del set di dati. |
| **Istruzioni di implementazione** | Testo libero. |

**REQUISITO 1.11** - **```metadata/2.0/req/datasets-and-series/lineage```**

La genealogia deve essere documentata (con riferimento all&#39;intera risorsa, dataset o serie di dataset, come specificato nel Requisito [1.9](#1.9)) attraverso l&#39;elemento _```gmd:dataQualityInfo/gmd:DQ_DataQuality/gmd:lineage/gmd:LI_Lineage/gmd:statement```_.

Si consiglia di utilizzare l&#39;elemento per descrivere la provenienza e il processo di produzione dei dati, fornendo informazioni sulla storia e il ciclo di vita, dalla rilevazione e l&#39;acquisizione fino alla forma attuale.

La molteplicità di questo elemento è 1.

---

***Raccomandazione 1.12** - **```metadata/2.0/rec/datasets-and-series/use-iso-dq-elements-and-measures```***

*Se il fornitore dei dati ha una propria procedura per la gestione della qualità dei dati, allora dovrebbero essere utilizzati gli appositi elementi previsti da ISO per valutare e riferire, nei metadati, i risultati sulla qualità dei dati, in aggiunta all&#39;elemento Genealogia.*

---

***Raccomandazione 1.13** - **```metadata/2.0/rec/datasets-and-series/lineage-avoid-acronyms```***

*Dovrebbe essere evitato l&#39;uso di abbreviazioni, inclusi gli acronimi. Se utilizzati, dovrebbe essere illustrato il loro significato.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dtataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:lineage>
        <gmd:LI_Lineage>
          <gmd:statement>
            <gco:CharacterString>La produzione di ortofoto digitali alla scala 1:10.000, si compone delle seguenti fasi operative: scansione dei fotogrammi; rete di inquadramento e di appoggio; triangolazione aerea; allestimento del DTM; ortorettifica. Le ortofoto vengono riprodotte almeno ogni tre anni.</gco:CharacterString>
          </gmd:statement>
        </gmd:LI_Lineage>
      </gmd:lineage>
    </gmd:DQ_DataQuality>
  </gmd:dataQualityInfo>
  …
</gmd:MD_Metadata>
```

### 3.4.5 Conformità: specifiche

|  |  |
| --- | --- |
| **Nome elemento** | Conformità: specifiche |
| **Riferimento** | [LG RNDT] – tab. I-37 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Conformità - specifica |
| **Definizione** | Citazione delle specifiche INSPIRE (adottate a norma dell&#39;art. 7 par. 1 della direttiva 2007/2/CE) cui la risorsa si conforma. |
| **Istruzioni di implementazione** | - **Titolo** [1] – Testo libero; - **Data** [1] – utilizzare il formato previsto dallo Standard ISO 8601: _aaaa-mm-gg_; - **Tipo data** [1] **–** Il valore da inserire, tratto dall&#39;elenco di codici &quot;_CI\_DateTypeCode_&quot; (§ 4.2.3.3 [LG RNDT]), è &quot;_pubblicazione_&quot; (_publication_). Nel tracciato XML è presente anche un ulteriore elemento (che è obbligatorio per gli schemi XSD ma che non è richiesto nè da INSPIRE nè dal RNDT): &quot;_explanation_&quot;. Valorizzare tale elemento come da esempio XML. |

**REQUISITO 1.10** - **```metadata/2.0/req/datasets-and-series/conformity```**

Nei metadati deve essere dichiarata la conformità alle disposizioni di esecuzione INSPIRE per l&#39;interoperabilità di dataset e serie di dataset attraverso l&#39;elemento _```gmd:report/gmd:DQ_DomainConsistency/gmd:result/gmd:DQ_ConformanceResult```_ come specificato nel Requisito [C.20](../common/data-quality.md#C.20).

Questo elemento deve contenere la citazione del [Regolamento 1089/2010] nelle modalità stabilite nel Requisito [C.21](../common/data-quality.md#C.21).

Deve essere indicato, inoltre, il grado di conformità come stabilito con il Requisito [C.22](../common/data-quality.md#C.22).

---

**REQUISITO R1.8** - **```rndt/metadata/2.0/req/datasets-and-series/regulation-citation```**

Le informazioni relative al [Regolamento 1089/2010] da inserire sono le seguenti:

**Titolo** : _REGOLAMENTO (UE) N. 1089/2010 DELLA COMMISSIONE del 23 novembre 2010 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda l&#39;interoperabilità dei set di dati territoriali e dei servizi di dati territoriali_

**Data** : _2010-12-08_

**Tipo data** : _pubblicazione_.

---

***Raccomandazione 1.10** - **```metadata/2.0/rec/datasets-and-series/uri-for-regulation-1089-2010```***

*Se il titolo delle disposizioni di esecuzione viene indicato attraverso l&#39;elemento ```gmx:Anchor```, per fare riferimento al Regolamento INSPIRE n. 1089/2010 dovrebbe essere utilizzato il seguente URI:*

*[_http://data.europa.eu/eli/reg/2010/1089_](http://data.europa.eu/eli/reg/2010/1089).*

---

***Raccomandazione 1.11** - **```metadata/2.0/rec/datasets-and-series/uris-for-ats-and-cc```***

*Se la conformità ad un ATS (Abstract Test Suite) o a una classe di conformità viene dichiarata utilizzando l&#39;elemento ```gmx:Anchor```, l&#39;URI che identifica l&#39;ATS o la classe di conformità dovrebbe essere utilizzato come valore dell&#39;attributo ```xlink:href``` dell&#39;elemento relativo al titolo della specifica.*

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:dataQualityInfo>
    <gmd:DQ_DataQuality>
    …
      <gmd:report>
        <gmd:DQ_DomainConsistency>
          <gmd:result>
            <gmd:DQ_ConformanceResult>
              <gmd:specification>
                <gmd:CI_Citation>
                  <gmd:title>
                    <gco:CharacterString>REGOLAMENTO (UE) N. 1089/2010 DELLA COMMISSIONE del 23 novembre 2010 recante attuazione della direttiva 2007/2/CE del Parlamento europeo e del Consiglio per quanto riguarda l'interoperabilità dei set di dati territoriali e dei servizi di dati territoriali</gco:CharacterString>
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

```xml
<gmd:MD_Metadata>
  …
  <gmd:dataQualityInfo>
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
              <gmd:pass gco:nilReason="unknown"/>
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
