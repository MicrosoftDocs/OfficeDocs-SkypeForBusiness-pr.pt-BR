---
title: " Interface de integração DSTU2 App os pacientes e EHR"
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integração de EHR app pacientes de equipes da Microsoft
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643060"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="4161d-103">Especificação de interface de DSTU2</span><span class="sxs-lookup"><span data-stu-id="4161d-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4161d-104">Configurando ou reconfigurando a um servidor FHIR para trabalhar com o aplicativo Microsoft equipes pacientes exige noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="4161d-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4161d-105">O servidor FHIR deve oferecer suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4161d-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4161d-106">Paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-106">Patient</span></span>](#patient)
- [<span data-ttu-id="4161d-107">Observação</span><span class="sxs-lookup"><span data-stu-id="4161d-107">Observation</span></span>](#observation)
- [<span data-ttu-id="4161d-108">Condição</span><span class="sxs-lookup"><span data-stu-id="4161d-108">Condition</span></span>](#condition)
- [<span data-ttu-id="4161d-109">Encontrar</span><span class="sxs-lookup"><span data-stu-id="4161d-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4161d-110">Intolerance alergia</span><span class="sxs-lookup"><span data-stu-id="4161d-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4161d-111">Cobertura</span><span class="sxs-lookup"><span data-stu-id="4161d-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="4161d-112">Ordem de remédios</span><span class="sxs-lookup"><span data-stu-id="4161d-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="4161d-113">Local</span><span class="sxs-lookup"><span data-stu-id="4161d-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="4161d-114">O recurso de pacientes é o obrigatório somente (sem que o aplicativo não será carregado nisso.</span><span class="sxs-lookup"><span data-stu-id="4161d-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="4161d-115">No entanto, é recomendável que o parceiro implementar o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para uma melhor experiência do usuário final com o Microsoft equipes pacientes App.</span><span class="sxs-lookup"><span data-stu-id="4161d-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4161d-116">Consultas do app pacientes de equipes da Microsoft para mais de um recurso postagem um pacote (em LOTES) de solicitações de URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="4161d-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4161d-117">O servidor processa cada solicitação e retorna um pacote dos recursos que correspondem a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="4161d-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4161d-118">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="4161d-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="4161d-119">Os seguintes recursos FHIR devem ser acessados pela referência direta de recursos.</span><span class="sxs-lookup"><span data-stu-id="4161d-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="4161d-120">Definir campo obrigatório mínimo de conformidade</span><span class="sxs-lookup"><span data-stu-id="4161d-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="4161d-121">O servidor FHIR deve implementar a declaração de conformidade de ter um resumo reais dos seus recursos.</span><span class="sxs-lookup"><span data-stu-id="4161d-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="4161d-122">Esperamos que os parâmetros em um servidor de FHIR DSTU2 abaixo:</span><span class="sxs-lookup"><span data-stu-id="4161d-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="4161d-123">REST</span><span class="sxs-lookup"><span data-stu-id="4161d-123">REST</span></span>
   1. <span data-ttu-id="4161d-124">Modo</span><span class="sxs-lookup"><span data-stu-id="4161d-124">Mode</span></span>
   2. <span data-ttu-id="4161d-125">Interação</span><span class="sxs-lookup"><span data-stu-id="4161d-125">Interaction</span></span>
   3. <span data-ttu-id="4161d-126">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="4161d-126">Resource: Type</span></span>
   4. <span data-ttu-id="4161d-127">[Extensão para OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html) de segurança:</span><span class="sxs-lookup"><span data-stu-id="4161d-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="4161d-128">FhirVersion (nosso código requer essa opção para entender qual versão podemos deve pivô conforme oferecemos suporte para várias versões.)</span><span class="sxs-lookup"><span data-stu-id="4161d-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="4161d-129">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4161d-130">Paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-130">Patient</span></span>

<span data-ttu-id="4161d-131">Estes são os campos necessários mínimos, que são um subconjunto dos campos de [perfil de pacientes Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="4161d-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="4161d-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="4161d-132">Name.Family</span></span>
2. <span data-ttu-id="4161d-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="4161d-133">Name.Given</span></span>
3. <span data-ttu-id="4161d-134">Gênero</span><span class="sxs-lookup"><span data-stu-id="4161d-134">Gender</span></span>
4. <span data-ttu-id="4161d-135">Data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4161d-135">BirthDate</span></span>
5. <span data-ttu-id="4161d-136">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="4161d-136">MRN (Identifier)</span></span>

<span data-ttu-id="4161d-137">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4161d-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="4161d-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="4161d-138">Name.Use</span></span>
2. <span data-ttu-id="4161d-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="4161d-139">Name.Prefix</span></span>
3. <span data-ttu-id="4161d-140">CareProvider (nesta referência do recurso de pacientes deve incluir os campos de exibição mostrados no exemplo a seguir).</span><span class="sxs-lookup"><span data-stu-id="4161d-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="4161d-141">Solicitação de: GET <fhir-server>/paciente/<patient-id></span><span class="sxs-lookup"><span data-stu-id="4161d-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="4161d-142">Resposta: {"resourceType": "Paciente", "id": "<patient-id>".</span><span class="sxs-lookup"><span data-stu-id="4161d-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="4161d-143">.</span><span class="sxs-lookup"><span data-stu-id="4161d-143"></span></span>
      <span data-ttu-id="4161d-144">.</span><span class="sxs-lookup"><span data-stu-id="4161d-144"></span></span>
      <span data-ttu-id="4161d-145">"name": [{"usar": "oficial", "prefixo": ["Mr"] "família": ["Chau"] "dado": ["Hugh"]}], "identificador": [{"usar": "oficial", "tipo": {"codificação": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR"}]}, "value": "1234567"}], "gênero": "masculino", "data de nascimento": "1957-06-05 ","careProvider": [{"Exibir":"Maria da Silva"}],}</span><span class="sxs-lookup"><span data-stu-id="4161d-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="4161d-146">Uma pesquisa de recurso usa o método POST no /Patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="4161d-147">ID</span><span class="sxs-lookup"><span data-stu-id="4161d-147">id</span></span>
2. <span data-ttu-id="4161d-148">família: contém = (procura por todos os pacientes cujo nome família contém o valor).</span><span class="sxs-lookup"><span data-stu-id="4161d-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="4161d-149">determinado =\<substring></span><span class="sxs-lookup"><span data-stu-id="4161d-149">given=\<substring></span></span>
4. <span data-ttu-id="4161d-150">nome =\<substring></span><span class="sxs-lookup"><span data-stu-id="4161d-150">name=\<substring></span></span>
5. <span data-ttu-id="4161d-151">Data de nascimento =(exact match)</span><span class="sxs-lookup"><span data-stu-id="4161d-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="4161d-152">\_Contagem de (número máximo de resultados que devem ser retornadas)</span><span class="sxs-lookup"><span data-stu-id="4161d-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4161d-153">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa, e \_contagem será usada pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="4161d-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="4161d-154">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="4161d-154">identifier=\<mrn></span></span>

<span data-ttu-id="4161d-155">O objetivo é conseguir pesquisa e filtro do paciente pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="4161d-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4161d-156">ID: Este é o ID de recurso que tem de cada recurso no FHIR.</span><span class="sxs-lookup"><span data-stu-id="4161d-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4161d-157">MRN: Esse é o identificador real do paciente que seria saber a equipe de início de estudos clínicos.</span><span class="sxs-lookup"><span data-stu-id="4161d-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4161d-158">Podemos entender que este MRN baseia-se ao tipo de identificador de recurso identificador na FHIR</span><span class="sxs-lookup"><span data-stu-id="4161d-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="4161d-159">Nome</span><span class="sxs-lookup"><span data-stu-id="4161d-159">Name</span></span>
- <span data-ttu-id="4161d-160">Data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4161d-160">Birthdate</span></span>

<span data-ttu-id="4161d-161">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="4161d-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="4161d-162">Solicitação: Corpo da solicitação POST <fhir-server>/paciente/_search: determinado = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="4161d-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="4161d-163">Resposta: {"resourceType": "Agrupam", "id": "<bundle-id>".</span><span class="sxs-lookup"><span data-stu-id="4161d-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="4161d-164">.</span><span class="sxs-lookup"><span data-stu-id="4161d-164"></span></span>
      <span data-ttu-id="4161d-165">.</span><span class="sxs-lookup"><span data-stu-id="4161d-165"></span></span>
      <span data-ttu-id="4161d-166">"entry": [{"recurso": {"resourceType": "Paciente", "id": "<patient id>", "nome": [{"text": "Hugh Chau", "família": ["Chau"] "dado": ["Hugh"]}], "gênero": "masculino", "data de nascimento": "1957-06-05"}, "pesquisa": {"modo": "correspondência"}}]}</span><span class="sxs-lookup"><span data-stu-id="4161d-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="4161d-167">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4161d-168">Observação</span><span class="sxs-lookup"><span data-stu-id="4161d-168">Observation</span></span>

<span data-ttu-id="4161d-169">Estes são os campos necessários mínimos, que são um subconjunto do perfil vital sinais Argonaut:</span><span class="sxs-lookup"><span data-stu-id="4161d-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="4161d-170">Efetivo (data hora ou período)</span><span class="sxs-lookup"><span data-stu-id="4161d-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="4161d-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="4161d-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="4161d-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="4161d-172">ValueQuantity.Value</span></span>

<span data-ttu-id="4161d-173">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4161d-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="4161d-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="4161d-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="4161d-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="4161d-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="4161d-176">Se usar observações do componente, a mesma lógica se aplica para Observação cada componente.</span><span class="sxs-lookup"><span data-stu-id="4161d-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="4161d-177">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4161d-178">paciente =\<id do paciente\></span><span class="sxs-lookup"><span data-stu-id="4161d-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="4161d-179">classificação: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="4161d-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="4161d-180">Data\></span><span class="sxs-lookup"><span data-stu-id="4161d-180">date\></span></span>

<span data-ttu-id="4161d-181">O objetivo é conseguir recuperar os sinais de vital mais recentes do paciente, [VitalSigns.DSTU.saz] (Observação).</span><span class="sxs-lookup"><span data-stu-id="4161d-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="4161d-182">Solicitação: Obtenha <fhir-server>/Observação? paciente = <patient-id>&_sort:desc = date&category = vital-sinais</span><span class="sxs-lookup"><span data-stu-id="4161d-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="4161d-183">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recurso": {"resourceType": "Observação", "id": "<resource id>", "categoria": {"codificação": [{código":"vital sinais"}],},"código": {" codificação": [{"sistema":"http://loinc.org","código":"39156-5","exibição":"IMC"}],},"effectiveDateTime":"2009-12-01","valueQuantity": {"value": 34.4,"unidade":" kg/m2","sistema":"http://unitsofmeasure.org","código":" kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="4161d-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="4161d-184">.</span><span class="sxs-lookup"><span data-stu-id="4161d-184"></span></span>
        <span data-ttu-id="4161d-185">.</span><span class="sxs-lookup"><span data-stu-id="4161d-185"></span></span>
      <span data-ttu-id="4161d-186">] }</span><span class="sxs-lookup"><span data-stu-id="4161d-186"></span></span>

* * *

<span data-ttu-id="4161d-187">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4161d-188">Condição</span><span class="sxs-lookup"><span data-stu-id="4161d-188">Condition</span></span>

<span data-ttu-id="4161d-189">Estes são os campos necessários mínimos, que são um subconjunto do [perfil de condição de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="4161d-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="4161d-190">Code.Coding[0]. Exibição</span><span class="sxs-lookup"><span data-stu-id="4161d-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="4161d-191">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4161d-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4161d-192">Data da gravação</span><span class="sxs-lookup"><span data-stu-id="4161d-192">Date Recorded</span></span>
2. <span data-ttu-id="4161d-193">Severidade</span><span class="sxs-lookup"><span data-stu-id="4161d-193">Severity</span></span>

<span data-ttu-id="4161d-194">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4161d-195">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-195">patient=\<patient id></span></span>
2. <span data-ttu-id="4161d-196">Count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="4161d-196">_count=\<max results></span></span>

<span data-ttu-id="4161d-197">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="4161d-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4161d-198">Solicitação: Obtenha <fhir-server>/condição? paciente = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4161d-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4161d-199">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "Condição", "id": "<resource id>", "código": {"codificação": [{               "sistema": "http://snomed.info/sct", "código": "386033004", "Exibir": "Neuropathy (danos parte)"}]}, "dateRecorded": "2018-09-17", "gravidade": {"codificação": [{"syst em":"http://snomed.info/sct","código":"24484000","Exibir":"Grave"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="4161d-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="4161d-200">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4161d-201">Encontrar</span><span class="sxs-lookup"><span data-stu-id="4161d-201">Encounter</span></span>

<span data-ttu-id="4161d-202">Estes são os campos necessários mínimos, que são um subconjunto dos EUA Core encontrar perfil "deve ter" campos:</span><span class="sxs-lookup"><span data-stu-id="4161d-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="4161d-203">Status</span><span class="sxs-lookup"><span data-stu-id="4161d-203">Status</span></span>
2. <span data-ttu-id="4161d-204">Tipo [0]. Codificação [0]. Exibição</span><span class="sxs-lookup"><span data-stu-id="4161d-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4161d-205">Além disso, os seguintes campos do perfil nos encontrar Core "devem suportar" fields</span><span class="sxs-lookup"><span data-stu-id="4161d-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="4161d-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="4161d-206">Period.Start</span></span>
2. <span data-ttu-id="4161d-207">Local [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="4161d-207">Location[0].Location.Display</span></span>

<span data-ttu-id="4161d-208">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4161d-209">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-209">patient=\<patient id></span></span>
2. <span data-ttu-id="4161d-210">_sort:desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="4161d-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="4161d-211">date></span><span class="sxs-lookup"><span data-stu-id="4161d-211">date></span></span>
3. <span data-ttu-id="4161d-212">Count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="4161d-212">_count=\<max results></span></span>

<span data-ttu-id="4161d-213">O objetivo é conseguir recuperar local conhecido do último do paciente.</span><span class="sxs-lookup"><span data-stu-id="4161d-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="4161d-214">Cada ocorrência faz referência a um recurso local.</span><span class="sxs-lookup"><span data-stu-id="4161d-214">Each encounter references a location resource.</span></span> <span data-ttu-id="4161d-215">A referência também deverá incluir o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="4161d-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="4161d-216">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="4161d-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="4161d-217">Solicitação: Obtenha <fhir-server>/ocorrência? paciente = <patient-id>&_sort:desc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="4161d-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="4161d-218">Resposta: {"resourceType": "Pacote", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "Encontrar", "id": "<resource id>", "identificador": [{"usar": "oficial", "value": "<id>"}], "status" : "chegou", "digite": [{"codificação": [{"Exibir": "Compromisso"}],}], "paciente": {"referência": "<patient/paciente-id>"}, "ponto": {"Iniciar": "17/09/2018 1:00:00 PM"}, "local": [{              "local": {"Exibir": "Inicial – ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4161d-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4161d-219">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4161d-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4161d-220">AllergyIntolerance</span></span>

<span data-ttu-id="4161d-221">Estes são os campos necessários mínimos, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="4161d-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="4161d-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="4161d-222">Code.Text</span></span>
2. <span data-ttu-id="4161d-223">Code.Coding[0]. Exibição</span><span class="sxs-lookup"><span data-stu-id="4161d-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="4161d-224">Status</span><span class="sxs-lookup"><span data-stu-id="4161d-224">Status</span></span>

<span data-ttu-id="4161d-225">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4161d-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="4161d-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="4161d-226">RecordedDate</span></span>
2. <span data-ttu-id="4161d-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="4161d-227">Note.Text</span></span>
3. <span data-ttu-id="4161d-228">Reação [..]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="4161d-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="4161d-229">Reação [..]. Manifestação [..]. Texto</span><span class="sxs-lookup"><span data-stu-id="4161d-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="4161d-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="4161d-230">Text.Div</span></span>

<span data-ttu-id="4161d-231">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4161d-232">Paciente = \<id> paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-232">Patient =  \<patient id></span></span>

<span data-ttu-id="4161d-233">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="4161d-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4161d-234">Solicitação: Obtenha <fhir-server>/AllergyIntolerance? paciente = <patient-id></span><span class="sxs-lookup"><span data-stu-id="4161d-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="4161d-235">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "recordedDate": "2018-09-17T07:00:00.00 0Z","substância": {"text":"Cashew nuts"},"status":"confirmado","reação": [{"substância": {"text":"cashew Porca allergenic extrair Injectable produto"},"manifestati em": [{"text":"Anaphylactic reação"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4161d-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4161d-236">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="4161d-237">Ordem de remédios</span><span class="sxs-lookup"><span data-stu-id="4161d-237">Medication Order</span></span>

<span data-ttu-id="4161d-238">Estes são os campos necessários mínimos, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="4161d-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="4161d-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="4161d-239">DateWritten</span></span>
2. <span data-ttu-id="4161d-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="4161d-240">Prescriber.Display</span></span>
3. <span data-ttu-id="4161d-241">Medication.Display (se referência)</span><span class="sxs-lookup"><span data-stu-id="4161d-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="4161d-242">Medication.Text (se conceito)</span><span class="sxs-lookup"><span data-stu-id="4161d-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="4161d-243">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4161d-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4161d-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="4161d-244">DateEnded</span></span>
2. <span data-ttu-id="4161d-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="4161d-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="4161d-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="4161d-246">Text.Div</span></span>

<span data-ttu-id="4161d-247">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4161d-248">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-248">patient=\<patient id></span></span>
2. <span data-ttu-id="4161d-249">Count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="4161d-249">_count=\<max results></span></span>

<span data-ttu-id="4161d-250">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="4161d-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4161d-251">Solicitação: Obtenha <fhir-server>/MedicationOrder? paciente = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4161d-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4161d-252">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "MedicationOrder", "id": "<resource id>", "dateWritten": "2018-09-17", "medi cationCodeableConcept": {"text":"Lisinopril 20 MG Oral Tablet"},"prescriber": {"Exibir":"Maria da Silva"},"dosageInstruction": [{"text":"1 diariamente"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4161d-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="4161d-253">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4161d-254">Cobertura</span><span class="sxs-lookup"><span data-stu-id="4161d-254">Coverage</span></span>

<span data-ttu-id="4161d-255">Estes são os campos necessários mínimos, não cobertos por nós principais ou Argonaut perfis:</span><span class="sxs-lookup"><span data-stu-id="4161d-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="4161d-256">Outros fornecedores</span><span class="sxs-lookup"><span data-stu-id="4161d-256">Payor</span></span>

<span data-ttu-id="4161d-257">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4161d-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4161d-258">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="4161d-258">patient=\<patient id></span></span>

<span data-ttu-id="4161d-259">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="4161d-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4161d-260">Solicitação: Obtenha <fhir server>/cobertura? paciente = <patient-id></span><span class="sxs-lookup"><span data-stu-id="4161d-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="4161d-261">Resposta: {"resourceType": "Pacote", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "Cobertura", "id": "<resource id>", "Planejar": "Não principal Insurance", "assinante": {"referência": "paciente / <patient-id> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="4161d-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="4161d-262">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="4161d-263">Local</span><span class="sxs-lookup"><span data-stu-id="4161d-263">Location</span></span>

<span data-ttu-id="4161d-264">Este recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="4161d-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="4161d-265">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="4161d-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
