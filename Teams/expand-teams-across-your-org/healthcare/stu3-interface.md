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
# <a name="stu3-interface-specification"></a><span data-ttu-id="308db-103">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="308db-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="308db-104">A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="308db-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="308db-105">Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe.</span><span class="sxs-lookup"><span data-stu-id="308db-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="308db-106">Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="308db-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="308db-107">Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="308db-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="308db-108">Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes.</span><span class="sxs-lookup"><span data-stu-id="308db-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="308db-109">Confira o modelo Pacientes em Listas para começar.</span><span class="sxs-lookup"><span data-stu-id="308db-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="308db-110">Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="308db-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="308db-111">Configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Pacientes do Microsoft Teams requer a compreensão de quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="308db-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="308db-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="308db-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="308db-113">Paciente</span><span class="sxs-lookup"><span data-stu-id="308db-113">Patient</span></span>](#patient)
- [<span data-ttu-id="308db-114">Observação</span><span class="sxs-lookup"><span data-stu-id="308db-114">Observation</span></span>](#observation)
- [<span data-ttu-id="308db-115">Condição</span><span class="sxs-lookup"><span data-stu-id="308db-115">Condition</span></span>](#condition)
- [<span data-ttu-id="308db-116">Encontro</span><span class="sxs-lookup"><span data-stu-id="308db-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="308db-117">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="308db-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="308db-118">Cobertura</span><span class="sxs-lookup"><span data-stu-id="308db-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="308db-119">[Declaração de](#medication-request) medicamentos (substitui a MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="308db-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="308db-120">Local (as informações necessárias desse recurso podem ser incluídas no Encounter)</span><span class="sxs-lookup"><span data-stu-id="308db-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="308db-121">O recurso Paciente é o único recurso obrigatório (sem o qual o aplicativo não será carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para a melhor experiência do usuário final com o aplicativo Pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="308db-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="308db-122">As consultas do aplicativo Pacientes do Microsoft Teams para mais de um recurso devem postar um pacote (LOTE) de solicitações à URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="308db-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="308db-123">O servidor processará cada solicitação e retornará um pacote dos recursos de acordo com cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="308db-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="308db-124">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="308db-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="308db-125">Declaração de Capacidade</span><span class="sxs-lookup"><span data-stu-id="308db-125">Capability Statement</span></span>

<span data-ttu-id="308db-126">Estes são os campos mínimos necessários:</span><span class="sxs-lookup"><span data-stu-id="308db-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="308db-127">Resto</span><span class="sxs-lookup"><span data-stu-id="308db-127">REST</span></span>

    - <span data-ttu-id="308db-128">Modo</span><span class="sxs-lookup"><span data-stu-id="308db-128">Mode</span></span>
    - <span data-ttu-id="308db-129">Interação</span><span class="sxs-lookup"><span data-stu-id="308db-129">Interaction</span></span>
    - <span data-ttu-id="308db-130">Recurso: Digite</span><span class="sxs-lookup"><span data-stu-id="308db-130">Resource: Type</span></span>
    - <span data-ttu-id="308db-131">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="308db-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="308db-132">FhirVersion (Nosso código requer isso para entender para qual versão devemos girar.)</span><span class="sxs-lookup"><span data-stu-id="308db-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="308db-133">Veja [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="308db-134">Paciente</span><span class="sxs-lookup"><span data-stu-id="308db-134">Patient</span></span>

<span data-ttu-id="308db-135">Aqui estão os campos mínimos necessários, que são um subconjunto dos campos de perfil do paciente Argonaut:</span><span class="sxs-lookup"><span data-stu-id="308db-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="308db-136">Nome.Dado</span><span class="sxs-lookup"><span data-stu-id="308db-136">Name.Given</span></span>
 - <span data-ttu-id="308db-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="308db-137">Name.Family</span></span>
 - <span data-ttu-id="308db-138">Gênero</span><span class="sxs-lookup"><span data-stu-id="308db-138">Gender</span></span>
 - <span data-ttu-id="308db-139">Nascimento</span><span class="sxs-lookup"><span data-stu-id="308db-139">BirthDate</span></span>
 - <span data-ttu-id="308db-140">MRN (Identificador)</span><span class="sxs-lookup"><span data-stu-id="308db-140">MRN (Identifier)</span></span>

<span data-ttu-id="308db-141">Além dos campos [Argonaut,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="308db-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="308db-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="308db-142">Name.Use</span></span>
 - <span data-ttu-id="308db-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="308db-143">Name.Prefix</span></span>
 - <span data-ttu-id="308db-144">[GeneralLastctitioner] - A referência GeneralQuectitioner deve ser incluída no recurso Paciente (somente campo de exibição)</span><span class="sxs-lookup"><span data-stu-id="308db-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="308db-145">Uma pesquisa de recursos usa o método POST em /Patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="308db-146">Id</span><span class="sxs-lookup"><span data-stu-id="308db-146">id</span></span>
 - <span data-ttu-id="308db-147">family=(procura todos os pacientes cujo nome da família contém o valor)</span><span class="sxs-lookup"><span data-stu-id="308db-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="308db-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="308db-148">given=\<substring></span></span>
 - <span data-ttu-id="308db-149">birthdate=(exact match)</span><span class="sxs-lookup"><span data-stu-id="308db-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="308db-150">gender=(values being one of the administrative-gender)</span><span class="sxs-lookup"><span data-stu-id="308db-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="308db-151">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="308db-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="308db-152">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a contagem será usada pelo PatientsApp para limitar o número \_ de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="308db-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="308db-153">identificador=\<mrn></span><span class="sxs-lookup"><span data-stu-id="308db-153">identifier=\<mrn></span></span>

<span data-ttu-id="308db-154">O objetivo é poder pesquisar e filtrar um paciente pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="308db-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="308db-155">ID: Esta é a ID de recurso que todos os recursos em FHIR têm.</span><span class="sxs-lookup"><span data-stu-id="308db-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="308db-156">MRN: Este é o identificador real do paciente que a equipe médica conheceria.</span><span class="sxs-lookup"><span data-stu-id="308db-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="308db-157">Entendemos que esse MRN se baseia no tipo de identificador dentro do recurso identificador em FHIR.</span><span class="sxs-lookup"><span data-stu-id="308db-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="308db-158">Nome</span><span class="sxs-lookup"><span data-stu-id="308db-158">Name</span></span>
- <span data-ttu-id="308db-159">Nascimento</span><span class="sxs-lookup"><span data-stu-id="308db-159">Birthdate</span></span>

<span data-ttu-id="308db-160">Veja o exemplo a seguir da chamada:</span><span class="sxs-lookup"><span data-stu-id="308db-160">See the following example of the call:</span></span>

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

<span data-ttu-id="308db-161">Veja [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="308db-162">Observação</span><span class="sxs-lookup"><span data-stu-id="308db-162">Observation</span></span>

<span data-ttu-id="308db-163">Estes são os campos mínimos necessários, que são um subconjunto do perfil [argonaut Vital-Signs.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)</span><span class="sxs-lookup"><span data-stu-id="308db-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="308db-164">Efetivo (data ou período)</span><span class="sxs-lookup"><span data-stu-id="308db-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="308db-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="308db-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="308db-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="308db-166">ValueQuantity.Value</span></span>

<span data-ttu-id="308db-167">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="308db-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="308db-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="308db-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="308db-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="308db-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="308db-170">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="308db-171">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="308db-171">patient=\<patient id></span></span>
 - <span data-ttu-id="308db-172">_sort=data</span><span class="sxs-lookup"><span data-stu-id="308db-172">_sort=-date</span></span>
 - <span data-ttu-id="308db-173">(consultaremos "categoria=sinais vitais") para recuperar a lista de sinais vitais.</span><span class="sxs-lookup"><span data-stu-id="308db-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="308db-174">Confira este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="308db-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="308db-175">Veja [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="308db-176">Condição</span><span class="sxs-lookup"><span data-stu-id="308db-176">Condition</span></span>

<span data-ttu-id="308db-177">Aqui estão os campos mínimos necessários, que são um subconjunto do perfil [de condição Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="308db-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="308db-178">Code.Coding[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="308db-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="308db-179">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="308db-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="308db-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="308db-180">AssertedDate</span></span>
 - <span data-ttu-id="308db-181">Gravidade</span><span class="sxs-lookup"><span data-stu-id="308db-181">Severity</span></span>

<span data-ttu-id="308db-182">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="308db-183">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="308db-183">patient=\<patient id></span></span>
 - <span data-ttu-id="308db-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="308db-184">_count=\<max results></span></span>

<span data-ttu-id="308db-185">Veja o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="308db-185">See the following example of this call:</span></span>

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

<span data-ttu-id="308db-186">Veja [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="308db-187">Encontro</span><span class="sxs-lookup"><span data-stu-id="308db-187">Encounter</span></span>

<span data-ttu-id="308db-188">Esses são os campos mínimos necessários, que são um subconjunto dos campos de perfil "deve ter" do perfil [Do Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) dos EUA).</span><span class="sxs-lookup"><span data-stu-id="308db-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="308db-189">Status</span><span class="sxs-lookup"><span data-stu-id="308db-189">Status</span></span>
 - <span data-ttu-id="308db-190">Digite[0]. Codificação[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="308db-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="308db-191">Além disso, os campos a seguir dos campos "deve ser suportado" do perfil do Us Core Encounter:</span><span class="sxs-lookup"><span data-stu-id="308db-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="308db-192">Ponto.Início</span><span class="sxs-lookup"><span data-stu-id="308db-192">Period.Start</span></span>
 - <span data-ttu-id="308db-193">Local[0]. Local.Display</span><span class="sxs-lookup"><span data-stu-id="308db-193">Location[0].Location.Display</span></span>

<span data-ttu-id="308db-194">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="308db-195">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="308db-195">patient=\<patient id></span></span>
 - <span data-ttu-id="308db-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="308db-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="308db-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="308db-197">_count=\<max results></span></span>

<span data-ttu-id="308db-198">O objetivo é recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="308db-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="308db-199">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="308db-199">Each encounter references a location resource.</span></span> <span data-ttu-id="308db-200">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="308db-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="308db-201">Veja [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="308db-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="308db-202">AllergyIntolerance</span></span>

<span data-ttu-id="308db-203">Estes são os campos mínimos necessários, que são um subconjunto do perfil [Argonaut AllergyIntolerance:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)</span><span class="sxs-lookup"><span data-stu-id="308db-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="308db-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="308db-204">Code.Text</span></span>
 - <span data-ttu-id="308db-205">Code.Coding[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="308db-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="308db-206">ClinicalStatus/VerificationStatus (lemos ambos)</span><span class="sxs-lookup"><span data-stu-id="308db-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="308db-207">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler o seguinte campo:</span><span class="sxs-lookup"><span data-stu-id="308db-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="308db-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="308db-208">AssertedDate</span></span>
 - <span data-ttu-id="308db-209">Texto.anotação</span><span class="sxs-lookup"><span data-stu-id="308db-209">Note.Text</span></span>
 - <span data-ttu-id="308db-210">Reação</span><span class="sxs-lookup"><span data-stu-id="308db-210">Reaction</span></span>
    - <span data-ttu-id="308db-211">Emotivo (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="308db-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="308db-212">Demonstração (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="308db-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="308db-213">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="308db-214">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="308db-214">Patient =  \<patient id></span></span>

<span data-ttu-id="308db-215">Veja o exemplo a seguir da chamada:</span><span class="sxs-lookup"><span data-stu-id="308db-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="308db-216">Veja [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="308db-217">Solicitação de medicamentos</span><span class="sxs-lookup"><span data-stu-id="308db-217">Medication Request</span></span>

<span data-ttu-id="308db-218">Estes são os campos mínimos necessários, que são um subconjunto do perfil [Us Core Medication Request](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="308db-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="308db-219">Medication.Display (se Referência)</span><span class="sxs-lookup"><span data-stu-id="308db-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="308db-220">Medication.Text (if CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="308db-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="308db-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="308db-221">AuthoredOn</span></span>
 - <span data-ttu-id="308db-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="308db-222">Requester.Agent.Display</span></span>

<span data-ttu-id="308db-223">Além dos campos Us Core, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="308db-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="308db-224">DeMoscarInstrução[..]. Texto</span><span class="sxs-lookup"><span data-stu-id="308db-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="308db-225">Texto</span><span class="sxs-lookup"><span data-stu-id="308db-225">Text</span></span>

<span data-ttu-id="308db-226">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="308db-227">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="308db-227">patient=\<patient id></span></span>
 - <span data-ttu-id="308db-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="308db-228">_count=\<max results></span></span>

<span data-ttu-id="308db-229">Veja [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="308db-230">Cobertura</span><span class="sxs-lookup"><span data-stu-id="308db-230">Coverage</span></span>

<span data-ttu-id="308db-231">Estes são os campos mínimos necessários, não cobertos por perfis Us Core ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="308db-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="308db-232">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="308db-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="308db-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="308db-233">GroupDisplay</span></span>
    - <span data-ttu-id="308db-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="308db-234">PlanDisplay</span></span>
 - <span data-ttu-id="308db-235">Período</span><span class="sxs-lookup"><span data-stu-id="308db-235">Period</span></span>
 - <span data-ttu-id="308db-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="308db-236">SubscriberId</span></span>

<span data-ttu-id="308db-237">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="308db-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="308db-238">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="308db-238">Patient = \<patient id></span></span>

<span data-ttu-id="308db-239">Veja [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="308db-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
