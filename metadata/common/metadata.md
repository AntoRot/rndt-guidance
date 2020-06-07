## 2.2 Informazioni sui metadati

### 2.2.1 Identificatore del file

| **Nome elemento** | **Identificatore del file** |
| --- | --- |
| **Riferimento** | [LG RNDT] – tab. I-1, tab. V-1, tab. VII-1 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Identificatore univoco del file dei metadati. |
| **Istruzioni di implementazione** | Testo libero. |

<a name=RC.3>**REQUISITO RC.3**</a>  **```rndt/metadata/2.0/req/common/file-identifier```**

L&#39;identificatore deve essere codificato utilizzando l&#39;elemento _gmd:MD\_Metadata/gmd:fileIdentifier_.

Esso deve contenere, come prefisso,il **codice iPA** assegnato all&#39;Amministrazione in sede di accreditamento all&#39;_Indice dei domicili digitali delle pubbliche amministrazioni e dei gestori di pubblici servizi (IPA)_.

Il separatore tra il codice iPA e la restante parte dell&#39;identificatore è &quot; **:**&quot; (due punti).

L&#39;identificatore deve essere univoco a livello globale e persistente.

La molteplicità dell&#39;elemento è 1.

---

**Esempio di XML:**

``` xml
<gmd:MD_Metadata>
  <gmd:fileIdentifier>
    <gco:CharacterString>r_campan:000002:20090220:111239</gco:CharacterString>
  </gmd:fileIdentifier>
…
</gmd:MD_Metadata>
```
