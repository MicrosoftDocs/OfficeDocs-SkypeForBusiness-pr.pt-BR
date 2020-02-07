---
title: Interface do STU3 de integração do EHR e aplicativo pacientes
author: jambirk
ms.author: jambirk
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
ms.openlocfilehash: 6c7638436f35a1e460c176964dfc63624985b12e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827629"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="0c49b-103">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="0c49b-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="0c49b-104">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="0c49b-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="0c49b-105">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="0c49b-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="0c49b-106">Aguarde</span><span class="sxs-lookup"><span data-stu-id="0c49b-106">Patient</span></span>](#patient)
- [<span data-ttu-id="0c49b-107">Observações</span><span class="sxs-lookup"><span data-stu-id="0c49b-107">Observation</span></span>](#observation)
- [<span data-ttu-id="0c49b-108">Condição</span><span class="sxs-lookup"><span data-stu-id="0c49b-108">Condition</span></span>](#condition)
- [<span data-ttu-id="0c49b-109">Encontrá</span><span class="sxs-lookup"><span data-stu-id="0c49b-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="0c49b-110">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="0c49b-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="0c49b-111">Análise</span><span class="sxs-lookup"><span data-stu-id="0c49b-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="0c49b-112">[Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="0c49b-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="0c49b-113">Local (as informações necessárias deste recurso podem ser incluídas em encontrar)</span><span class="sxs-lookup"><span data-stu-id="0c49b-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="0c49b-114">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0c49b-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="0c49b-115">As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="0c49b-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="0c49b-116">O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="0c49b-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="0c49b-117">Para obter mais informações e exemplos, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)consulte.</span><span class="sxs-lookup"><span data-stu-id="0c49b-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="0c49b-118">Declaração de recursos</span><span class="sxs-lookup"><span data-stu-id="0c49b-118">Capability Statement</span></span>

<span data-ttu-id="0c49b-119">Estes são os campos mínimos obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="0c49b-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="0c49b-120">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="0c49b-120">REST</span></span>
   1. <span data-ttu-id="0c49b-121">Modo</span><span class="sxs-lookup"><span data-stu-id="0c49b-121">Mode</span></span>
   2. <span data-ttu-id="0c49b-122">Haja</span><span class="sxs-lookup"><span data-stu-id="0c49b-122">Interaction</span></span>
   3. <span data-ttu-id="0c49b-123">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="0c49b-123">Resource: Type</span></span>
   4. <span data-ttu-id="0c49b-124">Segurança: [extensão para URIs OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="0c49b-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="0c49b-125">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)</span><span class="sxs-lookup"><span data-stu-id="0c49b-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="0c49b-126">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="0c49b-127">Aguarde</span><span class="sxs-lookup"><span data-stu-id="0c49b-127">Patient</span></span>

<span data-ttu-id="0c49b-128">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:</span><span class="sxs-lookup"><span data-stu-id="0c49b-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="0c49b-129">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="0c49b-129">Name.Given</span></span>
2. <span data-ttu-id="0c49b-130">Nome. família</span><span class="sxs-lookup"><span data-stu-id="0c49b-130">Name.Family</span></span>
3. <span data-ttu-id="0c49b-131">Sexo</span><span class="sxs-lookup"><span data-stu-id="0c49b-131">Gender</span></span>
4. <span data-ttu-id="0c49b-132">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="0c49b-132">BirthDate</span></span>
5. <span data-ttu-id="0c49b-133">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="0c49b-133">MRN (Identifier)</span></span>

<span data-ttu-id="0c49b-134">Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0c49b-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="0c49b-135">Name. Use</span><span class="sxs-lookup"><span data-stu-id="0c49b-135">Name.Use</span></span>
2. <span data-ttu-id="0c49b-136">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="0c49b-136">Name.Prefix</span></span>
3. <span data-ttu-id="0c49b-137">[GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)</span><span class="sxs-lookup"><span data-stu-id="0c49b-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="0c49b-138">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-139">%</span><span class="sxs-lookup"><span data-stu-id="0c49b-139">id</span></span>
2. <span data-ttu-id="0c49b-140">Family = (procura por todos os pacientes cujo nome de família contenha o valor)</span><span class="sxs-lookup"><span data-stu-id="0c49b-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="0c49b-141">especificado =\<subcadeia de caracteres></span><span class="sxs-lookup"><span data-stu-id="0c49b-141">given=\<substring></span></span>
4. <span data-ttu-id="0c49b-142">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="0c49b-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="0c49b-143">Gênero = (valores sendo um dos sexo administrativos)</span><span class="sxs-lookup"><span data-stu-id="0c49b-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="0c49b-144">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="0c49b-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="0c49b-145">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e \_da contagem que será usado pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="0c49b-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="0c49b-146">identificador =\<MRN></span><span class="sxs-lookup"><span data-stu-id="0c49b-146">identifier=\<mrn></span></span>

<span data-ttu-id="0c49b-147">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0c49b-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="0c49b-148">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="0c49b-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="0c49b-149">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="0c49b-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="0c49b-150">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.</span><span class="sxs-lookup"><span data-stu-id="0c49b-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="0c49b-151">Nome</span><span class="sxs-lookup"><span data-stu-id="0c49b-151">Name</span></span>
- <span data-ttu-id="0c49b-152">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="0c49b-152">Birthdate</span></span>

<span data-ttu-id="0c49b-153">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="0c49b-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="0c49b-154">Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: dadas = Ruth&Family = preto</span><span class="sxs-lookup"><span data-stu-id="0c49b-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="0c49b-155">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"relation": "self", "URL": <fhir-Server>/patient/_search "}]," entry ": [{" fullUrl ": <fhir-Server>/patient/<> de identificação do paciente", "recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "texto": {"status": "gerado", "div", "div": "</span><span class="sxs-lookup"><span data-stu-id="0c49b-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="0c49b-156">\n</span><span class="sxs-lookup"><span data-stu-id="0c49b-156">\n</span></span>        <p><span data-ttu-id="0c49b-157">Ruth negro</span><span class="sxs-lookup"><span data-stu-id="0c49b-157">Ruth Black</span></span></p><span data-ttu-id="0c49b-158">\n</span><span class="sxs-lookup"><span data-stu-id="0c49b-158">\n</span></span>      </div><span data-ttu-id="0c49b-159">"}," identificador ": [{" Use ":" usual "," tipo ": {" codificação ": [{" sistema ":"http://hl7.org/fhir/v2/0203"," código ":" Mr "," exibir ":" número do registro médico "," userselected ": false}]," texto ":" número do registro médico "," sistema ":http://hospital.smarthealthit.org" "," valor ":" 1234567 "}]," ativo ": verdadeiro," nome ": [{" usar ":" oficial "," família ":" preto "," fornecido ": [" Ruth "," C ",</span><span class="sxs-lookup"><span data-stu-id="0c49b-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="0c49b-160">]}], "telecomunicações": [{"System": "Phone", "value": "800-599-2739", "valor": "800-808-7785", "Use": "móvel", "valor": "", "Use": "celular", "valor" gênero ":" email "," valor ":" ruth.black@example.com "," ",", "gênero": "feminino", "DataDeNascimento": "1951-08-23", "endereço": [{"usar": "Home", "linha": ["26 South RdApt 22"], "cidade": "Sapulpa", "estado": "OK", "CEP": "74066", "país": "EUA"}]}, "localizar": {"Mode": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="0c49b-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="0c49b-161">Solicitação: Obtenha o <fhir>/patient/<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="0c49b-162">Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>", "identificador": [{"usar": "usual", "tipo": {"codificação": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "Sr",}], "texto": "número do registro médico"}, "valor": "1234567"}], "nome": [{"usar": "oficial", "família": "Adams", "determinado": ["Daniel", "X."</span><span class="sxs-lookup"><span data-stu-id="0c49b-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="0c49b-163">]}], "gênero": "macho", "Datadenascimentoe": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="0c49b-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="0c49b-164">Consulte [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="0c49b-165">Observações</span><span class="sxs-lookup"><span data-stu-id="0c49b-165">Observation</span></span>

<span data-ttu-id="0c49b-166">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil Argonaut de sinais essenciais](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="0c49b-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="0c49b-167">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="0c49b-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="0c49b-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="0c49b-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="0c49b-169">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="0c49b-169">ValueQuantity.Value</span></span>

<span data-ttu-id="0c49b-170">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0c49b-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="0c49b-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="0c49b-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="0c49b-172">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="0c49b-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="0c49b-173">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-174">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-174">patient=\<patient id></span></span>
2. <span data-ttu-id="0c49b-175">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="0c49b-175">_sort=-date</span></span>
3. <span data-ttu-id="0c49b-176">Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.</span><span class="sxs-lookup"><span data-stu-id="0c49b-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="0c49b-177">Consulte este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="0c49b-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="0c49b-178">Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<paciente-ID>&categoria = sinais essenciais</span><span class="sxs-lookup"><span data-stu-id="0c49b-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="0c49b-179">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "observação", "ID": "<Resource-ID>", "categoria": [{"codificação": [{"sistema": "http://hl7.org/fhir/observation-category", "código": "código vital" Code ": {" Coding ": [{" System ":"http://loinc.org"," código ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valor ": 72,0," unidade ":" {batidas}/min "," sistema ":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="0c49b-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="0c49b-180">.</span><span class="sxs-lookup"><span data-stu-id="0c49b-180">.</span></span>
        <span data-ttu-id="0c49b-181">.</span><span class="sxs-lookup"><span data-stu-id="0c49b-181">.</span></span>
      <span data-ttu-id="0c49b-182">] }</span><span class="sxs-lookup"><span data-stu-id="0c49b-182">] }</span></span>

* * *

<span data-ttu-id="0c49b-183">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="0c49b-184">Condição</span><span class="sxs-lookup"><span data-stu-id="0c49b-184">Condition</span></span>

<span data-ttu-id="0c49b-185">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="0c49b-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="0c49b-186">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="0c49b-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="0c49b-187">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0c49b-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="0c49b-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="0c49b-188">AssertedDate</span></span>
2. <span data-ttu-id="0c49b-189">Gravidade</span><span class="sxs-lookup"><span data-stu-id="0c49b-189">Severity</span></span>

<span data-ttu-id="0c49b-190">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-191">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-191">patient=\<patient id></span></span>
2. <span data-ttu-id="0c49b-192">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="0c49b-192">_count=\<max results></span></span>

<span data-ttu-id="0c49b-193">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="0c49b-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="0c49b-194">Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="0c49b-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="0c49b-195">Resposta: {"resourceType": "Bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "total": 2, "entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "código": {"codificação": [{"sistema": "http://snomed.info/sct", "código": "185903001", "exibição": "precisa de imunização influenza",}]}, "severidade": {"codificação": [{"sistema":http://snomed.info/sct"", "código": "24484000", "exibir": "severado}]}," assertedDate ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="0c49b-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="0c49b-196">.</span><span class="sxs-lookup"><span data-stu-id="0c49b-196">.</span></span>
        <span data-ttu-id="0c49b-197">.</span><span class="sxs-lookup"><span data-stu-id="0c49b-197">.</span></span>
      <span data-ttu-id="0c49b-198">] }</span><span class="sxs-lookup"><span data-stu-id="0c49b-198">] }</span></span>

* * *
<span data-ttu-id="0c49b-199">Consulte [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="0c49b-200">Encontrá</span><span class="sxs-lookup"><span data-stu-id="0c49b-200">Encounter</span></span>

<span data-ttu-id="0c49b-201">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="0c49b-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="0c49b-202">Situação</span><span class="sxs-lookup"><span data-stu-id="0c49b-202">Status</span></span>
2. <span data-ttu-id="0c49b-203">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="0c49b-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="0c49b-204">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:</span><span class="sxs-lookup"><span data-stu-id="0c49b-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="0c49b-205">Período. início</span><span class="sxs-lookup"><span data-stu-id="0c49b-205">Period.Start</span></span>
2. <span data-ttu-id="0c49b-206">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="0c49b-206">Location[0].Location.Display</span></span>

<span data-ttu-id="0c49b-207">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-208">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-208">patient=\<patient id></span></span>
2. <span data-ttu-id="0c49b-209">_sort: desc =\<Field ex.</span><span class="sxs-lookup"><span data-stu-id="0c49b-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="0c49b-210">Data></span><span class="sxs-lookup"><span data-stu-id="0c49b-210">date></span></span>
3. <span data-ttu-id="0c49b-211">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="0c49b-211">_count=\<max results></span></span>

<span data-ttu-id="0c49b-212">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="0c49b-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="0c49b-213">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="0c49b-213">Each encounter references a location resource.</span></span> <span data-ttu-id="0c49b-214">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="0c49b-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="0c49b-215">Consulte [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="0c49b-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="0c49b-216">AllergyIntolerance</span></span>

<span data-ttu-id="0c49b-217">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="0c49b-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="0c49b-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="0c49b-218">Code.Text</span></span>
2. <span data-ttu-id="0c49b-219">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="0c49b-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="0c49b-220">ClinicalStatus/VerificationStatus (Lemos)</span><span class="sxs-lookup"><span data-stu-id="0c49b-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="0c49b-221">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:</span><span class="sxs-lookup"><span data-stu-id="0c49b-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="0c49b-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="0c49b-222">AssertedDate</span></span>
2. <span data-ttu-id="0c49b-223">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="0c49b-223">Note.Text</span></span>
3. <span data-ttu-id="0c49b-224">Reação</span><span class="sxs-lookup"><span data-stu-id="0c49b-224">Reaction</span></span>
    1. <span data-ttu-id="0c49b-225">Substância (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="0c49b-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="0c49b-226">Manifestação (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="0c49b-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="0c49b-227">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-228">Paciente = \<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-228">Patient =  \<patient id></span></span>

<span data-ttu-id="0c49b-229">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="0c49b-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="0c49b-230">Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="0c49b-231">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "clinicalStatus": "ativo", "verificationStatus": "confirmado", "códigohttp://rxnav.nlm.nih.gov/REST/Ndfrt": "N0000175503", "exibir": "sulfonamide Antibacterial",}], "texto", "exibir": "sulfonamide",}], "texto", "Ant ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reação ": [{" manifestação ": [{" codificação ": [{" sistema ":"http://snomed.info/sct"," código ":" 271807003 "," tela ":" capa rash ",}]," texto ":" capa rash "}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="0c49b-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="0c49b-232">Consulte [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="0c49b-233">Solicitação de medicação</span><span class="sxs-lookup"><span data-stu-id="0c49b-233">Medication Request</span></span>

<span data-ttu-id="0c49b-234">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="0c49b-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="0c49b-235">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="0c49b-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="0c49b-236">Medicação. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="0c49b-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="0c49b-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="0c49b-237">AuthoredOn</span></span>
4. <span data-ttu-id="0c49b-238">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="0c49b-238">Requester.Agent.Display</span></span>

<span data-ttu-id="0c49b-239">Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="0c49b-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="0c49b-240">DosageInstruction[..]. Textos</span><span class="sxs-lookup"><span data-stu-id="0c49b-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="0c49b-241">Textos</span><span class="sxs-lookup"><span data-stu-id="0c49b-241">Text</span></span>

<span data-ttu-id="0c49b-242">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-243">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-243">patient=\<patient id></span></span>
2. <span data-ttu-id="0c49b-244">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="0c49b-244">_count=\<max results></span></span>

<span data-ttu-id="0c49b-245">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="0c49b-246">Análise</span><span class="sxs-lookup"><span data-stu-id="0c49b-246">Coverage</span></span>

<span data-ttu-id="0c49b-247">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="0c49b-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="0c49b-248">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="0c49b-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="0c49b-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="0c49b-249">GroupDisplay</span></span>
    2. <span data-ttu-id="0c49b-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="0c49b-250">PlanDisplay</span></span>
2. <span data-ttu-id="0c49b-251">Período</span><span class="sxs-lookup"><span data-stu-id="0c49b-251">Period</span></span>
3. <span data-ttu-id="0c49b-252">Subscriberid</span><span class="sxs-lookup"><span data-stu-id="0c49b-252">SubscriberId</span></span>

<span data-ttu-id="0c49b-253">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="0c49b-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="0c49b-254">Paciente = \<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="0c49b-254">Patient = \<patient id></span></span>

<span data-ttu-id="0c49b-255">Consulte [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="0c49b-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
