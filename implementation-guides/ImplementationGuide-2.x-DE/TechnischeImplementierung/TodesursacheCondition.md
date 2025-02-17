## Todesursache (Condition)

---

Dieses Profil beschreibt den Todesursache der PatientIn als Element des Kerndatensatzes Medizininformatik-Initiative.

@```
from StructureDefinition where url = 'https://www.medizininformatik-initiative.de/fhir/core/modul-person/StructureDefinition/Todesursache' select Name: name, Canonical: url
```

---

**Differential**

{{tree:https://www.medizininformatik-initiative.de/fhir/core/modul-person/StructureDefinition/Todesursache, diff}}

---

**Hinweise**

| FHIR-Element | Erklärung |
|--------------|-----------|
| Condition.id      | Must-support, jedoch optional       |
| Condition.meta       | Must-support, jedoch optional         |
| Condition.meta.profile       | Verpflichtend für die Abfrage im DIZ-Repsoitory inkl Versionsnummer des Profils. Siehe {{pagelink:ImplementationGuide-2.x/TechnischeImplementierung/CapabilityStatement.md}}. In allen anderen Fällen optional.         |
| Condition.category       | Fixed LOINC und SNOMED-Code, weitere Codings erlaubt.         |
| Condition.code       | Kodierung per ICD-10-WHO erforderlich, weitere Codings erlaubt. Weitere Infos siehe [BFARM](https://www.bfarm.de/DE/Kodiersysteme/Klassifikationen/ICD/ICD-10-WHO/Todesursachenstatistik/_node.html).|
| Condition.subject       | Patientenbezug muss stets gegeben sein.         |

---

**Mapping**

| FHIR-Element | Logischer Datensatz |
|--------------|-----------|
| Condition.code      | Person.Demographie.Vitalstatus.Todesgrund |

---

**Snapshot**

{{tree:https://www.medizininformatik-initiative.de/fhir/core/modul-person/StructureDefinition/Todesursache, snapshot}}

---

**Suchparameter**

Folgende Suchparameter sind für das Modul Person relevant, auch in Kombination:

1. Der Suchparameter "_id" MUSS unterstützt werden:

    Beispiele:

    ```GET [base]/Condition?_id=103270```

    Anwendungshinweise: Weitere Informationen zur Suche nach "_id" finden sich in der [FHIR-Basisspezifikation - Abschnitt "Parameters for all resources"](http://hl7.org/fhir/R4/search.html#all).

1. Der Suchparameter "_profile" MUSS unterstützt werden:

    Beispiele:

    ```GET [base]/Condition?_profile=https://www.medizininformatik-initiative.de/fhir/core/modul-person/StructureDefinition/Todesursache```

    Anwendungshinweise: Weitere Informationen zur Suche nach "_profile" finden sich in der [FHIR-Basisspezifikation - Abschnitt "Parameters for all resources"](http://hl7.org/fhir/R4/search.html#all).


1. Der Suchparameter "category" MUSS unterstützt werden:

    Beispiele:

    ```GET [base]/Condition?category=http://snomed.info/sct|16100001```

    Anwendungshinweise: Weitere Informationen zur Suche nach "Condition.category" finden sich in der [FHIR-Basisspezifikation - Abschnitt "Token Search"](http://hl7.org/fhir/R4/search.html#token).

1. Der Suchparameter "code" MUSS unterstützt werden:

    Beispiele:

    ```GET [base]/Condition?code=http://fhir.de/CodeSystem/bfarm/icd-10-gm|I46.1```

    Anwendungshinweise: Weitere Informationen zur Suche nach "Condition.code" finden sich in der [FHIR-Basisspezifikation - Abschnitt "Token Search"](http://hl7.org/fhir/R4/search.html#token).

1. Der Suchparameter "subject" MUSS unterstützt werden:

    Beispiele:

    ```GET [base]/Observation?subject=Patient/test```

    Anwendungshinweise: Weitere Informationen zur Suche nach "Condition.subject" finden sich in der [FHIR-Basisspezifikation - Abschnitt "reference"](http://hl7.org/fhir/R4/search.html#reference).

1. Der Suchparameter "patient" MUSS unterstützt werden:

    Beispiele:

    ```GET [base]/Observation?patient=Patient/test```

    Anwendungshinweise: Weitere Informationen zur Suche nach "Condition.subject" finden sich in der [FHIR-Basisspezifikation - Abschnitt "reference"](http://hl7.org/fhir/R4/search.html#reference).


---

**Beispiele**

Beispiel (vollständig):

{{json:beispiele/Example-Todesursache.json}}