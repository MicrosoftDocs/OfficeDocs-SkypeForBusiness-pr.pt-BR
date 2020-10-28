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
# <a name="dstu2-interface-specification"></a><span data-ttu-id="17959-103">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="17959-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="17959-104">A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="17959-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="17959-105">Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente.</span><span class="sxs-lookup"><span data-stu-id="17959-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="17959-106">Confira o modelo pacientes em listas para começar.</span><span class="sxs-lookup"><span data-stu-id="17959-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="17959-107">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="17959-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="17959-108">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="17959-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="17959-109">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="17959-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="17959-110">Aguarde</span><span class="sxs-lookup"><span data-stu-id="17959-110">Patient</span></span>](#patient)
- [<span data-ttu-id="17959-111">Observações</span><span class="sxs-lookup"><span data-stu-id="17959-111">Observation</span></span>](#observation)
- [<span data-ttu-id="17959-112">Condição</span><span class="sxs-lookup"><span data-stu-id="17959-112">Condition</span></span>](#condition)
- [<span data-ttu-id="17959-113">Encontrá</span><span class="sxs-lookup"><span data-stu-id="17959-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="17959-114">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="17959-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="17959-115">Análise</span><span class="sxs-lookup"><span data-stu-id="17959-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="17959-116">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="17959-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="17959-117">Local</span><span class="sxs-lookup"><span data-stu-id="17959-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="17959-118">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado.</span><span class="sxs-lookup"><span data-stu-id="17959-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="17959-119">No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17959-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="17959-120">Consultas do aplicativo Microsoft Teams pacientes para mais de um recurso poste um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="17959-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="17959-121">O servidor processa cada solicitação e retorna um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="17959-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="17959-122">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="17959-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="17959-123">Todos os recursos de FHIR a seguir devem ser acessíveis pela referência a recursos diretos.</span><span class="sxs-lookup"><span data-stu-id="17959-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="17959-124">Conjunto de campos obrigatórios mínimos de conformidade</span><span class="sxs-lookup"><span data-stu-id="17959-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="17959-125">O servidor FHIR deve implementar a instrução de conformidade para que possamos ter um resumo factual de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="17959-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="17959-126">Esperamos os parâmetros a seguir em um servidor FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="17959-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="17959-127">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="17959-127">REST</span></span>

    - <span data-ttu-id="17959-128">Modo</span><span class="sxs-lookup"><span data-stu-id="17959-128">Mode</span></span>
    - <span data-ttu-id="17959-129">Haja</span><span class="sxs-lookup"><span data-stu-id="17959-129">Interaction</span></span>
    - <span data-ttu-id="17959-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="17959-130">Resource: Type</span></span>
    - <span data-ttu-id="17959-131">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="17959-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="17959-132">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotá-lo como suporte a várias versões.)</span><span class="sxs-lookup"><span data-stu-id="17959-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="17959-133">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="17959-134">Aguarde</span><span class="sxs-lookup"><span data-stu-id="17959-134">Patient</span></span>

<span data-ttu-id="17959-135">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de [perfil do paciente do Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="17959-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="17959-136">Nome. família</span><span class="sxs-lookup"><span data-stu-id="17959-136">Name.Family</span></span>
 - <span data-ttu-id="17959-137">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="17959-137">Name.Given</span></span>
 - <span data-ttu-id="17959-138">Sexo</span><span class="sxs-lookup"><span data-stu-id="17959-138">Gender</span></span>
 - <span data-ttu-id="17959-139">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="17959-139">BirthDate</span></span>
 - <span data-ttu-id="17959-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="17959-140">MRN (Identifier)</span></span>

<span data-ttu-id="17959-141">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="17959-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="17959-142">Name. Use</span><span class="sxs-lookup"><span data-stu-id="17959-142">Name.Use</span></span>
 - <span data-ttu-id="17959-143">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="17959-143">Name.Prefix</span></span>
 - <span data-ttu-id="17959-144">Cuidado: (essa referência ao recurso do paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)</span><span class="sxs-lookup"><span data-stu-id="17959-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="17959-145">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="17959-146">%</span><span class="sxs-lookup"><span data-stu-id="17959-146">id</span></span>
 - <span data-ttu-id="17959-147">Family: Contains = (procura por todos os pacientes cujo nome de família contenha o valor.)</span><span class="sxs-lookup"><span data-stu-id="17959-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="17959-148">especificado =\<substring></span><span class="sxs-lookup"><span data-stu-id="17959-148">given=\<substring></span></span>
 - <span data-ttu-id="17959-149">nome =\<substring></span><span class="sxs-lookup"><span data-stu-id="17959-149">name=\<substring></span></span>
 - <span data-ttu-id="17959-150">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="17959-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="17959-151">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="17959-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="17959-152">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a \_ contagem será usada pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="17959-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="17959-153">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="17959-153">identifier=\<mrn></span></span>

<span data-ttu-id="17959-154">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="17959-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="17959-155">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="17959-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="17959-156">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="17959-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="17959-157">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR</span><span class="sxs-lookup"><span data-stu-id="17959-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="17959-158">Nome</span><span class="sxs-lookup"><span data-stu-id="17959-158">Name</span></span>
- <span data-ttu-id="17959-159">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="17959-159">Birthdate</span></span>

<span data-ttu-id="17959-160">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="17959-160">See the following example  of this call.</span></span>

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

<span data-ttu-id="17959-161">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="17959-162">Observações</span><span class="sxs-lookup"><span data-stu-id="17959-162">Observation</span></span>

<span data-ttu-id="17959-163">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil de sinais Argonaut vital:</span><span class="sxs-lookup"><span data-stu-id="17959-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="17959-164">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="17959-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="17959-165">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="17959-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="17959-166">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="17959-166">ValueQuantity.Value</span></span>

<span data-ttu-id="17959-167">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="17959-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="17959-168">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="17959-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="17959-169">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="17959-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="17959-170">Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.</span><span class="sxs-lookup"><span data-stu-id="17959-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="17959-171">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="17959-172">paciente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="17959-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="17959-173">classificar: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="17959-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="17959-174">O objetivo é poder recuperar os mais recentes sinais essenciais para um paciente, [VitalSigns. DSTU. Saz] (observação?).</span><span class="sxs-lookup"><span data-stu-id="17959-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="17959-175">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="17959-176">Condição</span><span class="sxs-lookup"><span data-stu-id="17959-176">Condition</span></span>

<span data-ttu-id="17959-177">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="17959-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="17959-178">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="17959-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="17959-179">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="17959-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="17959-180">Data de gravação</span><span class="sxs-lookup"><span data-stu-id="17959-180">Date Recorded</span></span>
 - <span data-ttu-id="17959-181">Gravidade</span><span class="sxs-lookup"><span data-stu-id="17959-181">Severity</span></span>

<span data-ttu-id="17959-182">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="17959-183">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="17959-183">patient=\<patient id></span></span>
 - <span data-ttu-id="17959-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="17959-184">_count=\<max results></span></span>

<span data-ttu-id="17959-185">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="17959-185">See the following example of this call:</span></span>

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

<span data-ttu-id="17959-186">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="17959-187">Encontrá</span><span class="sxs-lookup"><span data-stu-id="17959-187">Encounter</span></span>

<span data-ttu-id="17959-188">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos perfil do núcleo dos EUA "deve ter":</span><span class="sxs-lookup"><span data-stu-id="17959-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="17959-189">Situação</span><span class="sxs-lookup"><span data-stu-id="17959-189">Status</span></span>
 - <span data-ttu-id="17959-190">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="17959-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="17959-191">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil principal</span><span class="sxs-lookup"><span data-stu-id="17959-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="17959-192">Período. início</span><span class="sxs-lookup"><span data-stu-id="17959-192">Period.Start</span></span>
 - <span data-ttu-id="17959-193">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="17959-193">Location[0].Location.Display</span></span>

<span data-ttu-id="17959-194">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="17959-195">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="17959-195">patient=\<patient id></span></span>
 - <span data-ttu-id="17959-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="17959-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="17959-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="17959-197">_count=\<max results></span></span>

<span data-ttu-id="17959-198">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="17959-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="17959-199">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="17959-199">Each encounter references a location resource.</span></span> <span data-ttu-id="17959-200">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="17959-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="17959-201">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="17959-201">See the following example of this call.</span></span>

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

<span data-ttu-id="17959-202">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="17959-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="17959-203">AllergyIntolerance</span></span>

<span data-ttu-id="17959-204">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="17959-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="17959-205">Code. Text</span><span class="sxs-lookup"><span data-stu-id="17959-205">Code.Text</span></span>
 - <span data-ttu-id="17959-206">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="17959-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="17959-207">Situação</span><span class="sxs-lookup"><span data-stu-id="17959-207">Status</span></span>

<span data-ttu-id="17959-208">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="17959-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="17959-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="17959-209">RecordedDate</span></span>
 - <span data-ttu-id="17959-210">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="17959-210">Note.Text</span></span>
 - <span data-ttu-id="17959-211">Reação [..]. Substância. Text</span><span class="sxs-lookup"><span data-stu-id="17959-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="17959-212">Reação [..]. Manifestação [..]. Textos</span><span class="sxs-lookup"><span data-stu-id="17959-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="17959-213">Text. div</span><span class="sxs-lookup"><span data-stu-id="17959-213">Text.Div</span></span>

<span data-ttu-id="17959-214">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="17959-215">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="17959-215">Patient =  \<patient id></span></span>

<span data-ttu-id="17959-216">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="17959-216">See the following example of this call:</span></span>

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

<span data-ttu-id="17959-217">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="17959-218">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="17959-218">Medication Order</span></span>

<span data-ttu-id="17959-219">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="17959-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="17959-220">DateWritten</span><span class="sxs-lookup"><span data-stu-id="17959-220">DateWritten</span></span>
 - <span data-ttu-id="17959-221">Preparador. exibição</span><span class="sxs-lookup"><span data-stu-id="17959-221">Prescriber.Display</span></span>
 - <span data-ttu-id="17959-222">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="17959-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="17959-223">Medicação. Text (se conceito)</span><span class="sxs-lookup"><span data-stu-id="17959-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="17959-224">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="17959-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="17959-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="17959-225">DateEnded</span></span>
 - <span data-ttu-id="17959-226">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="17959-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="17959-227">Text. div</span><span class="sxs-lookup"><span data-stu-id="17959-227">Text.Div</span></span>

<span data-ttu-id="17959-228">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="17959-229">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="17959-229">patient=\<patient id></span></span>
 - <span data-ttu-id="17959-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="17959-230">_count=\<max results></span></span>

<span data-ttu-id="17959-231">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="17959-231">See the following example of this call:</span></span>

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

<span data-ttu-id="17959-232">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="17959-233">Análise</span><span class="sxs-lookup"><span data-stu-id="17959-233">Coverage</span></span>

<span data-ttu-id="17959-234">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="17959-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="17959-235">Payor</span><span class="sxs-lookup"><span data-stu-id="17959-235">Payor</span></span>

<span data-ttu-id="17959-236">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="17959-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="17959-237">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="17959-237">patient=\<patient id></span></span>

<span data-ttu-id="17959-238">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="17959-238">See the following example of this call:</span></span>

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
    
<span data-ttu-id="17959-239">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="17959-240">Local</span><span class="sxs-lookup"><span data-stu-id="17959-240">Location</span></span>

<span data-ttu-id="17959-241">Esse recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="17959-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="17959-242">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="17959-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
