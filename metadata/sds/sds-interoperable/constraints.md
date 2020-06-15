### 4.4.2 Vincoli


#### 4.4.2.1 Vincoli di fruibilità

| **Nome elemento** | **Vincoli di fruibilità** |
| --- | --- |
| **Nome elemento** | Vincoli di fruibilità |
| **Riferimento** | [LG RNDT] – tab. V-24 |
| **Molteplicità** | [1..\*] |
| **Elemento INSPIRE** | Condizioni applicabili all&#39;accesso e all&#39;uso |
| **Definizione** | Condizioni applicabili all&#39;accesso e all&#39;uso dei set di dati territoriali e ai relativi servizi e, dove applicabile, ai canoni corrispondenti, a norma dell&#39;articolo 5, comma 2, lettera b), e dell&#39;articolo 11, comma 2, lettera f), della Direttiva 2007/2/CE. |
| **Istruzioni di implementazione** | Devono essere forniti i seguenti elementi: - _gmd:accessConstraints_ oppure _gmd:useConstraints_ con valore &quot;Altri vincoli&quot; (otherRestrictions) dell&#39;elenco di codici &quot;_MD\_RestrictionCode_&quot; (§ 4.2.3.12 [LG RNDT]); - _gmd:otherConstraints_ con testo libero.|

**REQUISITO 6.3** - **```metadata/2.0/req/sds-interoperable/conditions-applying-to-access-and-use```**

I vincoli tecnici applicabili all&#39;accesso e all&#39;uso di un servizio di dati territoriali interoperabile devono essere specificati come indicato dal Requisito [C.18](../../common/constraints.md#C.18).

La molteplicità dell&#39;elemento _```gmd:resourceConstraints/gmd:MD_LegalConstraints```_ per lo scopo di cui sopra è 1..N.

Queste informazioni possono essere combinate nello stesso elemento _```gmd:resourceConstraints```_ utilizzato per descrivere i vincoli non tecnici applicabili all&#39;accesso e all&#39;uso del servizio di dati territoriali.

---

**Esempio di XML:**

V. [esempio](../../common/constraints.md#243-vincoli-di-fruibilità)

---

> Vai a [**4.4.3 Informazioni sulla qualità dei servizi**](quality.md)
