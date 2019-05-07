---
title: Interface de integração STU3 App os pacientes e EHR
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
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643062"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="04dcc-103">Especificação de interface de STU3</span><span class="sxs-lookup"><span data-stu-id="04dcc-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="04dcc-104">Configurando ou reconfigurando a um servidor FHIR para trabalhar com o aplicativo Microsoft equipes pacientes exige noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="04dcc-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="04dcc-105">O servidor FHIR deve oferecer suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="04dcc-106">Paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-106">Patient</span></span>](#patient)
- [<span data-ttu-id="04dcc-107">Observação</span><span class="sxs-lookup"><span data-stu-id="04dcc-107">Observation</span></span>](#observation)
- [<span data-ttu-id="04dcc-108">Condição</span><span class="sxs-lookup"><span data-stu-id="04dcc-108">Condition</span></span>](#condition)
- [<span data-ttu-id="04dcc-109">Encontrar</span><span class="sxs-lookup"><span data-stu-id="04dcc-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="04dcc-110">Alergias Intolerance</span><span class="sxs-lookup"><span data-stu-id="04dcc-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="04dcc-111">Cobertura</span><span class="sxs-lookup"><span data-stu-id="04dcc-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="04dcc-112">[Instrução remédios](#medication-request) (substitui o MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="04dcc-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="04dcc-113">Local (as informações necessárias deste recurso pode ser incluídas na ocorrência)</span><span class="sxs-lookup"><span data-stu-id="04dcc-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="04dcc-114">O recurso de pacientes é o recurso obrigatório somente (sem que o aplicativo não será carregado nisso); No entanto, é recomendável que o parceiro implementar o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para uma melhor experiência do usuário final com o Microsoft equipes pacientes App.</span><span class="sxs-lookup"><span data-stu-id="04dcc-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="04dcc-115">Consultas do app pacientes de equipes da Microsoft para mais de um recurso devem lançar um pacote (em LOTES) de solicitações de URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="04dcc-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="04dcc-116">O servidor deverá processar cada solicitação e retornar um pacote dos recursos que correspondem a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="04dcc-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="04dcc-117">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="04dcc-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="04dcc-118">Instrução de recurso</span><span class="sxs-lookup"><span data-stu-id="04dcc-118">Capability Statement</span></span>

<span data-ttu-id="04dcc-119">Estes são os campos necessários mínimos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="04dcc-120">REST</span><span class="sxs-lookup"><span data-stu-id="04dcc-120">REST</span></span>
   1. <span data-ttu-id="04dcc-121">Modo</span><span class="sxs-lookup"><span data-stu-id="04dcc-121">Mode</span></span>
   2. <span data-ttu-id="04dcc-122">Interação</span><span class="sxs-lookup"><span data-stu-id="04dcc-122">Interaction</span></span>
   3. <span data-ttu-id="04dcc-123">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="04dcc-123">Resource: Type</span></span>
   4. <span data-ttu-id="04dcc-124">[Extensão para OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html) de segurança:</span><span class="sxs-lookup"><span data-stu-id="04dcc-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="04dcc-125">FhirVersion (nosso código requer essa opção para entender qual versão podemos deve pivô.)</span><span class="sxs-lookup"><span data-stu-id="04dcc-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="04dcc-126">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="04dcc-127">Paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-127">Patient</span></span>

<span data-ttu-id="04dcc-128">Aqui estão os campos necessários mínimos, que são um subconjunto dos campos perfil pacientes Argonaut:</span><span class="sxs-lookup"><span data-stu-id="04dcc-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="04dcc-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="04dcc-129">Name.Given</span></span>
2. <span data-ttu-id="04dcc-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="04dcc-130">Name.Family</span></span>
3. <span data-ttu-id="04dcc-131">Gênero</span><span class="sxs-lookup"><span data-stu-id="04dcc-131">Gender</span></span>
4. <span data-ttu-id="04dcc-132">Data de nascimento</span><span class="sxs-lookup"><span data-stu-id="04dcc-132">BirthDate</span></span>
5. <span data-ttu-id="04dcc-133">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="04dcc-133">MRN (Identifier)</span></span>

<span data-ttu-id="04dcc-134">Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="04dcc-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="04dcc-135">Name.Use</span></span>
2. <span data-ttu-id="04dcc-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="04dcc-136">Name.Prefix</span></span>
3. <span data-ttu-id="04dcc-137">[GeneralPractitioner] - GeneralPractitioner a referência deve ser incluída no recurso paciente (somente para exibição field)</span><span class="sxs-lookup"><span data-stu-id="04dcc-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="04dcc-138">Uma pesquisa de recurso usa o método POST no /Patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-139">ID</span><span class="sxs-lookup"><span data-stu-id="04dcc-139">id</span></span>
2. <span data-ttu-id="04dcc-140">família = (pesquisas para todos os pacientes cujo nome família contém o valor)</span><span class="sxs-lookup"><span data-stu-id="04dcc-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="04dcc-141">determinado =\<substring></span><span class="sxs-lookup"><span data-stu-id="04dcc-141">given=\<substring></span></span>
4. <span data-ttu-id="04dcc-142">Data de nascimento =(exact match)</span><span class="sxs-lookup"><span data-stu-id="04dcc-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="04dcc-143">Gênero = (valores sendo uma do gênero-administrativas)</span><span class="sxs-lookup"><span data-stu-id="04dcc-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="04dcc-144">\_Contagem de (número máximo de resultados que devem ser retornadas)</span><span class="sxs-lookup"><span data-stu-id="04dcc-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="04dcc-145">A resposta deve conter a contagem total de registros retornados como resultado de pesquisa e \_contagem será usada pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="04dcc-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="04dcc-146">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="04dcc-146">identifier=\<mrn></span></span>

<span data-ttu-id="04dcc-147">O objetivo é conseguir pesquisa e filtro do paciente pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="04dcc-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="04dcc-148">ID: Este é o ID de recurso que tem de cada recurso no FHIR.</span><span class="sxs-lookup"><span data-stu-id="04dcc-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="04dcc-149">MRN: Esse é o identificador real do paciente que seria saber a equipe de início de estudos clínicos.</span><span class="sxs-lookup"><span data-stu-id="04dcc-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="04dcc-150">Podemos entender que este MRN baseia-se ao tipo de identificador de recurso identificador na FHIR.</span><span class="sxs-lookup"><span data-stu-id="04dcc-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="04dcc-151">Nome</span><span class="sxs-lookup"><span data-stu-id="04dcc-151">Name</span></span>
- <span data-ttu-id="04dcc-152">Data de nascimento</span><span class="sxs-lookup"><span data-stu-id="04dcc-152">Birthdate</span></span>

<span data-ttu-id="04dcc-153">Consulte o exemplo a seguir da chamada:</span><span class="sxs-lookup"><span data-stu-id="04dcc-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="04dcc-154">Solicitação: Corpo da solicitação POST <fhir-server>/paciente/_search: determinado = ruth&family = preto</span><span class="sxs-lookup"><span data-stu-id="04dcc-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="04dcc-155">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"relation": "self", "url": <fhir-server>/paciente/_search "}],"entry": [{ "fullUrl": <fhir-server>/paciente/<patient-id> ","recurso": {"resourceType":"Paciente","id":"<patient id>","meta": {"versionId":"1","lastUpdated":" 2017-10-18T18:32:37.000 + 00:00 "},"text": {"status":"gerado","div ": "</span><span class="sxs-lookup"><span data-stu-id="04dcc-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="04dcc-156">\n.</span><span class="sxs-lookup"><span data-stu-id="04dcc-156">\n</span></span>        <p><span data-ttu-id="04dcc-157">Ruth preto</span><span class="sxs-lookup"><span data-stu-id="04dcc-157">Ruth Black</span></span></p><span data-ttu-id="04dcc-158">\n.</span><span class="sxs-lookup"><span data-stu-id="04dcc-158">\n</span></span>      </div><span data-ttu-id="04dcc-159">"},"identificador": [{"usar":"normal","tipo": {"codificação": [{"sistema":"http://hl7.org/fhir/v2/0203","código":"MR","Exibir":"número de registro médico","userSelected": false}],"text":"número de registro médico"},"system":"http://hospital.smarthealthit.org","value":"1234567"}],"ativo": true," o nome": [{"usar":"oficial","família":"Preto","dado": ["Ruth","C."</span><span class="sxs-lookup"><span data-stu-id="04dcc-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="04dcc-160">]}], "telecomunicações": [{"sistema": "telefônicas", "value": "800-599-2739", "o uso": "residencial"}, {"sistema": "telefônicas", "value": "800-808-7785", "o uso": "mobile"}, {"sistema": "email", "value": "ruth.black@example.com"}], "gênero": "feminino", "data de nascimento": "1951-08-23", " endereço": [{"usar":"casa","linha": ["26 Sul RdApt 22"],"city":"Sapulpa","estado":"Okey","postalCode":"74066","country":"EUA"}]},"pesquisa": {"modo":"correspondência"}}]}</span><span class="sxs-lookup"><span data-stu-id="04dcc-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="04dcc-161">Solicitação de: GET <fhir-server>/paciente/<patient-id></span><span class="sxs-lookup"><span data-stu-id="04dcc-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="04dcc-162">Resposta: {"resourceType": "Paciente", "id": "<patient id>", "identificador": [{"usar": "normal", "tipo": {"codificação": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR"}], "text": "número de registro médico"}, "value": "1234567"}], "nome": [{"usar": "oficial", " família":"Adams","dado": ["Daniel","X".</span><span class="sxs-lookup"><span data-stu-id="04dcc-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="04dcc-163">{}]], "gênero": "masculino", "data de nascimento": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="04dcc-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="04dcc-164">Consulte [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="04dcc-165">Observação</span><span class="sxs-lookup"><span data-stu-id="04dcc-165">Observation</span></span>

<span data-ttu-id="04dcc-166">Esses são os campos necessários mínimos, que são um subconjunto do [perfil de Argonaut Vital-sinais](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="04dcc-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="04dcc-167">Efetivo (data hora ou período)</span><span class="sxs-lookup"><span data-stu-id="04dcc-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="04dcc-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="04dcc-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="04dcc-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="04dcc-169">ValueQuantity.Value</span></span>

<span data-ttu-id="04dcc-170">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="04dcc-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="04dcc-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="04dcc-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="04dcc-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="04dcc-173">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-174">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-174">patient=\<patient id></span></span>
2. <span data-ttu-id="04dcc-175">Data = _sort</span><span class="sxs-lookup"><span data-stu-id="04dcc-175">_sort=-date</span></span>
3. <span data-ttu-id="04dcc-176">categoria (podemos irá consultar "category = sinais de vital") para recuperar a lista de sinais de vital.</span><span class="sxs-lookup"><span data-stu-id="04dcc-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="04dcc-177">Consulte este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="04dcc-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="04dcc-178">Solicitação: Obtenha <fhir-server>/Observação? paciente = <patient-id>&category = vital-sinais</span><span class="sxs-lookup"><span data-stu-id="04dcc-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="04dcc-179">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recurso": {"resourceType": "Observação", "id": "<resource id>", "categoria": [{"codificação": [{"sistema": "http://hl7.org/fhir/observation-category", "código": " vital-sinais de"}]}],"código": {"codificação": [{"sistema":"http://loinc.org","código":"8867-4","exibição":"heart_rate"}]},"effectiveDateTime":" 2009-04-08T00:00:00-06:00 ","valueQuantity": {"value": 72.0,"unidade":" {batidas} / min ","sistema":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="04dcc-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="04dcc-180">.</span><span class="sxs-lookup"><span data-stu-id="04dcc-180"></span></span>
        <span data-ttu-id="04dcc-181">.</span><span class="sxs-lookup"><span data-stu-id="04dcc-181"></span></span>
      <span data-ttu-id="04dcc-182">] }</span><span class="sxs-lookup"><span data-stu-id="04dcc-182"></span></span>

* * *

<span data-ttu-id="04dcc-183">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="04dcc-184">Condição</span><span class="sxs-lookup"><span data-stu-id="04dcc-184">Condition</span></span>

<span data-ttu-id="04dcc-185">Eis os campos necessários mínimos, que são um subconjunto do [perfil de condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="04dcc-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="04dcc-186">Code.Coding[0]. Exibição</span><span class="sxs-lookup"><span data-stu-id="04dcc-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="04dcc-187">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="04dcc-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="04dcc-188">AssertedDate</span></span>
2. <span data-ttu-id="04dcc-189">Severidade</span><span class="sxs-lookup"><span data-stu-id="04dcc-189">Severity</span></span>

<span data-ttu-id="04dcc-190">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-191">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-191">patient=\<patient id></span></span>
2. <span data-ttu-id="04dcc-192">Count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="04dcc-192">_count=\<max results></span></span>

<span data-ttu-id="04dcc-193">Consulte o exemplo a seguir desta chamada:</span><span class="sxs-lookup"><span data-stu-id="04dcc-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="04dcc-194">Solicitação: Obtenha <fhir-server>/condição? paciente = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="04dcc-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="04dcc-195">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": dia 2, "entry": [{"recurso": {"resourceType": "Condição", "id": "<resource id>", "código": {"codificação": [{"sistema": "http://snomed.info/sct", "código": "185903001", " Exibir":"Necessidades vacina de influenza,"}]},"gravidade": {"codificação": [{"sistema":"http://snomed.info/sct","código":"24484000","Exibir":"Grave"}]},"assertedDate":"2018-04-04"}},.</span><span class="sxs-lookup"><span data-stu-id="04dcc-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="04dcc-196">.</span><span class="sxs-lookup"><span data-stu-id="04dcc-196"></span></span>
        <span data-ttu-id="04dcc-197">.</span><span class="sxs-lookup"><span data-stu-id="04dcc-197"></span></span>
      <span data-ttu-id="04dcc-198">] }</span><span class="sxs-lookup"><span data-stu-id="04dcc-198"></span></span>

* * *
<span data-ttu-id="04dcc-199">Consulte [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="04dcc-200">Encontrar</span><span class="sxs-lookup"><span data-stu-id="04dcc-200">Encounter</span></span>

<span data-ttu-id="04dcc-201">Esses são os campos necessários mínimos, que são um subconjunto dos campos [perfil encontrar de núcleo dos EUA](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "deve ter").</span><span class="sxs-lookup"><span data-stu-id="04dcc-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="04dcc-202">Status</span><span class="sxs-lookup"><span data-stu-id="04dcc-202">Status</span></span>
2. <span data-ttu-id="04dcc-203">Tipo [0]. Codificação [0]. Exibição</span><span class="sxs-lookup"><span data-stu-id="04dcc-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="04dcc-204">Além disso, os seguintes campos do perfil nos encontrar Core "devem suportar" campos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="04dcc-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="04dcc-205">Period.Start</span></span>
2. <span data-ttu-id="04dcc-206">Local [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="04dcc-206">Location[0].Location.Display</span></span>

<span data-ttu-id="04dcc-207">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-208">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-208">patient=\<patient id></span></span>
2. <span data-ttu-id="04dcc-209">_sort:desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="04dcc-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="04dcc-210">date></span><span class="sxs-lookup"><span data-stu-id="04dcc-210">date></span></span>
3. <span data-ttu-id="04dcc-211">Count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="04dcc-211">_count=\<max results></span></span>

<span data-ttu-id="04dcc-212">O objetivo é conseguir recuperar local conhecido do último do paciente.</span><span class="sxs-lookup"><span data-stu-id="04dcc-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="04dcc-213">Cada ocorrência faz referência a um recurso local.</span><span class="sxs-lookup"><span data-stu-id="04dcc-213">Each encounter references a location resource.</span></span> <span data-ttu-id="04dcc-214">A referência também deverá incluir o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="04dcc-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="04dcc-215">Consulte [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="04dcc-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="04dcc-216">AllergyIntolerance</span></span>

<span data-ttu-id="04dcc-217">Estes são os campos necessários mínimos, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="04dcc-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="04dcc-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="04dcc-218">Code.Text</span></span>
2. <span data-ttu-id="04dcc-219">Code.Coding[0]. Exibição</span><span class="sxs-lookup"><span data-stu-id="04dcc-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="04dcc-220">ClinicalStatus/VerificationStatus (Lemos ambos)</span><span class="sxs-lookup"><span data-stu-id="04dcc-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="04dcc-221">Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler o campo a seguir:</span><span class="sxs-lookup"><span data-stu-id="04dcc-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="04dcc-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="04dcc-222">AssertedDate</span></span>
2. <span data-ttu-id="04dcc-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="04dcc-223">Note.Text</span></span>
3. <span data-ttu-id="04dcc-224">Reação</span><span class="sxs-lookup"><span data-stu-id="04dcc-224">Reaction</span></span>
    1. <span data-ttu-id="04dcc-225">Substância (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="04dcc-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="04dcc-226">Manifestação (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="04dcc-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="04dcc-227">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-228">Paciente = \<id> paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-228">Patient =  \<patient id></span></span>

<span data-ttu-id="04dcc-229">Consulte o exemplo a seguir da chamada:</span><span class="sxs-lookup"><span data-stu-id="04dcc-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="04dcc-230">Solicitação: Obtenha <fhir-server>/AllergyIntolerance? paciente = <patient-id></span><span class="sxs-lookup"><span data-stu-id="04dcc-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="04dcc-231">Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "clinicalStatus": "ativo", "ve rificationStatus":"confirmado","código": {"codificação": [{"sistema":"http://rxnav.nlm.nih.gov/REST/Ndfrt","código":"N0000175503","Exibir":"sulfonamide antibacterial,"}],"text":"ant de sulfonamide ibacterial"}"assertedDate":" 2018-01-01T00:00:00-07:00 ","reação": [{"manifestação": [{"codificação": [{"sistema":"http://snomed.info/sct","código":  "271807003", "Exibir": "explosão de capa,"}], "text": "explosão capa"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="04dcc-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="04dcc-232">Consulte [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="04dcc-233">Solicitação de remédios</span><span class="sxs-lookup"><span data-stu-id="04dcc-233">Medication Request</span></span>

<span data-ttu-id="04dcc-234">Estes são os campos necessários mínimos, que são um subconjunto dos [EUA Core remédios solicitar perfil](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="04dcc-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="04dcc-235">Medication.Display (se referência)</span><span class="sxs-lookup"><span data-stu-id="04dcc-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="04dcc-236">Medication.Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="04dcc-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="04dcc-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="04dcc-237">AuthoredOn</span></span>
4. <span data-ttu-id="04dcc-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="04dcc-238">Requester.Agent.Display</span></span>

<span data-ttu-id="04dcc-239">Além dos campos nos principais, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="04dcc-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="04dcc-240">DosageInstruction [..]. Texto</span><span class="sxs-lookup"><span data-stu-id="04dcc-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="04dcc-241">Texto</span><span class="sxs-lookup"><span data-stu-id="04dcc-241">Text</span></span>

<span data-ttu-id="04dcc-242">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-243">paciente =\<id> paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-243">patient=\<patient id></span></span>
2. <span data-ttu-id="04dcc-244">Count =\<results> max</span><span class="sxs-lookup"><span data-stu-id="04dcc-244">_count=\<max results></span></span>

<span data-ttu-id="04dcc-245">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="04dcc-246">Cobertura</span><span class="sxs-lookup"><span data-stu-id="04dcc-246">Coverage</span></span>

<span data-ttu-id="04dcc-247">Estes são os campos necessários mínimos, não cobertos por nós principais ou Argonaut perfis:</span><span class="sxs-lookup"><span data-stu-id="04dcc-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="04dcc-248">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="04dcc-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="04dcc-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="04dcc-249">GroupDisplay</span></span>
    2. <span data-ttu-id="04dcc-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="04dcc-250">PlanDisplay</span></span>
2. <span data-ttu-id="04dcc-251">Período</span><span class="sxs-lookup"><span data-stu-id="04dcc-251">Period</span></span>
3. <span data-ttu-id="04dcc-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="04dcc-252">SubscriberId</span></span>

<span data-ttu-id="04dcc-253">Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04dcc-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="04dcc-254">Paciente = \<id> paciente</span><span class="sxs-lookup"><span data-stu-id="04dcc-254">Patient = \<patient id></span></span>

<span data-ttu-id="04dcc-255">Consulte [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para outros detalhes sobre este campo definido.</span><span class="sxs-lookup"><span data-stu-id="04dcc-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
