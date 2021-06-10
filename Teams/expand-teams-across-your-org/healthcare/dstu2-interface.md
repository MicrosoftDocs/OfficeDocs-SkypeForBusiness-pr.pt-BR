---
title: Interface DSTU2 de integração do Aplicativo e do EHR de Pacientes
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
description: Saiba mais sobre a especificação da interface DSTU2 no Teams, incluindo a configuração ou reconfiguração de um servidor FHIR para trabalhar com o aplicativo Microsoft Teams Patients.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803479"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="96cca-103">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="96cca-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="96cca-104">A partir de 30 de outubro de 2020, o aplicativo Pacientes será retirado e substituído pelo [aplicativo de Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="96cca-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="96cca-105">Os dados do aplicativo Pacientes são armazenados na caixa de correio do grupo do Office 365 que apoia a equipe.</span><span class="sxs-lookup"><span data-stu-id="96cca-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="96cca-106">Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="96cca-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="96cca-107">Os usuários podem criar suas listas usando o [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="96cca-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="96cca-108">Com o Lists, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam desde reuniões gerais com a equipe de atendimento até o monitoramento geral dos pacientes.</span><span class="sxs-lookup"><span data-stu-id="96cca-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="96cca-109">Confira o modelo Pacientes no Lists para começar.</span><span class="sxs-lookup"><span data-stu-id="96cca-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="96cca-110">Para saber mais sobre como gerenciar o aplicativo Lists em sua organização, consulte [Gerenciar o aplicativo Lists](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="96cca-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="96cca-111">Configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo de pacientes Microsoft Teams requer a compreensão de quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="96cca-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="96cca-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="96cca-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="96cca-113">Paciente</span><span class="sxs-lookup"><span data-stu-id="96cca-113">Patient</span></span>](#patient)
- [<span data-ttu-id="96cca-114">Observação</span><span class="sxs-lookup"><span data-stu-id="96cca-114">Observation</span></span>](#observation)
- [<span data-ttu-id="96cca-115">Condição</span><span class="sxs-lookup"><span data-stu-id="96cca-115">Condition</span></span>](#condition)
- [<span data-ttu-id="96cca-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="96cca-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="96cca-117">Intolerância de allergy</span><span class="sxs-lookup"><span data-stu-id="96cca-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="96cca-118">Cobertura</span><span class="sxs-lookup"><span data-stu-id="96cca-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="96cca-119">Ordem de Medicação</span><span class="sxs-lookup"><span data-stu-id="96cca-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="96cca-120">Local</span><span class="sxs-lookup"><span data-stu-id="96cca-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="96cca-121">O recurso Patient é o único recurso obrigatório (sem o qual o aplicativo não carregará nada.</span><span class="sxs-lookup"><span data-stu-id="96cca-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="96cca-122">No entanto, é recomendável que o Parceiro implemente suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para a melhor experiência do usuário final com o aplicativo de Microsoft Teams Patients.</span><span class="sxs-lookup"><span data-stu-id="96cca-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="96cca-123">Consultas do aplicativo Microsoft Teams Patients para mais de um recurso postam um lote (BATCH) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="96cca-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="96cca-124">O servidor processa cada solicitação e retorna um pacote de recursos de acordo com cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="96cca-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="96cca-125">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="96cca-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="96cca-126">Todos os recursos FHIR a seguir devem ser acessíveis por referência de recurso direto.</span><span class="sxs-lookup"><span data-stu-id="96cca-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="96cca-127">Conjunto de campos mínimo necessário de conformidade</span><span class="sxs-lookup"><span data-stu-id="96cca-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="96cca-128">O Servidor FHIR deve implementar a instrução de conformidade para que nós tenhamos um resumo factual de suas capacidades.</span><span class="sxs-lookup"><span data-stu-id="96cca-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="96cca-129">Esperamos os parâmetros abaixo em um servidor FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="96cca-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="96cca-130">REST</span><span class="sxs-lookup"><span data-stu-id="96cca-130">REST</span></span>

    - <span data-ttu-id="96cca-131">Modo</span><span class="sxs-lookup"><span data-stu-id="96cca-131">Mode</span></span>
    - <span data-ttu-id="96cca-132">Interação</span><span class="sxs-lookup"><span data-stu-id="96cca-132">Interaction</span></span>
    - <span data-ttu-id="96cca-133">Recurso: Tipo</span><span class="sxs-lookup"><span data-stu-id="96cca-133">Resource: Type</span></span>
    - <span data-ttu-id="96cca-134">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="96cca-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="96cca-135">FhirVersion (Nosso código requer isso para entender para qual versão devemos girar conforme suportamos várias versões.)</span><span class="sxs-lookup"><span data-stu-id="96cca-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="96cca-136">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="96cca-137">Paciente</span><span class="sxs-lookup"><span data-stu-id="96cca-137">Patient</span></span>

<span data-ttu-id="96cca-138">Esses são os campos mínimos necessários, que são um subconjunto dos campos de perfil de paciente [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)</span><span class="sxs-lookup"><span data-stu-id="96cca-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="96cca-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="96cca-139">Name.Family</span></span>
 - <span data-ttu-id="96cca-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="96cca-140">Name.Given</span></span>
 - <span data-ttu-id="96cca-141">Gênero</span><span class="sxs-lookup"><span data-stu-id="96cca-141">Gender</span></span>
 - <span data-ttu-id="96cca-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="96cca-142">BirthDate</span></span>
 - <span data-ttu-id="96cca-143">MRN (Identificador)</span><span class="sxs-lookup"><span data-stu-id="96cca-143">MRN (Identifier)</span></span>

<span data-ttu-id="96cca-144">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Patients também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="96cca-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="96cca-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="96cca-145">Name.Use</span></span>
 - <span data-ttu-id="96cca-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="96cca-146">Name.Prefix</span></span>
 - <span data-ttu-id="96cca-147">CareProvider (Essa referência no recurso Paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)</span><span class="sxs-lookup"><span data-stu-id="96cca-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="96cca-148">Uma pesquisa de recursos usa o método POST em /Patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="96cca-149">id</span><span class="sxs-lookup"><span data-stu-id="96cca-149">id</span></span>
 - <span data-ttu-id="96cca-150">family:contains=(searches for all patients whose family name contains the value.)</span><span class="sxs-lookup"><span data-stu-id="96cca-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="96cca-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="96cca-151">given=\<substring></span></span>
 - <span data-ttu-id="96cca-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="96cca-152">name=\<substring></span></span>
 - <span data-ttu-id="96cca-153">birthdate=(exact match)</span><span class="sxs-lookup"><span data-stu-id="96cca-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="96cca-154">\_count (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="96cca-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="96cca-155">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a contagem será usada pelo PatientsApp para limitar o número \_ de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="96cca-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="96cca-156">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="96cca-156">identifier=\<mrn></span></span>

<span data-ttu-id="96cca-157">O objetivo é poder pesquisar e filtrar um paciente pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="96cca-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="96cca-158">ID: Essa é a ID de recurso que todos os recursos em FHIR têm.</span><span class="sxs-lookup"><span data-stu-id="96cca-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="96cca-159">MRN: Este é o identificador real para o paciente que a equipe médica conheceria.</span><span class="sxs-lookup"><span data-stu-id="96cca-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="96cca-160">Entendemos que essa MRN se baseia no tipo de identificador dentro do recurso identificador no FHIR</span><span class="sxs-lookup"><span data-stu-id="96cca-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="96cca-161">Nome</span><span class="sxs-lookup"><span data-stu-id="96cca-161">Name</span></span>
- <span data-ttu-id="96cca-162">Data de nascimento</span><span class="sxs-lookup"><span data-stu-id="96cca-162">Birthdate</span></span>

<span data-ttu-id="96cca-163">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="96cca-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="96cca-164">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="96cca-165">Observação</span><span class="sxs-lookup"><span data-stu-id="96cca-165">Observation</span></span>

<span data-ttu-id="96cca-166">Esses são os campos mínimos necessários, que são um subconjunto do perfil de sinais vitais argonaut:</span><span class="sxs-lookup"><span data-stu-id="96cca-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="96cca-167">Efetivo (data ou período)</span><span class="sxs-lookup"><span data-stu-id="96cca-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="96cca-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="96cca-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="96cca-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="96cca-169">ValueQuantity.Value</span></span>

<span data-ttu-id="96cca-170">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Patients também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="96cca-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="96cca-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="96cca-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="96cca-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="96cca-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="96cca-173">Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.</span><span class="sxs-lookup"><span data-stu-id="96cca-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="96cca-174">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="96cca-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="96cca-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="96cca-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="96cca-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="96cca-177">O objetivo é recuperar os sinais vitais mais recentes de um paciente, [VitalSigns.DSTU.saz] (observação?).</span><span class="sxs-lookup"><span data-stu-id="96cca-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="96cca-178">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="96cca-179">Condição</span><span class="sxs-lookup"><span data-stu-id="96cca-179">Condition</span></span>

<span data-ttu-id="96cca-180">Esses são os campos mínimos necessários, que são um subconjunto do perfil de condição [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="96cca-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="96cca-181">Code.Coding[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="96cca-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="96cca-182">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Patients também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="96cca-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="96cca-183">Data gravada</span><span class="sxs-lookup"><span data-stu-id="96cca-183">Date Recorded</span></span>
 - <span data-ttu-id="96cca-184">Severidade</span><span class="sxs-lookup"><span data-stu-id="96cca-184">Severity</span></span>

<span data-ttu-id="96cca-185">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="96cca-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="96cca-186">patient=\<patient id></span></span>
 - <span data-ttu-id="96cca-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="96cca-187">_count=\<max results></span></span>

<span data-ttu-id="96cca-188">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="96cca-188">See the following example of this call:</span></span>

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

<span data-ttu-id="96cca-189">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="96cca-190">Encounter</span><span class="sxs-lookup"><span data-stu-id="96cca-190">Encounter</span></span>

<span data-ttu-id="96cca-191">Esses são os campos mínimos necessários, que são um subconjunto dos campos "deve ter" do perfil do Us Core Encounter:</span><span class="sxs-lookup"><span data-stu-id="96cca-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="96cca-192">Status</span><span class="sxs-lookup"><span data-stu-id="96cca-192">Status</span></span>
 - <span data-ttu-id="96cca-193">Tipo[0]. Codificação[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="96cca-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="96cca-194">Além disso, os campos a seguir dos campos "deve ser suportado" do perfil do Us Core Encounter</span><span class="sxs-lookup"><span data-stu-id="96cca-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="96cca-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="96cca-195">Period.Start</span></span>
 - <span data-ttu-id="96cca-196">Local[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="96cca-196">Location[0].Location.Display</span></span>

<span data-ttu-id="96cca-197">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="96cca-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="96cca-198">patient=\<patient id></span></span>
 - <span data-ttu-id="96cca-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="96cca-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="96cca-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="96cca-200">_count=\<max results></span></span>

<span data-ttu-id="96cca-201">O objetivo é recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="96cca-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="96cca-202">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="96cca-202">Each encounter references a location resource.</span></span> <span data-ttu-id="96cca-203">A referência também deve incluir o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="96cca-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="96cca-204">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="96cca-204">See the following example of this call.</span></span>

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

<span data-ttu-id="96cca-205">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="96cca-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="96cca-206">AllergyIntolerance</span></span>

<span data-ttu-id="96cca-207">Esses são os campos mínimos necessários, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="96cca-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="96cca-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="96cca-208">Code.Text</span></span>
 - <span data-ttu-id="96cca-209">Code.Coding[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="96cca-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="96cca-210">Status</span><span class="sxs-lookup"><span data-stu-id="96cca-210">Status</span></span>

<span data-ttu-id="96cca-211">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Patients também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="96cca-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="96cca-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="96cca-212">RecordedDate</span></span>
 - <span data-ttu-id="96cca-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="96cca-213">Note.Text</span></span>
 - <span data-ttu-id="96cca-214">Reação[..]. Substancia.Text</span><span class="sxs-lookup"><span data-stu-id="96cca-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="96cca-215">Reação[..]. Manifestação[..]. Texto</span><span class="sxs-lookup"><span data-stu-id="96cca-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="96cca-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="96cca-216">Text.Div</span></span>

<span data-ttu-id="96cca-217">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="96cca-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="96cca-218">Patient =  \<patient id></span></span>

<span data-ttu-id="96cca-219">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="96cca-219">See the following example of this call:</span></span>

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

<span data-ttu-id="96cca-220">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="96cca-221">Ordem de Medicação</span><span class="sxs-lookup"><span data-stu-id="96cca-221">Medication Order</span></span>

<span data-ttu-id="96cca-222">Esses são os campos mínimos necessários, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="96cca-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="96cca-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="96cca-223">DateWritten</span></span>
 - <span data-ttu-id="96cca-224">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="96cca-224">Prescriber.Display</span></span>
 - <span data-ttu-id="96cca-225">Medication.Display (se referência)</span><span class="sxs-lookup"><span data-stu-id="96cca-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="96cca-226">Medication.Text (se conceito)</span><span class="sxs-lookup"><span data-stu-id="96cca-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="96cca-227">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Patients também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="96cca-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="96cca-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="96cca-228">DateEnded</span></span>
 - <span data-ttu-id="96cca-229">DoseInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="96cca-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="96cca-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="96cca-230">Text.Div</span></span>

<span data-ttu-id="96cca-231">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="96cca-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="96cca-232">patient=\<patient id></span></span>
 - <span data-ttu-id="96cca-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="96cca-233">_count=\<max results></span></span>

<span data-ttu-id="96cca-234">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="96cca-234">See the following example of this call:</span></span>

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

<span data-ttu-id="96cca-235">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="96cca-236">Cobertura</span><span class="sxs-lookup"><span data-stu-id="96cca-236">Coverage</span></span>

<span data-ttu-id="96cca-237">Esses são os campos mínimos necessários, não cobertos por perfis US Core ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="96cca-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="96cca-238">Pagador</span><span class="sxs-lookup"><span data-stu-id="96cca-238">Payor</span></span>

<span data-ttu-id="96cca-239">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="96cca-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="96cca-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="96cca-240">patient=\<patient id></span></span>

<span data-ttu-id="96cca-241">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="96cca-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="96cca-242">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="96cca-243">Localização</span><span class="sxs-lookup"><span data-stu-id="96cca-243">Location</span></span>

<span data-ttu-id="96cca-244">Esse recurso está sendo usado apenas como referência no [recurso Encounter.](#encounter)</span><span class="sxs-lookup"><span data-stu-id="96cca-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="96cca-245">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) outros detalhes sobre este conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="96cca-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
