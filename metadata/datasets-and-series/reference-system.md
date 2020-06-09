## 3.5 Sistema di riferimento

**Elementi:**

[3.5.1 Sistema di riferimento spaziale](#351-sistema-di-riferimento-spaziale)

[3.5.2 Sistema di riferimento temporale](#352-sistema-di-riferimento-temporale)

### 3.5.1 Sistema di riferimento spaziale

|  |  |
| --- | --- |
| **Nome elemento** | Sistema di riferimento spaziale |
| **Riferimento** | [LG RNDT] – tab. I-39 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Sistema di riferimento di coordinate |
| **Definizione** | Descrizione del sistema o dei sistemi di riferimento di coordinate utilizzati nel set di dati. |
| **Istruzioni di implementazione** | Testo libero. Fare riferimento all&#39;elenco di codici _MD\_ReferenceSystemCode_&#39; (§ 4.2.3.11 [LG RNDT]) e ai relativi URI di cui alla tabella riportata all&#39;allegato [A.1](#_A.1_MD_ReferenceSystemCode). |

**REQUISITO 2.1** - **```metadata/2.0/req/isdss/crs```**

Il sistema di riferimento utilizzato per il dataset o la serie di dataset deve essere documentato attraverso l&#39;elemento _```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier```_.

La molteplicità dell&#39;elemento è 1..N.

L&#39;elemento _```gmd:RS_Identifier/gmd:code```_ è obbligatorio. L&#39;elemento _```gmd:RS_Identifier/gmd:codeSpace```_, invece, deve essere utilizzato se il codice, da solo, non identifica il sistema di riferimento.

Devono essere utilizzati solo gli identificatori di sistemi di riferimento specificati in un registro comune noto.

---

**REQUISITO R2.1** ``` **```rndt/metadata/2.0/req/isdss/crs```**

Per la documentazione dell&#39;elemento, deve essere valorizzato il tag &#39;_```gmd:code```_&#39; con il nome del sistema di riferimento presente nella colonna &#39;_Nome breve_&#39; dell&#39;elenco di codici &#39;_```MD_ReferenceSystemCode```_&#39; di cui al § [A.1](#_A.1_MD_ReferenceSystemCode) dell&#39;allegato A. In alternativa, il tag &quot;_```gmd:code```_&quot; può essere valorizzato con il relativo codice EPSG (v., a questo proposito, la colonna &quot;_Codice EPSG_&quot; della tabella disponibile nel citato § [A.1](#_A.1_MD_ReferenceSystemCode) dell&#39;allegato A) introducendo, in questo caso, anche il tag &quot;_```gmd:codeSpace```_&quot; attraverso il quale indicare l&#39;URL del registro EPSG &quot;[_http://www.epsg-registry.org_](http://www.epsg-registry.org/)&quot;.

---

***Raccomandazione 2.1** ``` **```metadata/2.0/rec/isdss/source-crs```***

*Se il dataset è fornito attraverso un servizio di scaricamento (download) che include funzionalità di trasformazione delle coordinate (che consente di fornire il dataset in tutti i sistemi di riferimento supportati dal servizio), nei metadati dovrebbe essere documentato il sistema di riferimento nativo del dataset.*

---

**REQUISITO R2.2** - **```rndt/metadata/2.0/req/isdss/crs-id```**

Se il sistema di riferimento è presente nell&#39;elenco di codici _```MD_ReferenceSystemCode```_ definito nelle [LG RNDT] e riportato nella tabella di cui all&#39;allegato [A.1](#_A.1_MD_ReferenceSystemCode), deve essere utilizzato l&#39;identificatore presente nella colonna URI come valore dell&#39;attributo _```xlink:href```_ dell&#39;elemento _```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier/gmd:code```_ e il nome (colonna &quot;_Nome breve_&quot;) come valore del tag del medesimo elemento.

---

***Raccomandazione 2.2** - **```metadata/2.0/rec/isdss/srs-using-geographic-identifiers```***

*Anche i sistemi di riferimento che utilizzano identificatori geografici dovrebbero essere identificati utilizzando sempre l&#39;elemento ```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier/gmd:code```. Dovrebbe essere utilizzato un elemento ```gmx:Anchor``` con l&#39;attributo ```xlink:href``` che fa riferimento ad un URI che fornisce ulteriori informazioni sui sistemi di riferimento spaziale che utilizzano identificatori geografici.*

---

**Esempi di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:referenceSystemInfo>
    <gmd:MD_ReferenceSystem>
      <gmd:referenceSystemIdentifier>
        <gmd:RS_Identifier>
          <gmd:code>
            <gco:CharacterString>RDN2008-6704</gco:CharacterString>
          </gmd:code>
        </gmd:RS_Identifier>
      </gmd:referenceSystemIdentifier>
    </gmd:MD_ReferenceSystem>
  </gmd:referenceSystemInfo>
  …
</gmd:MD_Metadata>
```

```xml
<gmd:MD_Metadata>
  …
  <gmd:referenceSystemInfo>
    <gmd:MD_ReferenceSystem>
      <gmd:referenceSystemIdentifier>
        <gmd:RS_Identifier>
          <gmd:code>
            <gco:CharacterString>3004</gco:CharacterString>
          </gmd:code>
          <gmd:codeSpace>
            <gco:CharacterString>http://www.epsg-registry.org/</gco:CharacterString>
          </gmd:codeSpace>
        </gmd:RS_Identifier>
      </gmd:referenceSystemIdentifier>
    </gmd:MD_ReferenceSystem>
  </gmd:referenceSystemInfo>
  …
</gmd:MD_Metadata>
```

```xml
<gmd:MD_Metadata>
  …
  <gmd:referenceSystemInfo>
    <gmd:MD_ReferenceSystem>
      <gmd:referenceSystemIdentifier>
        <gmd:RS_Identifier>
          <gmd:code>
            <gmx:Anchor xlink:href="http://www.opengis.net/def/crs/EPSG/0/6704">RDN2008-6704</gmx:Anchor>
          </gmd:code>
        </gmd:RS_Identifier>
      </gmd:referenceSystemIdentifier>
    </gmd:MD_ReferenceSystem>
  </gmd:referenceSystemInfo>
  …
</gmd:MD_Metadata>
```

### 3.5.2 Sistema di riferimento temporale

|  |  |
| --- | --- |
| **Nome elemento** | Sistema di riferimento temporale |
| **Riferimento** | [LG RNDT] – tab. I-40 |
| **Molteplicità** | [0..N] |
| **Elemento INSPIRE** | Sistema di riferimento temporale |
| **Definizione** | Descrizione del sistema o dei sistemi di riferimento temporali utilizzati nel set di dati. |
| **Istruzioni di implementazione** | Testo libero. Deve essere documentato solo se il dataset o la serie di dataset contiene informazioni temporali che non si riferiscono al sistema di riferimento temporale predefinito, cioè il calendario gregoriano. |

**REQUISITO 2.3** - **```metadata/2.0/req/isdss/temportal-rs```**

Il sistema di riferimento temporale utilizzato nel dataset o nella serie di dataset deve essere indicato attraverso l&#39;elemento _```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier```_.

La molteplicità di questo elemento è 0..N.

L&#39;elemento _```gmd:RS_Identifier/gmd:code```_ è obbligatorio. L&#39;elemento _```gmd:RS_Identifier/gmd:codeSpace```_ deve essere utilizzato se il codice, da solo, non identifica il sistema di riferimento.

---

***Raccomandazione 2.1** - **```metadata/2.0/rec/isdss/temporal-rs-id```***

*Se in un registro comune è disponibile un identificatore univoco noto per il sistema di riferimento temporale, tale identificatore dovrebbe essere utilizzato come valore dell&#39;elemento ```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier/gmd:code```.*

---

**Esempio di XML:**

```xml
<gmd:MD_Metadata>
  …
  <gmd:referenceSystemInfo>
    <gmd:MD_ReferenceSystem>
      <gmd:referenceSystemIdentifier>
        <gmd:RS_Identifier>
          <gmd:code>
            <gco:CharacterString>Calendario Giuliano</gco:CharacterString>
          </gmd:code>
        </gmd:RS_Identifier>
      </gmd:referenceSystemIdentifier>
    </gmd:MD_ReferenceSystem>
  </gmd:referenceSystemInfo>
  …
</gmd:MD_Metadata>
```
