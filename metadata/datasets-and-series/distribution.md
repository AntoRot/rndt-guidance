## 3.6 Distribuzione dei dati

**Elementi:**

3.6.1 Formato di distribuzione

3.6.2 Distributore

3.6.3 Risorsa on-line


### 3.6.1 Formato di distribuzione

|  |  |
| --- | --- |
| **Nome elemento** | Formato di distribuzione |
| **Riferimento** | [LG RNDT] – tab. I-41 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Codifica |
| **Definizione** | Descrizione del concetto (o dei concetti) del linguaggio informatico che specifica la rappresentazione degli oggetti di dati in un registro, un file, un messaggio, un supporto di memorizza­ zione o un canale di trasmissione. |
| **Istruzioni di implementazione** | - **Nome formato** [1] - Testo libero; - **Versione formato** [1] - Testo libero |

**Requisito 2.6** - **metadata/2.0/req/isdss/data-encoding**

Il formato dei dati deve essere indicato attraverso l&#39;elemento _gmd:distributionFormat/gmd:MD\_Format_.

La molteplicità di questo elemento è 1..N.

Devono essere fornite le seguenti informazioni:

**- nome formato** , attraverso l&#39;elemento _gmd:name_;

**- versione formato** , attraverso l&#39;elemento _gmd:version_.

Se la versione non è nota o se non esiste una versione, l&#39;elemento _gmd:version_ deve essere lasciato vuoto e deve essere utilizzato l&#39;attributo _nil reason_ con il valore &quot;_unknown_&quot; o il valore &quot;_inapplicable_&quot; rispettivamente.

**Raccomandazione R1.9**  **rndt/metadata/2.0/rec/datasets-and-series/use-anchors-for-format**

Il nome del formato può essere indicato anche attraverso l&#39;elemento _gmd:distributionFormat/gmd:MD\_Format/gmd:name/gmx:Anchor_, con l&#39;attributo _xlink:href_ riferito a uno dei valori del registro _INSPIRE media-types_ pubblicato nel Sistema di Registri di INSPIRE.

---

**Esempio di XML:**
