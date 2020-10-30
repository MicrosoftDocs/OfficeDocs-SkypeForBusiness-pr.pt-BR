---
title: Interface do STU3 de integração do EHR e aplicativo pacientes
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
description: Saiba como integrar registros de saúde eletrônicas ao aplicativo Microsoft Teams pacientes e à especificação de interface STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803489"
---
# <a name="stu3-interface-specification"></a>Especificação de interface STU3

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe. Todos os dados associados ao aplicativo pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente. Confira o modelo pacientes em listas para começar. Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).

A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar. O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Aguarde](#patient)
- [Observações](#observation)
- [Condição](#condition)
- [Encontrá](#encounter)
- [Allergy intolerância](#allergyintolerance)
- [Análise](#coverage)
- [Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)
- Local (as informações necessárias deste recurso podem ser incluídas em encontrar)

> [!NOTE]
> O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.

As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR. O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Declaração de recursos

Estes são os campos mínimos obrigatórios:

 - DEIXAR

    - Modo
    - Haja
    - Recurso: tipo
    - Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)

Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="patient"></a>Aguarde

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:

 - Nome. fornecido
 - Nome. família
 - Sexo
 - DataDeNascimento
 - MRN (identificador)

Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

 - Name. Use
 - Name. Prefix
 - [GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)

Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:

 - %
 - Family = (procura por todos os pacientes cujo nome de família contenha o valor)
 - especificado =\<substring>
 - DataDeNascimento = (correspondência exata)
 - Gênero = (valores sendo um dos sexo administrativos)
 - \_contagem (número máximo de resultados que devem ser retornados) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e da \_ contagem que será usado pelo PatientsApp para limitar o número de registros retornados.
 - identificador =\<mrn>

O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:

- ID: essa é a ID do recurso que cada recurso no FHIR tem.
- MRN: esse é o identificador real do paciente que a equipe clínica saberia. Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.
- Nome
- DataDeNascimento

Consulte o seguinte exemplo da chamada:

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="observation"></a>Observações

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de Vital-Signs Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

 - Efetivo (data e hora ou ponto)
 - Code. Coding. Code
 - Valor de ValueQuantity. valor

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

 - Code. Coding. display
 - ValueQuantity. unidade

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>
 - _sort =-data
 - Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.

Consulte este exemplo da chamada:

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="condition"></a>Condição

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

 - Code. Coding [0]. Mostrar

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

 - AssertedDate
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="encounter"></a>Encontrá

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .

 - Situação
 - Digite [0]. Codificação [0]. Mostrar

Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:

 - Período. início
 - Local [0]. Location. display

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>
 - _sort: desc =\<field ex. date>
 - _count =\<max results>

O objetivo é poder recuperar o último local conhecido do paciente. Cada encontro faz referência a um recurso de localização. A referência também incluirá o campo de exibição do local.

Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

 - Code. Text
 - Code. Coding [0]. Mostrar
 - ClinicalStatus/VerificationStatus (Lemos)

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:

 - AssertedDate
 - Observação. texto
 - Reação
    - Substância (um elemento de codificação)
    - Manifestação (um elemento de codificação)

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - Paciente =  \<patient id>

Consulte o seguinte exemplo da chamada: 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="medication-request"></a>Solicitação de medicação

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

 - Medicação. display (se referência)
 - Medicação. Text (se CodableConcept)
 - AuthoredOn
 - Solicitante. Agent. display

Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:

 - DosageInstruction[..]. Textos
 - Textos

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente =\<patient id>
 - _count =\<max results>

Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="coverage"></a>Análise

Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:

 - Agrupamento, pelo menos um elemento com
    - GroupDisplay
    - PlanDisplay
 - Período
 - Subscriberid

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - Paciente = \<patient id>

Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.
