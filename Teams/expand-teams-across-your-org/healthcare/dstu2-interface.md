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
# <a name="dstu2-interface-specification"></a><span data-ttu-id="1d6dd-103">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="1d6dd-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="1d6dd-104">A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="1d6dd-105">Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="1d6dd-106">Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="1d6dd-107">Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="1d6dd-108">Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="1d6dd-109">Confira o modelo Pacientes em Listas para começar.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="1d6dd-110">Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="1d6dd-111">Configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Pacientes do Microsoft Teams requer a compreensão de quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="1d6dd-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="1d6dd-113">Paciente</span><span class="sxs-lookup"><span data-stu-id="1d6dd-113">Patient</span></span>](#patient)
- [<span data-ttu-id="1d6dd-114">Observação</span><span class="sxs-lookup"><span data-stu-id="1d6dd-114">Observation</span></span>](#observation)
- [<span data-ttu-id="1d6dd-115">Condição</span><span class="sxs-lookup"><span data-stu-id="1d6dd-115">Condition</span></span>](#condition)
- [<span data-ttu-id="1d6dd-116">Encontro</span><span class="sxs-lookup"><span data-stu-id="1d6dd-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="1d6dd-117">Alerância alerância</span><span class="sxs-lookup"><span data-stu-id="1d6dd-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="1d6dd-118">Cobertura</span><span class="sxs-lookup"><span data-stu-id="1d6dd-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="1d6dd-119">Pedido de medicamentos</span><span class="sxs-lookup"><span data-stu-id="1d6dd-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="1d6dd-120">Local</span><span class="sxs-lookup"><span data-stu-id="1d6dd-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="1d6dd-121">O recurso Paciente é o único recurso obrigatório (sem o qual o aplicativo não será carregado.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="1d6dd-122">No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para a melhor experiência do usuário final com o aplicativo Pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="1d6dd-123">Consultas do aplicativo Pacientes do Microsoft Teams para mais de um recurso postam um pacote (LOTE) de solicitações à URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="1d6dd-124">O servidor processa cada solicitação e retorna um pacote de recursos de acordo com cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="1d6dd-125">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="1d6dd-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="1d6dd-126">Todos os seguintes recursos FHIR devem estar acessíveis por referência direta de recurso.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="1d6dd-127">Conjunto de campos mínimo necessário de conformidade</span><span class="sxs-lookup"><span data-stu-id="1d6dd-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="1d6dd-128">O FHIR Server deve implementar a declaração de conformidade para que tenhamos um resumo factual de suas capacidades.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="1d6dd-129">Esperamos os parâmetros abaixo em um servidor FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="1d6dd-130">Resto</span><span class="sxs-lookup"><span data-stu-id="1d6dd-130">REST</span></span>

    - <span data-ttu-id="1d6dd-131">Modo</span><span class="sxs-lookup"><span data-stu-id="1d6dd-131">Mode</span></span>
    - <span data-ttu-id="1d6dd-132">Interação</span><span class="sxs-lookup"><span data-stu-id="1d6dd-132">Interaction</span></span>
    - <span data-ttu-id="1d6dd-133">Recurso: Digite</span><span class="sxs-lookup"><span data-stu-id="1d6dd-133">Resource: Type</span></span>
    - <span data-ttu-id="1d6dd-134">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="1d6dd-135">FhirVersion (Nosso código requer isso para entender para qual versão devemos girar enquanto damos suporte a várias versões.)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="1d6dd-136">Veja [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="1d6dd-137">Paciente</span><span class="sxs-lookup"><span data-stu-id="1d6dd-137">Patient</span></span>

<span data-ttu-id="1d6dd-138">Estes são os campos mínimos necessários, que são um subconjunto dos campos de perfil do paciente [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="1d6dd-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="1d6dd-139">Name.Family</span></span>
 - <span data-ttu-id="1d6dd-140">Nome.Dado</span><span class="sxs-lookup"><span data-stu-id="1d6dd-140">Name.Given</span></span>
 - <span data-ttu-id="1d6dd-141">Gênero</span><span class="sxs-lookup"><span data-stu-id="1d6dd-141">Gender</span></span>
 - <span data-ttu-id="1d6dd-142">Nascimento</span><span class="sxs-lookup"><span data-stu-id="1d6dd-142">BirthDate</span></span>
 - <span data-ttu-id="1d6dd-143">MRN (Identificador)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-143">MRN (Identifier)</span></span>

<span data-ttu-id="1d6dd-144">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="1d6dd-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="1d6dd-145">Name.Use</span></span>
 - <span data-ttu-id="1d6dd-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="1d6dd-146">Name.Prefix</span></span>
 - <span data-ttu-id="1d6dd-147">CuidadoProvider (Esta referência no recurso Paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="1d6dd-148">Uma pesquisa de recursos usa o método POST em /Patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-149">Id</span><span class="sxs-lookup"><span data-stu-id="1d6dd-149">id</span></span>
 - <span data-ttu-id="1d6dd-150">família:contains=(procura todos os pacientes cujo nome da família contém o valor.)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="1d6dd-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="1d6dd-151">given=\<substring></span></span>
 - <span data-ttu-id="1d6dd-152">nome=\<substring></span><span class="sxs-lookup"><span data-stu-id="1d6dd-152">name=\<substring></span></span>
 - <span data-ttu-id="1d6dd-153">birthdate=(exact match)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="1d6dd-154">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="1d6dd-155">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa, e a contagem será usada pelo PatientsApp para limitar o número \_ de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="1d6dd-156">identificador=\<mrn></span><span class="sxs-lookup"><span data-stu-id="1d6dd-156">identifier=\<mrn></span></span>

<span data-ttu-id="1d6dd-157">O objetivo é poder pesquisar e filtrar um paciente pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="1d6dd-158">ID: Esta é a ID de recurso que todos os recursos em FHIR têm.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="1d6dd-159">MRN: Este é o identificador real do paciente que a equipe médica conheceria.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="1d6dd-160">Entendemos que esse MRN se baseia no tipo de identificador dentro do recurso identificador em FHIR</span><span class="sxs-lookup"><span data-stu-id="1d6dd-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="1d6dd-161">Nome</span><span class="sxs-lookup"><span data-stu-id="1d6dd-161">Name</span></span>
- <span data-ttu-id="1d6dd-162">Nascimento</span><span class="sxs-lookup"><span data-stu-id="1d6dd-162">Birthdate</span></span>

<span data-ttu-id="1d6dd-163">Veja o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="1d6dd-164">Veja [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="1d6dd-165">Observação</span><span class="sxs-lookup"><span data-stu-id="1d6dd-165">Observation</span></span>

<span data-ttu-id="1d6dd-166">Estes são os campos mínimos necessários, que são um subconjunto do perfil de sinais vitais Argonaut:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="1d6dd-167">Efetivo (data ou período)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="1d6dd-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="1d6dd-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="1d6dd-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="1d6dd-169">ValueQuantity.Value</span></span>

<span data-ttu-id="1d6dd-170">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="1d6dd-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="1d6dd-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="1d6dd-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="1d6dd-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="1d6dd-173">Se estiver usando observações de componentes, a mesma lógica se aplica a cada observação de componente.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="1d6dd-174">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-175">paciente=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="1d6dd-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="1d6dd-176">classificar:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="1d6dd-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="1d6dd-177">O objetivo é recuperar os sinais vitais mais recentes de um paciente, [VitalSigns.DSTU.saz] (observação?).</span><span class="sxs-lookup"><span data-stu-id="1d6dd-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="1d6dd-178">Veja [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="1d6dd-179">Condição</span><span class="sxs-lookup"><span data-stu-id="1d6dd-179">Condition</span></span>

<span data-ttu-id="1d6dd-180">Estes são os campos mínimos necessários, que são um subconjunto do perfil [da condição Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="1d6dd-181">Code.Coding[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="1d6dd-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="1d6dd-182">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="1d6dd-183">Data gravada</span><span class="sxs-lookup"><span data-stu-id="1d6dd-183">Date Recorded</span></span>
 - <span data-ttu-id="1d6dd-184">Gravidade</span><span class="sxs-lookup"><span data-stu-id="1d6dd-184">Severity</span></span>

<span data-ttu-id="1d6dd-185">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-186">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d6dd-186">patient=\<patient id></span></span>
 - <span data-ttu-id="1d6dd-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="1d6dd-187">_count=\<max results></span></span>

<span data-ttu-id="1d6dd-188">Veja o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-188">See the following example of this call:</span></span>

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

<span data-ttu-id="1d6dd-189">Veja [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="1d6dd-190">Encontro</span><span class="sxs-lookup"><span data-stu-id="1d6dd-190">Encounter</span></span>

<span data-ttu-id="1d6dd-191">Estes são os campos mínimos necessários, que são um subconjunto dos campos de perfil "deve ter" do perfil Do Core Encounter dos EUA:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="1d6dd-192">Status</span><span class="sxs-lookup"><span data-stu-id="1d6dd-192">Status</span></span>
 - <span data-ttu-id="1d6dd-193">Digite[0]. Codificação[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="1d6dd-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="1d6dd-194">Além disso, os campos a seguir dos campos "deve ser suportado" do perfil "deve ser suportado" do perfil us Core Encounter</span><span class="sxs-lookup"><span data-stu-id="1d6dd-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="1d6dd-195">Ponto.Início</span><span class="sxs-lookup"><span data-stu-id="1d6dd-195">Period.Start</span></span>
 - <span data-ttu-id="1d6dd-196">Local[0]. Local.Display</span><span class="sxs-lookup"><span data-stu-id="1d6dd-196">Location[0].Location.Display</span></span>

<span data-ttu-id="1d6dd-197">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-198">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d6dd-198">patient=\<patient id></span></span>
 - <span data-ttu-id="1d6dd-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="1d6dd-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="1d6dd-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="1d6dd-200">_count=\<max results></span></span>

<span data-ttu-id="1d6dd-201">O objetivo é recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="1d6dd-202">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-202">Each encounter references a location resource.</span></span> <span data-ttu-id="1d6dd-203">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="1d6dd-204">Veja o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-204">See the following example of this call.</span></span>

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

<span data-ttu-id="1d6dd-205">Veja [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="1d6dd-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="1d6dd-206">AllergyIntolerance</span></span>

<span data-ttu-id="1d6dd-207">Estes são os campos mínimos necessários, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="1d6dd-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="1d6dd-208">Code.Text</span></span>
 - <span data-ttu-id="1d6dd-209">Code.Coding[0]. Exibir</span><span class="sxs-lookup"><span data-stu-id="1d6dd-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="1d6dd-210">Status</span><span class="sxs-lookup"><span data-stu-id="1d6dd-210">Status</span></span>

<span data-ttu-id="1d6dd-211">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="1d6dd-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="1d6dd-212">RecordedDate</span></span>
 - <span data-ttu-id="1d6dd-213">Texto.anotação</span><span class="sxs-lookup"><span data-stu-id="1d6dd-213">Note.Text</span></span>
 - <span data-ttu-id="1d6dd-214">Reação[..]. Emoções.texto</span><span class="sxs-lookup"><span data-stu-id="1d6dd-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="1d6dd-215">Reação[..]. Demonstração[..]. Texto</span><span class="sxs-lookup"><span data-stu-id="1d6dd-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="1d6dd-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="1d6dd-216">Text.Div</span></span>

<span data-ttu-id="1d6dd-217">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-218">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="1d6dd-218">Patient =  \<patient id></span></span>

<span data-ttu-id="1d6dd-219">Veja o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-219">See the following example of this call:</span></span>

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

<span data-ttu-id="1d6dd-220">Veja [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="1d6dd-221">Pedido de medicamentos</span><span class="sxs-lookup"><span data-stu-id="1d6dd-221">Medication Order</span></span>

<span data-ttu-id="1d6dd-222">Estes são os campos mínimos necessários, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="1d6dd-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="1d6dd-223">DateWritten</span></span>
 - <span data-ttu-id="1d6dd-224">Desmador.display</span><span class="sxs-lookup"><span data-stu-id="1d6dd-224">Prescriber.Display</span></span>
 - <span data-ttu-id="1d6dd-225">Medication.Display (se referência)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="1d6dd-226">Medicação.Texto (se conceito)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="1d6dd-227">Além dos campos Argonaut, para uma ótima experiência do usuário, o aplicativo Pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="1d6dd-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="1d6dd-228">DateEnded</span></span>
 - <span data-ttu-id="1d6dd-229">DomosInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="1d6dd-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="1d6dd-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="1d6dd-230">Text.Div</span></span>

<span data-ttu-id="1d6dd-231">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-232">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d6dd-232">patient=\<patient id></span></span>
 - <span data-ttu-id="1d6dd-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="1d6dd-233">_count=\<max results></span></span>

<span data-ttu-id="1d6dd-234">Veja o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-234">See the following example of this call:</span></span>

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

<span data-ttu-id="1d6dd-235">Veja [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="1d6dd-236">Cobertura</span><span class="sxs-lookup"><span data-stu-id="1d6dd-236">Coverage</span></span>

<span data-ttu-id="1d6dd-237">Estes são os campos mínimos necessários, não cobertos por perfis Us Core ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="1d6dd-238">Pagador</span><span class="sxs-lookup"><span data-stu-id="1d6dd-238">Payor</span></span>

<span data-ttu-id="1d6dd-239">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="1d6dd-240">paciente=\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d6dd-240">patient=\<patient id></span></span>

<span data-ttu-id="1d6dd-241">Veja o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="1d6dd-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="1d6dd-242">Veja [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="1d6dd-243">Local</span><span class="sxs-lookup"><span data-stu-id="1d6dd-243">Location</span></span>

<span data-ttu-id="1d6dd-244">Esse recurso está sendo usado apenas como referência no [recurso Encontrar.](#encounter)</span><span class="sxs-lookup"><span data-stu-id="1d6dd-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="1d6dd-245">Veja [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="1d6dd-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
