---
title: Interface do DSTU2 de integração do EHR e aplicativo pacientes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba mais sobre a especificação de interface DSTU2 no Teams, incluindo configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Microsoft Teams pacientes.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772202"
---
# <a name="dstu2-interface-specification"></a>Especificação de interface DSTU2

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente. Confira o modelo pacientes em listas para começar. Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md)

A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar. O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Aguarde](#patient)
- [Observações](#observation)
- [Condição](#condition)
- [Encontrá](#encounter)
- [Allergy intolerância](#allergyintolerance)
- [Análise](#coverage)
- [Pedido de medicação](#medication-order)
- [Local](#location)

> [!NOTE]
> O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado. No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.

Consultas do aplicativo Microsoft Teams pacientes para mais de um recurso poste um pacote (lote) de solicitações para a URL do servidor FHIR. O servidor processa cada solicitação e retorna um pacote dos recursos correspondentes a cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Todos os recursos de FHIR a seguir devem ser acessíveis pela referência a recursos diretos.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos obrigatórios mínimos de conformidade

 O servidor FHIR deve implementar a instrução de conformidade para que possamos ter um resumo factual de seus recursos. Esperamos os parâmetros a seguir em um servidor FHIR DSTU2:

 - DEIXAR

    - Modo
    - Haja
    - Recurso: tipo
    - Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotá-lo como suporte a várias versões.)

Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="patient"></a>Aguarde

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de [perfil do paciente do Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

 - Nome. família
 - Nome. fornecido
 - Sexo
 - DataDeNascimento
 - MRN (identificador)

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:

 - Name. Use
 - Name. Prefix
 - Cuidado: (essa referência ao recurso do paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:

 - %
 - Family: Contains = (procura por todos os pacientes cujo nome de família contenha o valor.)
 - especificado =\<substring>
 - nome =\<substring>
 - DataDeNascimento = (correspondência exata)
 - \_contagem (número máximo de resultados que devem ser retornados) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a \_ contagem será usada pelo PatientsApp para limitar o número de registros retornados.
 - identificador =\<mrn>

O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:

- ID: essa é a ID do recurso que cada recurso no FHIR tem.
- MRN: esse é o identificador real do paciente que a equipe clínica saberia. Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR
- Nome
- DataDeNascimento

Consulte o exemplo a seguir desta chamada.

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="observation"></a>Observações

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil de sinais Argonaut vital:

 - Efetivo (data e hora ou ponto)
 - Code. Coding. Code
 - Valor de ValueQuantity. valor

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:

 - Code. Coding. display
 - ValueQuantity. unidade

Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id\>
 - classificar: desc =\<field ex. date\>

O objetivo é poder recuperar os mais recentes sinais essenciais para um paciente, [VitalSigns. DSTU. Saz] (observação?).

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="condition"></a>Condição

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. Mostrar

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

 - Data de gravação
 - Gravidade

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>
 - _count =\<max results>

Consulte o seguinte exemplo desta chamada:

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="encounter"></a>Encontrá

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos perfil do núcleo dos EUA "deve ter":

 - Situação
 - Digite [0]. Codificação [0]. Mostrar

Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil principal

 - Período. início
 - Local [0]. Location. display

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>
 - _sort: desc =\<field ex. date>
 - _count =\<max results>

O objetivo é poder recuperar o último local conhecido do paciente. Cada encontro faz referência a um recurso de localização. A referência também incluirá o campo de exibição do local. Consulte o exemplo a seguir desta chamada.

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obter outros detalhes sobre esse conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut AllergyIntolerance:

 - Code. Text
 - Code. Coding [0]. Mostrar
 - Situação

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:

 - RecordedDate
 - Observação. texto
 - Reação [..]. Substância. Text
 - Reação [..]. Manifestação [..]. Textos
 - Text. div

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - Paciente =  \<patient id>

Consulte o seguinte exemplo desta chamada:

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="medication-order"></a>Pedido de medicação

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut MedicationOrder:

 - DateWritten
 - Preparador. exibição
 - Medicação. display (se referência)
 - Medicação. Text (se conceito)

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

 - DateEnded
 - DosageInstruction. Text
 - Text. div

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>
 - _count =\<max results>

Consulte o seguinte exemplo desta chamada:

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="coverage"></a>Análise

Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:

 - Payor

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>

Consulte o seguinte exemplo desta chamada:

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="location"></a>Local

Esse recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .

Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obter outros detalhes sobre esse conjunto de campos.
