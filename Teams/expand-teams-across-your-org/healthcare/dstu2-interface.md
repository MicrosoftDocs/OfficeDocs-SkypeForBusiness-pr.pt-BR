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
description: Integração do EHR do aplicativo Microsoft Teams pacientes
ms.openlocfilehash: 10a6b21e583b5fdd3e70857c4cfc5e7e21a7e988
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153813"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="9f3c0-103">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="9f3c0-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="9f3c0-104">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="9f3c0-105">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="9f3c0-106">Aguarde</span><span class="sxs-lookup"><span data-stu-id="9f3c0-106">Patient</span></span>](#patient)
- [<span data-ttu-id="9f3c0-107">Observações</span><span class="sxs-lookup"><span data-stu-id="9f3c0-107">Observation</span></span>](#observation)
- [<span data-ttu-id="9f3c0-108">Condição</span><span class="sxs-lookup"><span data-stu-id="9f3c0-108">Condition</span></span>](#condition)
- [<span data-ttu-id="9f3c0-109">Encontrá</span><span class="sxs-lookup"><span data-stu-id="9f3c0-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="9f3c0-110">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="9f3c0-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="9f3c0-111">Análise</span><span class="sxs-lookup"><span data-stu-id="9f3c0-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="9f3c0-112">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="9f3c0-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="9f3c0-113">Local</span><span class="sxs-lookup"><span data-stu-id="9f3c0-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="9f3c0-114">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="9f3c0-115">No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="9f3c0-116">Consultas do aplicativo Microsoft Teams pacientes para mais de um recurso poste um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="9f3c0-117">O servidor processa cada solicitação e retorna um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="9f3c0-118">Para obter mais informações e exemplos, [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)consulte.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="9f3c0-119">Todos os recursos de FHIR a seguir devem ser acessíveis pela referência a recursos diretos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="9f3c0-120">Conjunto de campos obrigatórios mínimos de conformidade</span><span class="sxs-lookup"><span data-stu-id="9f3c0-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="9f3c0-121">O servidor FHIR deve implementar a instrução de conformidade para que possamos ter um resumo factual de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="9f3c0-122">Esperamos os parâmetros a seguir em um servidor FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="9f3c0-123">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="9f3c0-123">REST</span></span>
   1. <span data-ttu-id="9f3c0-124">Modo</span><span class="sxs-lookup"><span data-stu-id="9f3c0-124">Mode</span></span>
   2. <span data-ttu-id="9f3c0-125">Haja</span><span class="sxs-lookup"><span data-stu-id="9f3c0-125">Interaction</span></span>
   3. <span data-ttu-id="9f3c0-126">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="9f3c0-126">Resource: Type</span></span>
   4. <span data-ttu-id="9f3c0-127">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="9f3c0-128">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotá-lo como suporte a várias versões.)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="9f3c0-129">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="9f3c0-130">Aguarde</span><span class="sxs-lookup"><span data-stu-id="9f3c0-130">Patient</span></span>

<span data-ttu-id="9f3c0-131">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de [perfil do paciente do Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="9f3c0-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="9f3c0-132">Nome. família</span><span class="sxs-lookup"><span data-stu-id="9f3c0-132">Name.Family</span></span>
2. <span data-ttu-id="9f3c0-133">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="9f3c0-133">Name.Given</span></span>
3. <span data-ttu-id="9f3c0-134">Sexo</span><span class="sxs-lookup"><span data-stu-id="9f3c0-134">Gender</span></span>
4. <span data-ttu-id="9f3c0-135">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="9f3c0-135">BirthDate</span></span>
5. <span data-ttu-id="9f3c0-136">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-136">MRN (Identifier)</span></span>

<span data-ttu-id="9f3c0-137">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="9f3c0-138">Name. Use</span><span class="sxs-lookup"><span data-stu-id="9f3c0-138">Name.Use</span></span>
2. <span data-ttu-id="9f3c0-139">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="9f3c0-139">Name.Prefix</span></span>
3. <span data-ttu-id="9f3c0-140">Cuidado: (essa referência ao recurso do paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="9f3c0-141">Solicitação: Obtenha o <fhir>/patient/<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="9f3c0-142">Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>",.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="9f3c0-143">.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-143">.</span></span>
      <span data-ttu-id="9f3c0-144">.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-144">.</span></span>
      <span data-ttu-id="9f3c0-145">"nome": [{"Use": "Official", "prefix": ["Sr"], "família": ["Chau"], "atribuído": ["Hugh"]}], "identificador": [{"usar": "oficial", "digite": {"codificação": [{"System": "https://hl7.org/fhir/v2/0203", "código": "Mr"}]}, "valor": "1234567", "cuidadosprovider": "macho", "datadenascimentoe": "1957-06-05", "cuidadosprovider": [{"display": "Jane Doe"}],}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="9f3c0-146">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-147">%</span><span class="sxs-lookup"><span data-stu-id="9f3c0-147">id</span></span>
2. <span data-ttu-id="9f3c0-148">Family: Contains = (procura por todos os pacientes cujo nome de família contenha o valor.)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="9f3c0-149">especificado =\<subcadeia de caracteres></span><span class="sxs-lookup"><span data-stu-id="9f3c0-149">given=\<substring></span></span>
4. <span data-ttu-id="9f3c0-150">name =\<subcadeia></span><span class="sxs-lookup"><span data-stu-id="9f3c0-150">name=\<substring></span></span>
5. <span data-ttu-id="9f3c0-151">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="9f3c0-152">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="9f3c0-153">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e \_a contagem será usada pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="9f3c0-154">identificador =\<MRN></span><span class="sxs-lookup"><span data-stu-id="9f3c0-154">identifier=\<mrn></span></span>

<span data-ttu-id="9f3c0-155">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="9f3c0-156">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="9f3c0-157">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="9f3c0-158">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR</span><span class="sxs-lookup"><span data-stu-id="9f3c0-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="9f3c0-159">Nome</span><span class="sxs-lookup"><span data-stu-id="9f3c0-159">Name</span></span>
- <span data-ttu-id="9f3c0-160">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="9f3c0-160">Birthdate</span></span>

<span data-ttu-id="9f3c0-161">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="9f3c0-162">Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: especificado = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="9f3c0-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="9f3c0-163">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>",.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="9f3c0-164">.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-164">.</span></span>
      <span data-ttu-id="9f3c0-165">.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-165">.</span></span>
      <span data-ttu-id="9f3c0-166">"entrada": [{"recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "nome": [{"texto": "Hugh Chau", "família": ["Chau"], "determinado": ["Hugh"]}], "gênero": "macho", "Datadenascimentoe": "1957-06-05"}, "localizar": {"Mode": "matching"}}]}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="9f3c0-167">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="9f3c0-168">Observações</span><span class="sxs-lookup"><span data-stu-id="9f3c0-168">Observation</span></span>

<span data-ttu-id="9f3c0-169">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil de sinais Argonaut vital:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="9f3c0-170">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="9f3c0-171">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="9f3c0-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="9f3c0-172">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="9f3c0-172">ValueQuantity.Value</span></span>

<span data-ttu-id="9f3c0-173">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="9f3c0-174">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="9f3c0-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="9f3c0-175">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="9f3c0-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="9f3c0-176">Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="9f3c0-177">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-178">paciente =\<identificação do paciente\></span><span class="sxs-lookup"><span data-stu-id="9f3c0-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="9f3c0-179">Sort: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="9f3c0-180">Data\></span><span class="sxs-lookup"><span data-stu-id="9f3c0-180">date\></span></span>

<span data-ttu-id="9f3c0-181">O objetivo é poder recuperar os mais recentes sinais essenciais para um paciente, [VitalSigns. DSTU. Saz] (observação?).</span><span class="sxs-lookup"><span data-stu-id="9f3c0-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="9f3c0-182">Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<o ID do paciente>&_sort:d ESC = data&Category = sinais essenciais</span><span class="sxs-lookup"><span data-stu-id="9f3c0-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="9f3c0-183">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "digite": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "reobservação", "ID": "<Resource-ID>", "categoria": {"codificação": "código": "informativo-sinais"}],}, "código": {"codificação": [{"System"http://loinc.org: "", "código": "39156-5", "display": "BMI"}],}, "effectiveDateTime": "2009-12-01", "valueQuantity": {"valor": 34,4, "unidade": "kg/m2", "sistema"http://unitsofmeasure.org: "", "código": "kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="9f3c0-184">.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-184">.</span></span>
        <span data-ttu-id="9f3c0-185">.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-185">.</span></span>
      <span data-ttu-id="9f3c0-186">] }</span><span class="sxs-lookup"><span data-stu-id="9f3c0-186">] }</span></span>

* * *

<span data-ttu-id="9f3c0-187">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="9f3c0-188">Condição</span><span class="sxs-lookup"><span data-stu-id="9f3c0-188">Condition</span></span>

<span data-ttu-id="9f3c0-189">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="9f3c0-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="9f3c0-190">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="9f3c0-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="9f3c0-191">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="9f3c0-192">Data de gravação</span><span class="sxs-lookup"><span data-stu-id="9f3c0-192">Date Recorded</span></span>
2. <span data-ttu-id="9f3c0-193">Gravidade</span><span class="sxs-lookup"><span data-stu-id="9f3c0-193">Severity</span></span>

<span data-ttu-id="9f3c0-194">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-195">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-195">patient=\<patient id></span></span>
2. <span data-ttu-id="9f3c0-196">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="9f3c0-196">_count=\<max results></span></span>

<span data-ttu-id="9f3c0-197">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="9f3c0-198">Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="9f3c0-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="9f3c0-199">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "Code": "386033004", "display": "neuropathy (Nervehttp://snomed.info/sctdanificado)" "," "," display ":" (dano) "}]}," dateRecorded ":" 2018-09-17 "," severidade ": {" codificação ": [{" syst em ":"http://snomed.info/sct"," código ":" 24484000 "," vídeo ":" severado "}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="9f3c0-200">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="9f3c0-201">Encontrá</span><span class="sxs-lookup"><span data-stu-id="9f3c0-201">Encounter</span></span>

<span data-ttu-id="9f3c0-202">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos perfil do núcleo dos EUA "deve ter":</span><span class="sxs-lookup"><span data-stu-id="9f3c0-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="9f3c0-203">Situação</span><span class="sxs-lookup"><span data-stu-id="9f3c0-203">Status</span></span>
2. <span data-ttu-id="9f3c0-204">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="9f3c0-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="9f3c0-205">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil principal</span><span class="sxs-lookup"><span data-stu-id="9f3c0-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="9f3c0-206">Período. início</span><span class="sxs-lookup"><span data-stu-id="9f3c0-206">Period.Start</span></span>
2. <span data-ttu-id="9f3c0-207">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="9f3c0-207">Location[0].Location.Display</span></span>

<span data-ttu-id="9f3c0-208">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-209">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-209">patient=\<patient id></span></span>
2. <span data-ttu-id="9f3c0-210">_sort: desc =\<Field ex.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="9f3c0-211">Data></span><span class="sxs-lookup"><span data-stu-id="9f3c0-211">date></span></span>
3. <span data-ttu-id="9f3c0-212">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="9f3c0-212">_count=\<max results></span></span>

<span data-ttu-id="9f3c0-213">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="9f3c0-214">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-214">Each encounter references a location resource.</span></span> <span data-ttu-id="9f3c0-215">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="9f3c0-216">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="9f3c0-217">Solicitação: Obtenha o <fhir-Server>/Encounter? paciente =<o ID do paciente>&_sort:d ESC = data&_count = 1</span><span class="sxs-lookup"><span data-stu-id="9f3c0-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="9f3c0-218">Resposta: {"ResourceType": "lote", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"ResourceType": "encontrar", "ID": "<Resource-ID>", "identificador": [{"usar": "oficial", "valor": "<id>"}], "status": "recebido", "tipo": [{"codificação": [{"exibir": "compromisso"}],}], "paciente": {"referência": "paciente/<paciente-ID>"}, "ponto": {"Iniciar": "09/17/2018 1:00:00 PM", "local": [{              "local": {"display": "Clinic-ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="9f3c0-219">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="9f3c0-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="9f3c0-220">AllergyIntolerance</span></span>

<span data-ttu-id="9f3c0-221">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="9f3c0-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="9f3c0-222">Code.Text</span></span>
2. <span data-ttu-id="9f3c0-223">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="9f3c0-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="9f3c0-224">Situação</span><span class="sxs-lookup"><span data-stu-id="9f3c0-224">Status</span></span>

<span data-ttu-id="9f3c0-225">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="9f3c0-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="9f3c0-226">RecordedDate</span></span>
2. <span data-ttu-id="9f3c0-227">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="9f3c0-227">Note.Text</span></span>
3. <span data-ttu-id="9f3c0-228">Reação [..]. Substância. Text</span><span class="sxs-lookup"><span data-stu-id="9f3c0-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="9f3c0-229">Reação [..]. Manifestação [..]. Textos</span><span class="sxs-lookup"><span data-stu-id="9f3c0-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="9f3c0-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="9f3c0-230">Text.Div</span></span>

<span data-ttu-id="9f3c0-231">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-232">Paciente = \<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-232">Patient =  \<patient id></span></span>

<span data-ttu-id="9f3c0-233">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="9f3c0-234">Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="9f3c0-235">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<> de ID de recurso", "recordedDate": "2018-09-17T07:00:00.000 Z", "substância": {"texto": "Cashew porcas"}, "status": "confirmado", "reação a um produto injetado"}, {"texto": "Cashew porca allergenic extrair produto que está incluído"}, "manifestati em ": [{" texto ":" anaphylactic reação "}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="9f3c0-236">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="9f3c0-237">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="9f3c0-237">Medication Order</span></span>

<span data-ttu-id="9f3c0-238">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="9f3c0-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="9f3c0-239">DateWritten</span></span>
2. <span data-ttu-id="9f3c0-240">Preparador. exibição</span><span class="sxs-lookup"><span data-stu-id="9f3c0-240">Prescriber.Display</span></span>
3. <span data-ttu-id="9f3c0-241">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="9f3c0-242">Medicação. Text (se conceito)</span><span class="sxs-lookup"><span data-stu-id="9f3c0-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="9f3c0-243">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="9f3c0-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="9f3c0-244">DateEnded</span></span>
2. <span data-ttu-id="9f3c0-245">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="9f3c0-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="9f3c0-246">Text. div</span><span class="sxs-lookup"><span data-stu-id="9f3c0-246">Text.Div</span></span>

<span data-ttu-id="9f3c0-247">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-248">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-248">patient=\<patient id></span></span>
2. <span data-ttu-id="9f3c0-249">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="9f3c0-249">_count=\<max results></span></span>

<span data-ttu-id="9f3c0-250">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="9f3c0-251">Solicitação: Obtenha o <fhir-Server>/MedicationOrder? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="9f3c0-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="9f3c0-252">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"texto": "Janete-Tablet MG"}, "preparador": {"exibir": "Janete"}, "dosageInstruction": [{"texto": "1 diário"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="9f3c0-253">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="9f3c0-254">Análise</span><span class="sxs-lookup"><span data-stu-id="9f3c0-254">Coverage</span></span>

<span data-ttu-id="9f3c0-255">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="9f3c0-256">Payor</span><span class="sxs-lookup"><span data-stu-id="9f3c0-256">Payor</span></span>

<span data-ttu-id="9f3c0-257">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="9f3c0-258">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-258">patient=\<patient id></span></span>

<span data-ttu-id="9f3c0-259">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="9f3c0-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="9f3c0-260">Solicitação: Obtenha o <fhir-Server>/Coverage? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="9f3c0-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="9f3c0-261">Resposta: {"resourceType": "pacote", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "Coverage", "ID": "<Resource-ID>", "plano": "não há seguro principal", "assinante": {"referência": "paciente/<paciente-identificação>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="9f3c0-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="9f3c0-262">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="9f3c0-263">Local</span><span class="sxs-lookup"><span data-stu-id="9f3c0-263">Location</span></span>

<span data-ttu-id="9f3c0-264">Esse recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="9f3c0-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="9f3c0-265">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="9f3c0-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
