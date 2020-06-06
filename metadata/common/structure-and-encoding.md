## 2.1 Struttura e codifica dei metadati

<a name=C.1>**Requisito C.1** </a>- **```metadata/2.0/req/common/xml-schema```**

I record di metadati devono essere codificati in formato XML conforme ad uno dei seguenti schemi XSD:

- [CSW2 AP ISO] XML Schema,

- [ISO 19139] XML Schema disponibile nel repository ISO,

- [ISO 19139] XML Schema disponibile nel repository degli schemi OGC.

Tutti e tre gli schemi indicati dichiarano lo stesso namespace [_http://www.isotc211.org/2005/gmd_](http://www.isotc211.org/2005/gmd).

Per i servizi deve essere utilizzato lo schema XSD disponibile nel repository degli schemi OGC. Questo schema rappresenta l&#39;implementazione XML dello Standard [ISO 19119] per i metadati dei servizi e dichiara il namespace [_http://www.isotc211.org/2005/srv_](http://www.isotc211.org/2005/srv).

---

<a name=C.2>**Requisito C.2**</a> - **```metadata/2.0/req/common/root-element```**

I metadati per dataset, serie di dataset e servizi devono essere codificati utilizzando uno ed un solo elemento _gmd:MD\_Metadata_ come specificato nelle regole di cui agli schemi XSD e nei Requisiti delle Classi di Conformità definiti in questa guida operativa.

Inoltre, a meno di diversa indicazione negli schemi XSD e in questa guida operativa, devono essere seguiti i requisiti definiti dagli Standard ISO 19115, ISO 19119 e ISO TS 19139.

---

<a name=RC.1>**Requisito RC.1**</a> - **```rndt/metadata/2.0/req/common/non-empty-content```**

All'interno del file XML, il tag corrispondente a ciascun elemento deve essere obbligatoriamente valorizzato. Ciò significa che la presenza del tag nel file XML, senza che questo sia opportunamente valorizzato, non garantisce la validità del file stesso, sebbene non sia comunque inficiata la validazione rispetto agli schemi XSD.

---

Risulta valido, quindi, ai fini del caricamento nel RNDT, il seguente tracciato XML:

``` xml
…
<gmd:organisationName>
<gco:CharacterString>Regione Piemonte</gco:CharacterString>
</gmd:organisationName>
…
```