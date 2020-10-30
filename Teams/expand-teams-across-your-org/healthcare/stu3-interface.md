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
# <a name="stu3-interface-specification"></a><span data-ttu-id="9402f-103">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="9402f-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="9402f-104">A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="9402f-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="9402f-105">Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe.</span><span class="sxs-lookup"><span data-stu-id="9402f-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="9402f-106">Todos os dados associados ao aplicativo pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9402f-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="9402f-107">Os usuários podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="9402f-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="9402f-108">Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente.</span><span class="sxs-lookup"><span data-stu-id="9402f-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="9402f-109">Confira o modelo pacientes em listas para começar.</span><span class="sxs-lookup"><span data-stu-id="9402f-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="9402f-110">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="9402f-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="9402f-111">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="9402f-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="9402f-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="9402f-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="9402f-113">Aguarde</span><span class="sxs-lookup"><span data-stu-id="9402f-113">Patient</span></span>](#patient)
- [<span data-ttu-id="9402f-114">Observações</span><span class="sxs-lookup"><span data-stu-id="9402f-114">Observation</span></span>](#observation)
- [<span data-ttu-id="9402f-115">Condição</span><span class="sxs-lookup"><span data-stu-id="9402f-115">Condition</span></span>](#condition)
- [<span data-ttu-id="9402f-116">Encontrá</span><span class="sxs-lookup"><span data-stu-id="9402f-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="9402f-117">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="9402f-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="9402f-118">Análise</span><span class="sxs-lookup"><span data-stu-id="9402f-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="9402f-119">[Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="9402f-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="9402f-120">Local (as informações necessárias deste recurso podem ser incluídas em encontrar)</span><span class="sxs-lookup"><span data-stu-id="9402f-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="9402f-121">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9402f-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="9402f-122">As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="9402f-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="9402f-123">O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="9402f-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="9402f-124">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="9402f-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="9402f-125">Declaração de recursos</span><span class="sxs-lookup"><span data-stu-id="9402f-125">Capability Statement</span></span>

<span data-ttu-id="9402f-126">Estes são os campos mínimos obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="9402f-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="9402f-127">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="9402f-127">REST</span></span>

    - <span data-ttu-id="9402f-128">Modo</span><span class="sxs-lookup"><span data-stu-id="9402f-128">Mode</span></span>
    - <span data-ttu-id="9402f-129">Haja</span><span class="sxs-lookup"><span data-stu-id="9402f-129">Interaction</span></span>
    - <span data-ttu-id="9402f-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="9402f-130">Resource: Type</span></span>
    - <span data-ttu-id="9402f-131">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="9402f-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="9402f-132">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)</span><span class="sxs-lookup"><span data-stu-id="9402f-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="9402f-133">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="9402f-134">Aguarde</span><span class="sxs-lookup"><span data-stu-id="9402f-134">Patient</span></span>

<span data-ttu-id="9402f-135">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:</span><span class="sxs-lookup"><span data-stu-id="9402f-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="9402f-136">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="9402f-136">Name.Given</span></span>
 - <span data-ttu-id="9402f-137">Nome. família</span><span class="sxs-lookup"><span data-stu-id="9402f-137">Name.Family</span></span>
 - <span data-ttu-id="9402f-138">Sexo</span><span class="sxs-lookup"><span data-stu-id="9402f-138">Gender</span></span>
 - <span data-ttu-id="9402f-139">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="9402f-139">BirthDate</span></span>
 - <span data-ttu-id="9402f-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="9402f-140">MRN (Identifier)</span></span>

<span data-ttu-id="9402f-141">Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="9402f-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9402f-142">Name. Use</span><span class="sxs-lookup"><span data-stu-id="9402f-142">Name.Use</span></span>
 - <span data-ttu-id="9402f-143">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="9402f-143">Name.Prefix</span></span>
 - <span data-ttu-id="9402f-144">[GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)</span><span class="sxs-lookup"><span data-stu-id="9402f-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="9402f-145">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="9402f-146">%</span><span class="sxs-lookup"><span data-stu-id="9402f-146">id</span></span>
 - <span data-ttu-id="9402f-147">Family = (procura por todos os pacientes cujo nome de família contenha o valor)</span><span class="sxs-lookup"><span data-stu-id="9402f-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="9402f-148">especificado =\<substring></span><span class="sxs-lookup"><span data-stu-id="9402f-148">given=\<substring></span></span>
 - <span data-ttu-id="9402f-149">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="9402f-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="9402f-150">Gênero = (valores sendo um dos sexo administrativos)</span><span class="sxs-lookup"><span data-stu-id="9402f-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="9402f-151">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="9402f-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="9402f-152">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e da \_ contagem que será usado pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="9402f-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="9402f-153">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="9402f-153">identifier=\<mrn></span></span>

<span data-ttu-id="9402f-154">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9402f-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="9402f-155">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="9402f-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="9402f-156">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="9402f-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="9402f-157">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.</span><span class="sxs-lookup"><span data-stu-id="9402f-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="9402f-158">Nome</span><span class="sxs-lookup"><span data-stu-id="9402f-158">Name</span></span>
- <span data-ttu-id="9402f-159">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="9402f-159">Birthdate</span></span>

<span data-ttu-id="9402f-160">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="9402f-160">See the following example of the call:</span></span>

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

<span data-ttu-id="9402f-161">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="9402f-162">Observações</span><span class="sxs-lookup"><span data-stu-id="9402f-162">Observation</span></span>

<span data-ttu-id="9402f-163">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de Vital-Signs Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="9402f-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="9402f-164">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="9402f-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="9402f-165">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="9402f-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="9402f-166">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="9402f-166">ValueQuantity.Value</span></span>

<span data-ttu-id="9402f-167">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="9402f-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9402f-168">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="9402f-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="9402f-169">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="9402f-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="9402f-170">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9402f-171">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="9402f-171">patient=\<patient id></span></span>
 - <span data-ttu-id="9402f-172">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="9402f-172">_sort=-date</span></span>
 - <span data-ttu-id="9402f-173">Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.</span><span class="sxs-lookup"><span data-stu-id="9402f-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="9402f-174">Consulte este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="9402f-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="9402f-175">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="9402f-176">Condição</span><span class="sxs-lookup"><span data-stu-id="9402f-176">Condition</span></span>

<span data-ttu-id="9402f-177">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="9402f-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="9402f-178">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="9402f-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="9402f-179">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="9402f-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9402f-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="9402f-180">AssertedDate</span></span>
 - <span data-ttu-id="9402f-181">Gravidade</span><span class="sxs-lookup"><span data-stu-id="9402f-181">Severity</span></span>

<span data-ttu-id="9402f-182">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9402f-183">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="9402f-183">patient=\<patient id></span></span>
 - <span data-ttu-id="9402f-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="9402f-184">_count=\<max results></span></span>

<span data-ttu-id="9402f-185">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="9402f-185">See the following example of this call:</span></span>

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

<span data-ttu-id="9402f-186">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="9402f-187">Encontrá</span><span class="sxs-lookup"><span data-stu-id="9402f-187">Encounter</span></span>

<span data-ttu-id="9402f-188">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="9402f-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="9402f-189">Situação</span><span class="sxs-lookup"><span data-stu-id="9402f-189">Status</span></span>
 - <span data-ttu-id="9402f-190">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="9402f-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="9402f-191">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:</span><span class="sxs-lookup"><span data-stu-id="9402f-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="9402f-192">Período. início</span><span class="sxs-lookup"><span data-stu-id="9402f-192">Period.Start</span></span>
 - <span data-ttu-id="9402f-193">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="9402f-193">Location[0].Location.Display</span></span>

<span data-ttu-id="9402f-194">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9402f-195">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="9402f-195">patient=\<patient id></span></span>
 - <span data-ttu-id="9402f-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="9402f-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="9402f-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="9402f-197">_count=\<max results></span></span>

<span data-ttu-id="9402f-198">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="9402f-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="9402f-199">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="9402f-199">Each encounter references a location resource.</span></span> <span data-ttu-id="9402f-200">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="9402f-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="9402f-201">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="9402f-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="9402f-202">AllergyIntolerance</span></span>

<span data-ttu-id="9402f-203">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="9402f-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="9402f-204">Code. Text</span><span class="sxs-lookup"><span data-stu-id="9402f-204">Code.Text</span></span>
 - <span data-ttu-id="9402f-205">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="9402f-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="9402f-206">ClinicalStatus/VerificationStatus (Lemos)</span><span class="sxs-lookup"><span data-stu-id="9402f-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="9402f-207">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:</span><span class="sxs-lookup"><span data-stu-id="9402f-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="9402f-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="9402f-208">AssertedDate</span></span>
 - <span data-ttu-id="9402f-209">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="9402f-209">Note.Text</span></span>
 - <span data-ttu-id="9402f-210">Reação</span><span class="sxs-lookup"><span data-stu-id="9402f-210">Reaction</span></span>
    - <span data-ttu-id="9402f-211">Substância (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="9402f-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="9402f-212">Manifestação (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="9402f-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="9402f-213">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9402f-214">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="9402f-214">Patient =  \<patient id></span></span>

<span data-ttu-id="9402f-215">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="9402f-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="9402f-216">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="9402f-217">Solicitação de medicação</span><span class="sxs-lookup"><span data-stu-id="9402f-217">Medication Request</span></span>

<span data-ttu-id="9402f-218">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="9402f-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="9402f-219">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="9402f-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="9402f-220">Medicação. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="9402f-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="9402f-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="9402f-221">AuthoredOn</span></span>
 - <span data-ttu-id="9402f-222">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="9402f-222">Requester.Agent.Display</span></span>

<span data-ttu-id="9402f-223">Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="9402f-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9402f-224">DosageInstruction[..]. Textos</span><span class="sxs-lookup"><span data-stu-id="9402f-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="9402f-225">Textos</span><span class="sxs-lookup"><span data-stu-id="9402f-225">Text</span></span>

<span data-ttu-id="9402f-226">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9402f-227">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="9402f-227">patient=\<patient id></span></span>
 - <span data-ttu-id="9402f-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="9402f-228">_count=\<max results></span></span>

<span data-ttu-id="9402f-229">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="9402f-230">Análise</span><span class="sxs-lookup"><span data-stu-id="9402f-230">Coverage</span></span>

<span data-ttu-id="9402f-231">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="9402f-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="9402f-232">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="9402f-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="9402f-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="9402f-233">GroupDisplay</span></span>
    - <span data-ttu-id="9402f-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="9402f-234">PlanDisplay</span></span>
 - <span data-ttu-id="9402f-235">Período</span><span class="sxs-lookup"><span data-stu-id="9402f-235">Period</span></span>
 - <span data-ttu-id="9402f-236">Subscriberid</span><span class="sxs-lookup"><span data-stu-id="9402f-236">SubscriberId</span></span>

<span data-ttu-id="9402f-237">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9402f-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9402f-238">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="9402f-238">Patient = \<patient id></span></span>

<span data-ttu-id="9402f-239">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9402f-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
