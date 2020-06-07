## 2.2 Informazioni sui metadati

### 2.2.1 Identificatore del file

|  |  |
| --- | --- |
| **Nome elemento** | Identificatore del file |
| **Riferimento** | [LG RNDT] – tab. I-1, tab. V-1, tab. VII-1 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Nessun elemento corrispondente |
| **Definizione** | Identificatore univoco del file dei metadati. |
| **Istruzioni di implementazione** | Testo libero. |

<a name=RC.3>**REQUISITO RC.3**</a> - **```rndt/metadata/2.0/req/common/file-identifier```**

L&#39;identificatore deve essere codificato utilizzando l&#39;elemento _```gmd:MD\_Metadata/gmd:fileIdentifier```_.

Esso deve contenere, come prefisso,il **codice iPA** assegnato all&#39;Amministrazione in sede di accreditamento all&#39;[_Indice dei domicili digitali delle pubbliche amministrazioni e dei gestori di pubblici servizi (IPA)_](https://www.indicepa.gov.it/).

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

### 2.2.2 Lingua dei metadati


| **Nome elemento** | **Lingua dei metadati** |
| --- | --- |
| **Riferimento** | [LG RNDT] – tab. I-2, tab. V-2, tab. VII-2 |
| **Molteplicità** | [1] |
| **Elemento INSPIRE** | Lingua dei metadati |
| **Definizione** | Linguaggio nel quale sono espressi i metadati. |
| **Istruzioni di implementazione** | L&#39;elenco di codici per le 24 lingue ufficiali della UE, da utilizzare per valorizzare l&#39;elemento, è il seguente (elenco basato sui codici a tre lettere di ISO 639-2/B come definito all&#39;indirizzo [http://www.loc.gov/standards/iso639-2/](http://www.loc.gov/standards/iso639-2/)): Bulgaro – **bul**, Ceco – **cze**, Croato - **hrv**, Danese – **dan**, Estone – **est**, Finlandese – **fin**, Francese – **fre**, Greco – **gre**, Inglese – **eng**, Irlandese – **gle**, Italiano – **ita**, Lettone – **lav**, Lituano – **lit**, Maltese – **mlt**, Olandese – **dut**, Polacco – **pol**, Portoghese – **por**, Rumeno – **rum**, Slovacco – **slo**, Sloveno – **slv**, Spagnolo – **spa**, Svedese - **swe**, Tedesco – **ger**, Ungherese – **hun**. La lingua di default per i metadati RNDT è, ovviamente, l&#39; **italiano** ( **ita** ). L&#39;elenco di tutti i codici (compresi quelli delle lingue regionali) è disponibile all&#39;indirizzo [http://www.loc.gov/standards/iso639-2/](http://www.loc.gov/standards/iso639-2/). |

<a name=C.5>**REQUISITO C.5**</a> - **metadata/2.0/req/common/metadata-language-code**

La lingua del contenuto dei metadati deve essere fornita attraverso l&#39;elemento _```gmd:MD\_Metadata/gmd:language/gmd:LanguageCode```_ che deve puntare a uno dei codici a tre lettere delle lingue dell&#39;elenco ISO 639-2/B.

Devono essere usati solo i valori delle lingue ufficiali dell&#39;Unione Europea.

La molteplicità dell&#39;elemento è 1.

---

<a name=RC.4>**REQUISITO RC.4**</a> - **rndt/metadata/2.0/req/common/metadata-language-name**

Il valore del tag dell&#39;elemento _```gmd:MD\_Metadata/gmd:language/gmd:LanguageCode```_ deve riportare lo stesso codice a tre lettere presente nell&#39;attributo _```codeListValue```_.

---

**Esempio di XML:**

``` xml
<gmd:MD_Metadata>
…
  <gmd:language>
    <gmd:LanguageCode codeList="http://www.loc.gov/standards/iso639-2/" codeListValue="ita">ita</gmd:LanguageCode>
  </gmd:language>
…
</gmd:MD_Metadata>
```
