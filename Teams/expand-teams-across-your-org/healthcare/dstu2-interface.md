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
ms.openlocfilehash: d29dab88f6ee53eb4c758f6c95f71278e20ecdbe
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766974"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="82612-103">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="82612-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82612-104">**A partir de 30 de outubro de 2020, o aplicativo pacientes será preterido, e os usuários não poderão mais instalá-lo na App Store da equipe. Recomendamos que você comece a usar o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Microsoft Teams hoje mesmo.**</span><span class="sxs-lookup"><span data-stu-id="82612-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="82612-105">Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe.</span><span class="sxs-lookup"><span data-stu-id="82612-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="82612-106">Quando o aplicativo pacientes é desativado, todos os dados associados a ele serão mantidos nesse grupo, mas não poderão mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="82612-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="82612-107">Os usuários atuais podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="82612-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="82612-108">O [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal.</span><span class="sxs-lookup"><span data-stu-id="82612-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="82612-109">Com listas, as equipes de saúde podem criar listas de pacientes usando o modelo de pacientes interno, do zero ou importando dados para o Excel.</span><span class="sxs-lookup"><span data-stu-id="82612-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="82612-110">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="82612-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="82612-111">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="82612-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="82612-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="82612-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="82612-113">Aguarde</span><span class="sxs-lookup"><span data-stu-id="82612-113">Patient</span></span>](#patient)
- [<span data-ttu-id="82612-114">Observações</span><span class="sxs-lookup"><span data-stu-id="82612-114">Observation</span></span>](#observation)
- [<span data-ttu-id="82612-115">Condição</span><span class="sxs-lookup"><span data-stu-id="82612-115">Condition</span></span>](#condition)
- [<span data-ttu-id="82612-116">Encontrá</span><span class="sxs-lookup"><span data-stu-id="82612-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="82612-117">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="82612-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="82612-118">Análise</span><span class="sxs-lookup"><span data-stu-id="82612-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="82612-119">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="82612-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="82612-120">Local</span><span class="sxs-lookup"><span data-stu-id="82612-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="82612-121">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado.</span><span class="sxs-lookup"><span data-stu-id="82612-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="82612-122">No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="82612-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="82612-123">Consultas do aplicativo Microsoft Teams pacientes para mais de um recurso poste um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="82612-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="82612-124">O servidor processa cada solicitação e retorna um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="82612-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="82612-125">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="82612-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="82612-126">Todos os recursos de FHIR a seguir devem ser acessíveis pela referência a recursos diretos.</span><span class="sxs-lookup"><span data-stu-id="82612-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="82612-127">Conjunto de campos obrigatórios mínimos de conformidade</span><span class="sxs-lookup"><span data-stu-id="82612-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="82612-128">O servidor FHIR deve implementar a instrução de conformidade para que possamos ter um resumo factual de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="82612-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="82612-129">Esperamos os parâmetros a seguir em um servidor FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="82612-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="82612-130">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="82612-130">REST</span></span>

    - <span data-ttu-id="82612-131">Modo</span><span class="sxs-lookup"><span data-stu-id="82612-131">Mode</span></span>
    - <span data-ttu-id="82612-132">Haja</span><span class="sxs-lookup"><span data-stu-id="82612-132">Interaction</span></span>
    - <span data-ttu-id="82612-133">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="82612-133">Resource: Type</span></span>
    - <span data-ttu-id="82612-134">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="82612-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="82612-135">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotá-lo como suporte a várias versões.)</span><span class="sxs-lookup"><span data-stu-id="82612-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="82612-136">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="82612-137">Aguarde</span><span class="sxs-lookup"><span data-stu-id="82612-137">Patient</span></span>

<span data-ttu-id="82612-138">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de [perfil do paciente do Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="82612-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="82612-139">Nome. família</span><span class="sxs-lookup"><span data-stu-id="82612-139">Name.Family</span></span>
 - <span data-ttu-id="82612-140">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="82612-140">Name.Given</span></span>
 - <span data-ttu-id="82612-141">Sexo</span><span class="sxs-lookup"><span data-stu-id="82612-141">Gender</span></span>
 - <span data-ttu-id="82612-142">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="82612-142">BirthDate</span></span>
 - <span data-ttu-id="82612-143">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="82612-143">MRN (Identifier)</span></span>

<span data-ttu-id="82612-144">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="82612-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="82612-145">Name. Use</span><span class="sxs-lookup"><span data-stu-id="82612-145">Name.Use</span></span>
 - <span data-ttu-id="82612-146">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="82612-146">Name.Prefix</span></span>
 - <span data-ttu-id="82612-147">Cuidado: (essa referência ao recurso do paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)</span><span class="sxs-lookup"><span data-stu-id="82612-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="82612-148">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="82612-149">%</span><span class="sxs-lookup"><span data-stu-id="82612-149">id</span></span>
 - <span data-ttu-id="82612-150">Family: Contains = (procura por todos os pacientes cujo nome de família contenha o valor.)</span><span class="sxs-lookup"><span data-stu-id="82612-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="82612-151">especificado =\<substring></span><span class="sxs-lookup"><span data-stu-id="82612-151">given=\<substring></span></span>
 - <span data-ttu-id="82612-152">nome =\<substring></span><span class="sxs-lookup"><span data-stu-id="82612-152">name=\<substring></span></span>
 - <span data-ttu-id="82612-153">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="82612-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="82612-154">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="82612-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="82612-155">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a \_ contagem será usada pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="82612-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="82612-156">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="82612-156">identifier=\<mrn></span></span>

<span data-ttu-id="82612-157">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="82612-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="82612-158">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="82612-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="82612-159">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="82612-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="82612-160">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR</span><span class="sxs-lookup"><span data-stu-id="82612-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="82612-161">Nome</span><span class="sxs-lookup"><span data-stu-id="82612-161">Name</span></span>
- <span data-ttu-id="82612-162">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="82612-162">Birthdate</span></span>

<span data-ttu-id="82612-163">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="82612-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="82612-164">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="82612-165">Observações</span><span class="sxs-lookup"><span data-stu-id="82612-165">Observation</span></span>

<span data-ttu-id="82612-166">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil de sinais Argonaut vital:</span><span class="sxs-lookup"><span data-stu-id="82612-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="82612-167">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="82612-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="82612-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="82612-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="82612-169">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="82612-169">ValueQuantity.Value</span></span>

<span data-ttu-id="82612-170">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="82612-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="82612-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="82612-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="82612-172">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="82612-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="82612-173">Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.</span><span class="sxs-lookup"><span data-stu-id="82612-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="82612-174">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="82612-175">paciente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="82612-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="82612-176">classificar: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="82612-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="82612-177">O objetivo é poder recuperar os mais recentes sinais essenciais para um paciente, [VitalSigns. DSTU. Saz] (observação?).</span><span class="sxs-lookup"><span data-stu-id="82612-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="82612-178">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="82612-179">Condição</span><span class="sxs-lookup"><span data-stu-id="82612-179">Condition</span></span>

<span data-ttu-id="82612-180">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="82612-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="82612-181">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="82612-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="82612-182">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="82612-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="82612-183">Data de gravação</span><span class="sxs-lookup"><span data-stu-id="82612-183">Date Recorded</span></span>
 - <span data-ttu-id="82612-184">Gravidade</span><span class="sxs-lookup"><span data-stu-id="82612-184">Severity</span></span>

<span data-ttu-id="82612-185">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="82612-186">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="82612-186">patient=\<patient id></span></span>
 - <span data-ttu-id="82612-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="82612-187">_count=\<max results></span></span>

<span data-ttu-id="82612-188">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="82612-188">See the following example of this call:</span></span>

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

<span data-ttu-id="82612-189">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="82612-190">Encontrá</span><span class="sxs-lookup"><span data-stu-id="82612-190">Encounter</span></span>

<span data-ttu-id="82612-191">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos perfil do núcleo dos EUA "deve ter":</span><span class="sxs-lookup"><span data-stu-id="82612-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="82612-192">Situação</span><span class="sxs-lookup"><span data-stu-id="82612-192">Status</span></span>
 - <span data-ttu-id="82612-193">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="82612-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="82612-194">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil principal</span><span class="sxs-lookup"><span data-stu-id="82612-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="82612-195">Período. início</span><span class="sxs-lookup"><span data-stu-id="82612-195">Period.Start</span></span>
 - <span data-ttu-id="82612-196">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="82612-196">Location[0].Location.Display</span></span>

<span data-ttu-id="82612-197">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="82612-198">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="82612-198">patient=\<patient id></span></span>
 - <span data-ttu-id="82612-199">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="82612-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="82612-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="82612-200">_count=\<max results></span></span>

<span data-ttu-id="82612-201">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="82612-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="82612-202">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="82612-202">Each encounter references a location resource.</span></span> <span data-ttu-id="82612-203">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="82612-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="82612-204">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="82612-204">See the following example of this call.</span></span>

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

<span data-ttu-id="82612-205">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="82612-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="82612-206">AllergyIntolerance</span></span>

<span data-ttu-id="82612-207">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="82612-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="82612-208">Code. Text</span><span class="sxs-lookup"><span data-stu-id="82612-208">Code.Text</span></span>
 - <span data-ttu-id="82612-209">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="82612-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="82612-210">Situação</span><span class="sxs-lookup"><span data-stu-id="82612-210">Status</span></span>

<span data-ttu-id="82612-211">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="82612-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="82612-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="82612-212">RecordedDate</span></span>
 - <span data-ttu-id="82612-213">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="82612-213">Note.Text</span></span>
 - <span data-ttu-id="82612-214">Reação [..]. Substância. Text</span><span class="sxs-lookup"><span data-stu-id="82612-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="82612-215">Reação [..]. Manifestação [..]. Textos</span><span class="sxs-lookup"><span data-stu-id="82612-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="82612-216">Text. div</span><span class="sxs-lookup"><span data-stu-id="82612-216">Text.Div</span></span>

<span data-ttu-id="82612-217">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="82612-218">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="82612-218">Patient =  \<patient id></span></span>

<span data-ttu-id="82612-219">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="82612-219">See the following example of this call:</span></span>

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

<span data-ttu-id="82612-220">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="82612-221">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="82612-221">Medication Order</span></span>

<span data-ttu-id="82612-222">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="82612-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="82612-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="82612-223">DateWritten</span></span>
 - <span data-ttu-id="82612-224">Preparador. exibição</span><span class="sxs-lookup"><span data-stu-id="82612-224">Prescriber.Display</span></span>
 - <span data-ttu-id="82612-225">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="82612-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="82612-226">Medicação. Text (se conceito)</span><span class="sxs-lookup"><span data-stu-id="82612-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="82612-227">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="82612-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="82612-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="82612-228">DateEnded</span></span>
 - <span data-ttu-id="82612-229">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="82612-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="82612-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="82612-230">Text.Div</span></span>

<span data-ttu-id="82612-231">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="82612-232">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="82612-232">patient=\<patient id></span></span>
 - <span data-ttu-id="82612-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="82612-233">_count=\<max results></span></span>

<span data-ttu-id="82612-234">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="82612-234">See the following example of this call:</span></span>

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

<span data-ttu-id="82612-235">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="82612-236">Análise</span><span class="sxs-lookup"><span data-stu-id="82612-236">Coverage</span></span>

<span data-ttu-id="82612-237">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="82612-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="82612-238">Payor</span><span class="sxs-lookup"><span data-stu-id="82612-238">Payor</span></span>

<span data-ttu-id="82612-239">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="82612-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="82612-240">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="82612-240">patient=\<patient id></span></span>

<span data-ttu-id="82612-241">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="82612-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="82612-242">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="82612-243">Local</span><span class="sxs-lookup"><span data-stu-id="82612-243">Location</span></span>

<span data-ttu-id="82612-244">Esse recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="82612-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="82612-245">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="82612-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
