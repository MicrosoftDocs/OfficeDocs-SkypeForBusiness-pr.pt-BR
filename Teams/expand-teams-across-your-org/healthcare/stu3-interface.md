---
title: Interface STU3 de integração do Aplicativo Patients e do EHR
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
description: Saiba mais sobre como integrar registros de saúde eletrônica ao aplicativo Pacientes do Microsoft Teams e a especificação de interface STU3.
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
> A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes. Confira o modelo Pacientes em Listas para começar. Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)

Configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Pacientes do Microsoft Teams requer a compreensão de quais dados o aplicativo precisa acessar. O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Paciente](#patient)
- [Observação](#observation)
- [Condição](#condition)
- [Encontro](#encounter)
- [Allergy Intolerance](#allergyintolerance)
- [Cobertura](#coverage)
- [Declaração de](#medication-request) medicamentos (substitui a MedicationOrder na versão DSTU2 do PatientsApp)
- Local (as informações necessárias desse recurso podem ser incluídas no Encounter)

> [!NOTE]
> O recurso Paciente é o único recurso obrigatório (sem o qual o aplicativo não será carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para a melhor experiência do usuário final com o aplicativo Pacientes do Microsoft Teams.

As consultas do aplicativo Pacientes do Microsoft Teams para mais de um recurso devem postar um pacote (LOTE) de solicitações à URL do servidor FHIR. O servidor processará cada solicitação e retornará um pacote dos recursos de acordo com cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Declaração de Capacidade

Estes são os campos mínimos necessários:

 - Resto

    - Modo
    - Interação
    - Recurso: Digite
    - Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (Nosso código requer isso para entender para qual versão devemos girar.)

Veja [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) outros detalhes sobre esse conjunto de campos.

## <a name="patient"></a>Paciente

Aqui estão os campos mínimos necessários, que são um subconjunto dos campos de perfil do paciente Argonaut:

 - Nome.Dado
 - Name.Family
 - Gênero
 - Nascimento
 - MRN (Identificador)

Além dos campos [Argonaut,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:

 - Name.Use
 - Name.Prefix
 - [GeneralLastctitioner] - A referência GeneralQuectitioner deve ser incluída no recurso Paciente (somente campo de exibição)

Uma pesquisa de recursos usa o método POST em /Patient/_search e os seguintes parâmetros:

 - Id
 - family=(procura todos os pacientes cujo nome da família contém o valor)
 - given=\<substring>
 - birthdate=(exact match)
 - gender=(values being one of the administrative-gender)
 - \_contagem (número máximo de resultados que devem ser retornados) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a contagem será usada pelo PatientsApp para limitar o número \_ de registros retornados.
 - identificador=\<mrn>

O objetivo é poder pesquisar e filtrar um paciente pelo seguinte:

- ID: Esta é a ID de recurso que todos os recursos em FHIR têm.
- MRN: Este é o identificador real do paciente que a equipe médica conheceria. Entendemos que esse MRN se baseia no tipo de identificador dentro do recurso identificador em FHIR.
- Nome
- Nascimento

Veja o exemplo a seguir da chamada:

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

Veja [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) outros detalhes sobre esse conjunto de campos.

## <a name="observation"></a>Observação

Estes são os campos mínimos necessários, que são um subconjunto do perfil [argonaut Vital-Signs.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Efetivo (data ou período)
 - Code.Coding.Code
 - ValueQuantity.Value

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:

 - Code.Coding.Display
 - ValueQuantity.Unit

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>
 - _sort=data
 - (consultaremos "categoria=sinais vitais") para recuperar a lista de sinais vitais.

Confira este exemplo da chamada:

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

Veja [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) outros detalhes sobre esse conjunto de campos.

## <a name="condition"></a>Condição

Aqui estão os campos mínimos necessários, que são um subconjunto do perfil [de condição Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Exibir

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:

 - AssertedDate
 - Gravidade

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>
 - _count=\<max results>

Veja o exemplo a seguir desta chamada:

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

Veja [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) outros detalhes sobre esse conjunto de campos.

## <a name="encounter"></a>Encontro

Esses são os campos mínimos necessários, que são um subconjunto dos campos de perfil "deve ter" do perfil [Do Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) dos EUA).

 - Status
 - Digite[0]. Codificação[0]. Exibir

Além disso, os campos a seguir dos campos "deve ser suportado" do perfil do Us Core Encounter:

 - Ponto.Início
 - Local[0]. Local.Display

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

O objetivo é recuperar o último local conhecido do paciente. Cada encontro faz referência a um recurso de localização. A referência também incluirá o campo de exibição do local.

Veja [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) outros detalhes sobre esse conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos mínimos necessários, que são um subconjunto do perfil [Argonaut AllergyIntolerance:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)

 - Code.Text
 - Code.Coding[0]. Exibir
 - ClinicalStatus/VerificationStatus (lemos ambos)

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler o seguinte campo:

 - AssertedDate
 - Texto.anotação
 - Reação
    - Emotivo (um elemento de codificação)
    - Demonstração (um elemento de codificação)

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - Paciente =  \<patient id>

Veja o exemplo a seguir da chamada: 

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

Veja [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) outros detalhes sobre esse conjunto de campos.

## <a name="medication-request"></a>Solicitação de medicamentos

Estes são os campos mínimos necessários, que são um subconjunto do perfil [Us Core Medication Request](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

 - Medication.Display (se Referência)
 - Medication.Text (if CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Além dos campos Us Core, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:

 - DeMoscarInstrução[..]. Texto
 - Texto

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>
 - _count=\<max results>

Veja [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) outros detalhes sobre esse conjunto de campos.

## <a name="coverage"></a>Cobertura

Estes são os campos mínimos necessários, não cobertos por perfis Us Core ou Argonaut:

 - Agrupamento, pelo menos um elemento com
    - GroupDisplay
    - PlanDisplay
 - Período
 - SubscriberId

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - Paciente = \<patient id>

Veja [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) outros detalhes sobre esse conjunto de campos.
