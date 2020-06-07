## 2.4 Vincoli si dati

** Elementi: **

[2.4.1 Limitazione d'uso](constraints.md#241-limitazione-duso)

2.4.2 Vincoli di accesso

2.4.3 Vincoli di fruibilità

### 2.4.1 Limitazione d&#39;uso

|  |  |
| --- | --- |
| **Nome elemento** | Limitazione d&#39;uso |
| **Riferimento** | [LG RNDT] – tab. I-26, tab. V-22, tab. VII-19 |
| **Molteplicità** | [0..1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Restrizioni di utilizzo dei dati. |
| **Istruzioni di implementazione** | Testo libero. |

***Raccomandazione RC.12** - **```rndt/metadata/2.0/rec/common/use-limitation```***

*L&#39;elemento ```gmd:resourceConstraints/gmd:MD_Constraints/gmd:useLimitation``` può essere utilizzato per indicare eventuali limitazioni che incidono sull&#39;idoneità all&#39;uso della risorsa documentata.*

*La molteplicità dell&#39;elemento è 0..1.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:resourceConstraints>
        <gmd:MD_Constraints>
          <gmd:useLimitation>
            <gco:CharacterString>L’utilizzo è limitato solo ai Comuni</gco:CharacterString>
          </gmd:useLimitation>
          …
        </gmd:MD_Constraints>
      </gmd:resourceConstraints>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

### Vincoli di accesso

|  |  |
| --- | --- |
| **Nome elemento** | Vincoli di accesso |
| **Riferimento** | [LG RNDT] – tab. I-27, tab. V-23 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Vincoli per l&#39;accesso pubblico |
| **Definizione** | Informazioni sulle limitazioni e le relative motivazioni imposte all&#39;accesso pubblico ai set di dati territoriali e ai servizi a essi relativi a norma dell&#39;articolo 13 della Direttiva 2007/2/CE. |
| **Istruzioni di implementazione** | Devono essere forniti i seguenti elementi: - _gmd:accessConstraints_ con valore &quot;Altri vincoli&quot; (otherRestrictions) dell&#39;elenco di codici &quot;_MD\_RestrictionCode_&quot; (§ 4.2.3.12 [LG RNDT]); - _gmd:otherConstraints_ con testo libero. |

**REQUISITO C.17** - **```metadata/2.0/req/common/limitations-on-public-access```**

I vincoli per l&#39;accesso pubblico (o la mancanza di tali vincoli) per la risorsa descritta devono essere indicati utilizzando uno ed un solo elemento _```gmd:resourceConstraints/gmd:MD_LegalConstraints```_. Questo elemento non deve essere lo stesso utilizzato per descrivere i vincoli di fruibilità - condizioni applicabili all&#39;accesso e all&#39;uso (vedi § [2.4.3](#_Vincoli_di_fruibilit%C3%A0)).

Per indicare i vincoli per l&#39;accesso pubblico basati sui motivi di cui alla lettera (a) o alle lettere da (c) ad (h) dell&#39;art. 13 paragrafo 1 della Direttiva INSPIRE, l&#39;elemento _```gmd:resourceConstraints/gmd:MD_LegalConstraints```_ deve includere una combinazione di:

- una istanza dell&#39;elemento _```gmd:accessConstraints/gmd:MD_RestrictionCode```_ con il valore &quot;Altri vincoli&quot; (&quot;otherRestrictions&quot;) presente nell&#39;elenco di codici ISO _```MD_RestrictionCode```_;

- almeno una istanza di _```gmd:otherConstraints/gmx:Anchor```_ con l&#39;attributo _```xlink:href```_ riferito all&#39;URI di uno dei valori dell&#39;elenco di codici _```LimitationsOnPublicAccess```_ definito nel relativo [registro pubblicato nel Sistema di Registri INSPIRE](http://inspire.ec.europa.eu/metadata-codelist/LimitationsOnPublicAccess). Se non ci sono vincoli all&#39;accesso pubblico, l&#39;elemento deve puntare al valore &quot;_noLimitations_&quot; dell&#39;elenco di codici di cui sopra.

---

***Raccomandazione RC.13** - **```rndt/metadata/2.0/rec/common/security-constraints```***

*Nel caso in cui i vincoli per l&#39;accesso pubblico sono basati sui motivi di cui alla lettera (b) dell&#39;art. 13 paragrafo 1 della [Direttiva INSPIRE], si può utilizzare l&#39;elemento ```gmd:resourceConstraints/gmd:MD_SecurityConstraints/gmd:classification/gmd:MD_ClassificationCode``` con riferimento all&#39;elenco di codici ```MD_ClassificationCode```.*

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:resourceConstraints>
      …
        <gmd:MD_LegalConstraints>
          <gmd:accessConstraints>
            <gmd:MD_RestrictionCode codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_RestrictionCode" codeListValue="otherRestrictions">altri vincoli</gmd:MD_RestrictionCode>
          </gmd:accessConstraints>
          <gmd:otherConstraints>
            <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/LimitationsOnPublicAccess/INSPIRE_Directive_Article13_1a">Accesso pubblico limitato ai sensi dell'articolo 13, paragrafo 1, lettera a), della direttiva INSPIRE</gmx:Anchor>
          </gmd:otherConstraints>
        </gmd:MD_LegalConstraints>
      </gmd:resourceConstraints>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```

```xml
<gmd:MD_Metadata>
…
  <gmd:identificationInfo>
    <gmd:MD_DataIdentification>
    …
      <gmd:resourceConstraints>
      …
        <gmd:MD_LegalConstraints>
          <gmd:accessConstraints>
            <gmd:MD_RestrictionCode codeList=" http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#MD_RestrictionCode" codeListValue="otherRestrictions">altri vincoli</gmd:MD_RestrictionCode>
          </gmd:accessConstraints>
          <gmd:otherConstraints>
            <gmx:Anchor xlink:href="http://inspire.ec.europa.eu/metadata-codelist/LimitationsOnPublicAccess/noLimitations">Nessun vincolo all’accesso pubblico</gmx:Anchor>
          </gmd:otherConstraints>
        </gmd:MD_LegalConstraints>
      </gmd:resourceConstraints>
      …
    </gmd:MD_DataIdentification>
  </gmd:identificationInfo>
…
</gmd:MD_Metadata>
```
