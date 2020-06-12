### 4.4.4 Sistema di riferimento


#### 4.4.4.1 Sistema di riferimento spaziale

|  |  |
| --- | --- |
| **Nome elemento** | Sistema di riferimento spaziale |
| **Riferimento** | [LG RNDT] – tab. VI-4 |
| **Molteplicità** | [1..N] |
| **Elemento INSPIRE** | Identificatore di sistemi di riferimento di coordinate |
| **Definizione** | Descrizione del sistema o dei sistemi di riferimento di coordinate utilizzati nel set di dati. |
| **Istruzioni di implementazione** | Testo libero. Fare riferimento all&#39;elenco di codici _MD\_ReferenceSystemCode_ (§ 4.2.3.11 [LG RNDT]) e ai relativi URI di cui alla tabella riportata all&#39;allegato [A.1](#_A.1_MD_ReferenceSystemCode). |

**REQUISITO 6.1** - **```metadata/2.0/req/sds-interoperable/crs```**

Il sistema di riferimento supportato dal servizio di dati territoriali interoperabile deve essere documentato attraverso l&#39;elemento _```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier```_.

La molteplicità dell&#39;elemento è 1..N.

L&#39;elemento _```gmd:RS_Identifier/gmd:code```_ è obbligatorio. L&#39;elemento _```gmd:RS_Identifier/gmd:codeSpace```_ deve essere utilizzato se il codice, da solo, non identifica il sistema di riferimento.

Devono essere utilizzati solo gli identificatori di sistemi di riferimento specificati in un registro comune noto.

---

**REQUISITO R6.2** - **```rndt/metadata/2.0/req/sds-interoperable/crs-http-uris```**

Se il sistema di riferimento è elencato nell&#39;elenco di codici _```MD_ReferenceSystemCode```_ definito nelle Linee Guida e riportato nella tabella di cui al § [A.1](#_A.1_MD_ReferenceSystemCode) dell&#39;allegato A, deve essere utilizzato l&#39;identificatore presente nella colonna URI come valore dell&#39;attributo _```xlink:href```_ dell&#39;elemento _```gmd:referenceSystemInfo/gmd:MD_ReferenceSystem/gmd:referenceSystemIdentifier/gmd:RS_Identifier/gmd:code```_ e il nome (colonna &quot;_Nome breve_&quot;) come valore del tag del medesimo elemento.

In questo caso l&#39;elemento _```gmd:codeSpace```_ non deve essere utilizzato.

---

**Esempio di XML:**

V. [esempi](../../datasets-and-series/reference-system.md#351-sistema-di-riferimento-spaziale)
