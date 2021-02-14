---
title: Interface DSTU2 de integração do Aplicativo Patients e EHR
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
description: Saiba mais sobre a especificação de interface DSTU2 no Teams, incluindo a configuração ou reconfiguração de um servidor FHIR para trabalhar com o aplicativo Pacientes do Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803479"
---
# <a name="dstu2-interface-specification"></a>Especificação de interface DSTU2

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes. Confira o modelo Pacientes em Listas para começar. Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)

Configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Pacientes do Microsoft Teams requer a compreensão de quais dados o aplicativo precisa acessar. O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Paciente](#patient)
- [Observação](#observation)
- [Condição](#condition)
- [Encontro](#encounter)
- [Alerância alerância](#allergyintolerance)
- [Cobertura](#coverage)
- [Pedido de medicamentos](#medication-order)
- [Local](#location)

> [!NOTE]
> O recurso Paciente é o único recurso obrigatório (sem o qual o aplicativo não será carregado. No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para a melhor experiência do usuário final com o aplicativo Pacientes do Microsoft Teams.

Consultas do aplicativo Pacientes do Microsoft Teams para mais de um recurso postam um pacote (LOTE) de solicitações à URL do servidor FHIR. O servidor processa cada solicitação e retorna um pacote de recursos de acordo com cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Todos os seguintes recursos FHIR devem estar acessíveis por referência direta de recurso.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos mínimo necessário de conformidade

 O FHIR Server deve implementar a declaração de conformidade para que tenhamos um resumo factual de suas capacidades. Esperamos os parâmetros abaixo em um servidor FHIR DSTU2:

 - Resto

    - Modo
    - Interação
    - Recurso: Digite
    - Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (Nosso código requer isso para entender para qual versão devemos girar enquanto damos suporte a várias versões.)

Veja [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) outros detalhes sobre esse conjunto de campos.

## <a name="patient"></a>Paciente

Estes são os campos mínimos necessários, que são um subconjunto dos campos de perfil do paciente [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)

 - Name.Family
 - Nome.Dado
 - Gênero
 - Nascimento
 - MRN (Identificador)

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também lê os seguintes campos:

 - Name.Use
 - Name.Prefix
 - CuidadoProvider (Esta referência no recurso Paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)

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

Uma pesquisa de recursos usa o método POST em /Patient/_search e os seguintes parâmetros:

 - Id
 - família:contains=(procura todos os pacientes cujo nome da família contém o valor.)
 - given=\<substring>
 - nome=\<substring>
 - birthdate=(exact match)
 - \_contagem (número máximo de resultados que devem ser retornados) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa, e a contagem será usada pelo PatientsApp para limitar o número \_ de registros retornados.
 - identificador=\<mrn>

O objetivo é poder pesquisar e filtrar um paciente pelo seguinte:

- ID: Esta é a ID de recurso que todos os recursos em FHIR têm.
- MRN: Este é o identificador real do paciente que a equipe médica conheceria. Entendemos que esse MRN se baseia no tipo de identificador dentro do recurso identificador em FHIR
- Nome
- Nascimento

Veja o exemplo a seguir desta chamada.

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

Veja [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) outros detalhes sobre esse conjunto de campos.

## <a name="observation"></a>Observação

Estes são os campos mínimos necessários, que são um subconjunto do perfil de sinais vitais Argonaut:

 - Efetivo (data ou período)
 - Code.Coding.Code
 - ValueQuantity.Value

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também lê os seguintes campos:

 - Code.Coding.Display
 - ValueQuantity.Unit

Se estiver usando observações de componentes, a mesma lógica se aplica a cada observação de componente.

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id\>
 - classificar:desc=\<field ex. date\>

O objetivo é recuperar os sinais vitais mais recentes de um paciente, [VitalSigns.DSTU.saz] (observação?).

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

Veja [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) outros detalhes sobre esse conjunto de campos.

## <a name="condition"></a>Condição

Estes são os campos mínimos necessários, que são um subconjunto do perfil [da condição Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Exibir

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:

 - Data gravada
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

Veja [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) outros detalhes sobre esse conjunto de campos.

## <a name="encounter"></a>Encontro

Estes são os campos mínimos necessários, que são um subconjunto dos campos de perfil "deve ter" do perfil Do Core Encounter dos EUA:

 - Status
 - Digite[0]. Codificação[0]. Exibir

Além disso, os campos a seguir dos campos "deve ser suportado" do perfil "deve ser suportado" do perfil us Core Encounter

 - Ponto.Início
 - Local[0]. Local.Display

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

O objetivo é recuperar o último local conhecido do paciente. Cada encontro faz referência a um recurso de localização. A referência também incluirá o campo de exibição do local. Veja o exemplo a seguir desta chamada.

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

Veja [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) outros detalhes sobre esse conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos mínimos necessários, que são um subconjunto do perfil Argonaut AllergyIntolerance:

 - Code.Text
 - Code.Coding[0]. Exibir
 - Status

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também lê os seguintes campos:

 - RecordedDate
 - Texto.anotação
 - Reação[..]. Emoções.texto
 - Reação[..]. Demonstração[..]. Texto
 - Text.Div

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - Paciente =  \<patient id>

Veja o exemplo a seguir desta chamada:

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

Veja [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) outros detalhes sobre esse conjunto de campos.

## <a name="medication-order"></a>Pedido de medicamentos

Estes são os campos mínimos necessários, que são um subconjunto do perfil Argonaut MedicationOrder:

 - DateWritten
 - Desmador.display
 - Medication.Display (se referência)
 - Medicação.Texto (se conceito)

Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:

 - DateEnded
 - DomosInstruction.Text
 - Text.Div

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>
 - _count=\<max results>

Veja o exemplo a seguir desta chamada:

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

Veja [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) outros detalhes sobre esse conjunto de campos.

## <a name="coverage"></a>Cobertura

Estes são os campos mínimos necessários, não cobertos por perfis Us Core ou Argonaut:

 - Pagador

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

 - paciente=\<patient id>

Veja o exemplo a seguir desta chamada:

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
    
Veja [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) outros detalhes sobre esse conjunto de campos.

## <a name="location"></a>Local

Esse recurso está sendo usado apenas como referência no [recurso Encontrar.](#encounter)

Veja [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) outros detalhes sobre esse conjunto de campos.
