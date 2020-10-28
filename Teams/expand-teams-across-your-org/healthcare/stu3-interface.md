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
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772262"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="badd1-103">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="badd1-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="badd1-104">A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="badd1-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="badd1-105">Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente.</span><span class="sxs-lookup"><span data-stu-id="badd1-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="badd1-106">Confira o modelo pacientes em listas para começar.</span><span class="sxs-lookup"><span data-stu-id="badd1-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="badd1-107">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="badd1-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="badd1-108">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="badd1-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="badd1-109">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="badd1-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="badd1-110">Aguarde</span><span class="sxs-lookup"><span data-stu-id="badd1-110">Patient</span></span>](#patient)
- [<span data-ttu-id="badd1-111">Observações</span><span class="sxs-lookup"><span data-stu-id="badd1-111">Observation</span></span>](#observation)
- [<span data-ttu-id="badd1-112">Condição</span><span class="sxs-lookup"><span data-stu-id="badd1-112">Condition</span></span>](#condition)
- [<span data-ttu-id="badd1-113">Encontrá</span><span class="sxs-lookup"><span data-stu-id="badd1-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="badd1-114">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="badd1-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="badd1-115">Análise</span><span class="sxs-lookup"><span data-stu-id="badd1-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="badd1-116">[Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="badd1-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="badd1-117">Local (as informações necessárias deste recurso podem ser incluídas em encontrar)</span><span class="sxs-lookup"><span data-stu-id="badd1-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="badd1-118">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="badd1-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="badd1-119">As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="badd1-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="badd1-120">O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="badd1-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="badd1-121">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="badd1-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="badd1-122">Declaração de recursos</span><span class="sxs-lookup"><span data-stu-id="badd1-122">Capability Statement</span></span>

<span data-ttu-id="badd1-123">Estes são os campos mínimos obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="badd1-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="badd1-124">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="badd1-124">REST</span></span>

    - <span data-ttu-id="badd1-125">Modo</span><span class="sxs-lookup"><span data-stu-id="badd1-125">Mode</span></span>
    - <span data-ttu-id="badd1-126">Haja</span><span class="sxs-lookup"><span data-stu-id="badd1-126">Interaction</span></span>
    - <span data-ttu-id="badd1-127">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="badd1-127">Resource: Type</span></span>
    - <span data-ttu-id="badd1-128">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="badd1-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="badd1-129">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)</span><span class="sxs-lookup"><span data-stu-id="badd1-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="badd1-130">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="badd1-131">Aguarde</span><span class="sxs-lookup"><span data-stu-id="badd1-131">Patient</span></span>

<span data-ttu-id="badd1-132">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:</span><span class="sxs-lookup"><span data-stu-id="badd1-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="badd1-133">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="badd1-133">Name.Given</span></span>
 - <span data-ttu-id="badd1-134">Nome. família</span><span class="sxs-lookup"><span data-stu-id="badd1-134">Name.Family</span></span>
 - <span data-ttu-id="badd1-135">Sexo</span><span class="sxs-lookup"><span data-stu-id="badd1-135">Gender</span></span>
 - <span data-ttu-id="badd1-136">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="badd1-136">BirthDate</span></span>
 - <span data-ttu-id="badd1-137">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="badd1-137">MRN (Identifier)</span></span>

<span data-ttu-id="badd1-138">Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="badd1-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="badd1-139">Name. Use</span><span class="sxs-lookup"><span data-stu-id="badd1-139">Name.Use</span></span>
 - <span data-ttu-id="badd1-140">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="badd1-140">Name.Prefix</span></span>
 - <span data-ttu-id="badd1-141">[GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)</span><span class="sxs-lookup"><span data-stu-id="badd1-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="badd1-142">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="badd1-143">%</span><span class="sxs-lookup"><span data-stu-id="badd1-143">id</span></span>
 - <span data-ttu-id="badd1-144">Family = (procura por todos os pacientes cujo nome de família contenha o valor)</span><span class="sxs-lookup"><span data-stu-id="badd1-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="badd1-145">especificado =\<substring></span><span class="sxs-lookup"><span data-stu-id="badd1-145">given=\<substring></span></span>
 - <span data-ttu-id="badd1-146">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="badd1-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="badd1-147">Gênero = (valores sendo um dos sexo administrativos)</span><span class="sxs-lookup"><span data-stu-id="badd1-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="badd1-148">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="badd1-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="badd1-149">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e da \_ contagem que será usado pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="badd1-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="badd1-150">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="badd1-150">identifier=\<mrn></span></span>

<span data-ttu-id="badd1-151">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="badd1-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="badd1-152">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="badd1-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="badd1-153">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="badd1-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="badd1-154">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.</span><span class="sxs-lookup"><span data-stu-id="badd1-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="badd1-155">Nome</span><span class="sxs-lookup"><span data-stu-id="badd1-155">Name</span></span>
- <span data-ttu-id="badd1-156">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="badd1-156">Birthdate</span></span>

<span data-ttu-id="badd1-157">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="badd1-157">See the following example of the call:</span></span>

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

<span data-ttu-id="badd1-158">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="badd1-159">Observações</span><span class="sxs-lookup"><span data-stu-id="badd1-159">Observation</span></span>

<span data-ttu-id="badd1-160">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de Vital-Signs Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="badd1-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="badd1-161">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="badd1-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="badd1-162">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="badd1-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="badd1-163">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="badd1-163">ValueQuantity.Value</span></span>

<span data-ttu-id="badd1-164">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="badd1-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="badd1-165">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="badd1-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="badd1-166">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="badd1-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="badd1-167">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="badd1-168">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="badd1-168">patient=\<patient id></span></span>
 - <span data-ttu-id="badd1-169">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="badd1-169">_sort=-date</span></span>
 - <span data-ttu-id="badd1-170">Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.</span><span class="sxs-lookup"><span data-stu-id="badd1-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="badd1-171">Consulte este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="badd1-171">Refer to this example of the call:</span></span>

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

<span data-ttu-id="badd1-172">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="badd1-173">Condição</span><span class="sxs-lookup"><span data-stu-id="badd1-173">Condition</span></span>

<span data-ttu-id="badd1-174">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="badd1-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="badd1-175">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="badd1-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="badd1-176">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="badd1-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="badd1-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="badd1-177">AssertedDate</span></span>
 - <span data-ttu-id="badd1-178">Gravidade</span><span class="sxs-lookup"><span data-stu-id="badd1-178">Severity</span></span>

<span data-ttu-id="badd1-179">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="badd1-180">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="badd1-180">patient=\<patient id></span></span>
 - <span data-ttu-id="badd1-181">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="badd1-181">_count=\<max results></span></span>

<span data-ttu-id="badd1-182">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="badd1-182">See the following example of this call:</span></span>

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

<span data-ttu-id="badd1-183">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="badd1-184">Encontrá</span><span class="sxs-lookup"><span data-stu-id="badd1-184">Encounter</span></span>

<span data-ttu-id="badd1-185">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="badd1-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="badd1-186">Situação</span><span class="sxs-lookup"><span data-stu-id="badd1-186">Status</span></span>
 - <span data-ttu-id="badd1-187">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="badd1-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="badd1-188">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:</span><span class="sxs-lookup"><span data-stu-id="badd1-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="badd1-189">Período. início</span><span class="sxs-lookup"><span data-stu-id="badd1-189">Period.Start</span></span>
 - <span data-ttu-id="badd1-190">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="badd1-190">Location[0].Location.Display</span></span>

<span data-ttu-id="badd1-191">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="badd1-192">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="badd1-192">patient=\<patient id></span></span>
 - <span data-ttu-id="badd1-193">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="badd1-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="badd1-194">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="badd1-194">_count=\<max results></span></span>

<span data-ttu-id="badd1-195">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="badd1-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="badd1-196">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="badd1-196">Each encounter references a location resource.</span></span> <span data-ttu-id="badd1-197">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="badd1-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="badd1-198">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="badd1-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="badd1-199">AllergyIntolerance</span></span>

<span data-ttu-id="badd1-200">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="badd1-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="badd1-201">Code. Text</span><span class="sxs-lookup"><span data-stu-id="badd1-201">Code.Text</span></span>
 - <span data-ttu-id="badd1-202">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="badd1-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="badd1-203">ClinicalStatus/VerificationStatus (Lemos)</span><span class="sxs-lookup"><span data-stu-id="badd1-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="badd1-204">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:</span><span class="sxs-lookup"><span data-stu-id="badd1-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="badd1-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="badd1-205">AssertedDate</span></span>
 - <span data-ttu-id="badd1-206">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="badd1-206">Note.Text</span></span>
 - <span data-ttu-id="badd1-207">Reação</span><span class="sxs-lookup"><span data-stu-id="badd1-207">Reaction</span></span>
    - <span data-ttu-id="badd1-208">Substância (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="badd1-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="badd1-209">Manifestação (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="badd1-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="badd1-210">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="badd1-211">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="badd1-211">Patient =  \<patient id></span></span>

<span data-ttu-id="badd1-212">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="badd1-212">See the following example of the call:</span></span> 

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

<span data-ttu-id="badd1-213">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="badd1-214">Solicitação de medicação</span><span class="sxs-lookup"><span data-stu-id="badd1-214">Medication Request</span></span>

<span data-ttu-id="badd1-215">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="badd1-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="badd1-216">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="badd1-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="badd1-217">Medicação. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="badd1-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="badd1-218">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="badd1-218">AuthoredOn</span></span>
 - <span data-ttu-id="badd1-219">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="badd1-219">Requester.Agent.Display</span></span>

<span data-ttu-id="badd1-220">Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="badd1-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="badd1-221">DosageInstruction[..]. Textos</span><span class="sxs-lookup"><span data-stu-id="badd1-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="badd1-222">Textos</span><span class="sxs-lookup"><span data-stu-id="badd1-222">Text</span></span>

<span data-ttu-id="badd1-223">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="badd1-224">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="badd1-224">patient=\<patient id></span></span>
 - <span data-ttu-id="badd1-225">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="badd1-225">_count=\<max results></span></span>

<span data-ttu-id="badd1-226">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="badd1-227">Análise</span><span class="sxs-lookup"><span data-stu-id="badd1-227">Coverage</span></span>

<span data-ttu-id="badd1-228">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="badd1-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="badd1-229">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="badd1-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="badd1-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="badd1-230">GroupDisplay</span></span>
    - <span data-ttu-id="badd1-231">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="badd1-231">PlanDisplay</span></span>
 - <span data-ttu-id="badd1-232">Período</span><span class="sxs-lookup"><span data-stu-id="badd1-232">Period</span></span>
 - <span data-ttu-id="badd1-233">Subscriberid</span><span class="sxs-lookup"><span data-stu-id="badd1-233">SubscriberId</span></span>

<span data-ttu-id="badd1-234">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="badd1-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="badd1-235">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="badd1-235">Patient = \<patient id></span></span>

<span data-ttu-id="badd1-236">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="badd1-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
