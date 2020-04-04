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
description: Saiba mais sobre a especificação de interface STU3 no Teams, incluindo configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Microsoft Teams pacientes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 35d887575ffb894b7a47e50511e6bd6c3a9a75d1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141194"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="64656-103">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="64656-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="64656-104">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="64656-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="64656-105">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="64656-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="64656-106">Aguarde</span><span class="sxs-lookup"><span data-stu-id="64656-106">Patient</span></span>](#patient)
- [<span data-ttu-id="64656-107">Observações</span><span class="sxs-lookup"><span data-stu-id="64656-107">Observation</span></span>](#observation)
- [<span data-ttu-id="64656-108">Condição</span><span class="sxs-lookup"><span data-stu-id="64656-108">Condition</span></span>](#condition)
- [<span data-ttu-id="64656-109">Encontrá</span><span class="sxs-lookup"><span data-stu-id="64656-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="64656-110">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="64656-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="64656-111">Análise</span><span class="sxs-lookup"><span data-stu-id="64656-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="64656-112">[Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="64656-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="64656-113">Local (as informações necessárias deste recurso podem ser incluídas em encontrar)</span><span class="sxs-lookup"><span data-stu-id="64656-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="64656-114">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64656-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="64656-115">As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="64656-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="64656-116">O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="64656-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="64656-117">Para obter mais informações e exemplos, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)consulte.</span><span class="sxs-lookup"><span data-stu-id="64656-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="64656-118">Declaração de recursos</span><span class="sxs-lookup"><span data-stu-id="64656-118">Capability Statement</span></span>

<span data-ttu-id="64656-119">Estes são os campos mínimos obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="64656-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="64656-120">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="64656-120">REST</span></span>
   1. <span data-ttu-id="64656-121">Modo</span><span class="sxs-lookup"><span data-stu-id="64656-121">Mode</span></span>
   2. <span data-ttu-id="64656-122">Haja</span><span class="sxs-lookup"><span data-stu-id="64656-122">Interaction</span></span>
   3. <span data-ttu-id="64656-123">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="64656-123">Resource: Type</span></span>
   4. <span data-ttu-id="64656-124">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="64656-124">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="64656-125">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)</span><span class="sxs-lookup"><span data-stu-id="64656-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="64656-126">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="64656-127">Aguarde</span><span class="sxs-lookup"><span data-stu-id="64656-127">Patient</span></span>

<span data-ttu-id="64656-128">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:</span><span class="sxs-lookup"><span data-stu-id="64656-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="64656-129">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="64656-129">Name.Given</span></span>
2. <span data-ttu-id="64656-130">Nome. família</span><span class="sxs-lookup"><span data-stu-id="64656-130">Name.Family</span></span>
3. <span data-ttu-id="64656-131">Sexo</span><span class="sxs-lookup"><span data-stu-id="64656-131">Gender</span></span>
4. <span data-ttu-id="64656-132">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="64656-132">BirthDate</span></span>
5. <span data-ttu-id="64656-133">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="64656-133">MRN (Identifier)</span></span>

<span data-ttu-id="64656-134">Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="64656-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="64656-135">Name. Use</span><span class="sxs-lookup"><span data-stu-id="64656-135">Name.Use</span></span>
2. <span data-ttu-id="64656-136">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="64656-136">Name.Prefix</span></span>
3. <span data-ttu-id="64656-137">[GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)</span><span class="sxs-lookup"><span data-stu-id="64656-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="64656-138">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="64656-139">%</span><span class="sxs-lookup"><span data-stu-id="64656-139">id</span></span>
2. <span data-ttu-id="64656-140">Family = (procura por todos os pacientes cujo nome de família contenha o valor)</span><span class="sxs-lookup"><span data-stu-id="64656-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="64656-141">especificado =\<subcadeia de caracteres></span><span class="sxs-lookup"><span data-stu-id="64656-141">given=\<substring></span></span>
4. <span data-ttu-id="64656-142">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="64656-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="64656-143">Gênero = (valores sendo um dos sexo administrativos)</span><span class="sxs-lookup"><span data-stu-id="64656-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="64656-144">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="64656-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="64656-145">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e \_da contagem que será usado pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="64656-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="64656-146">identificador =\<MRN></span><span class="sxs-lookup"><span data-stu-id="64656-146">identifier=\<mrn></span></span>

<span data-ttu-id="64656-147">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="64656-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="64656-148">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="64656-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="64656-149">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="64656-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="64656-150">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.</span><span class="sxs-lookup"><span data-stu-id="64656-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="64656-151">Nome</span><span class="sxs-lookup"><span data-stu-id="64656-151">Name</span></span>
- <span data-ttu-id="64656-152">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="64656-152">Birthdate</span></span>

<span data-ttu-id="64656-153">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="64656-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="64656-154">Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: dadas = Ruth&Family = preto</span><span class="sxs-lookup"><span data-stu-id="64656-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="64656-155">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"relation": "self", "URL": <fhir-Server>/patient/_search "}]," entry ": [{" fullUrl ": <fhir-Server>/patient/<> de identificação do paciente", "recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "texto": {"status": "gerado", "div", "div": "</span><span class="sxs-lookup"><span data-stu-id="64656-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="64656-156">\n</span><span class="sxs-lookup"><span data-stu-id="64656-156">\n</span></span>        <p><span data-ttu-id="64656-157">Ruth negro</span><span class="sxs-lookup"><span data-stu-id="64656-157">Ruth Black</span></span></p><span data-ttu-id="64656-158">\n</span><span class="sxs-lookup"><span data-stu-id="64656-158">\n</span></span>      </div><span data-ttu-id="64656-159">"}," identificador ": [{" Use ":" usual "," tipo ": {" codificação ": [{" sistema ":"https://hl7.org/fhir/v2/0203"," código ":" Mr "," exibir ":" número do registro médico "," userselected ": false}]," texto ":" número do registro médico "," sistema ":http://hospital.smarthealthit.org" "," valor ":" 1234567 "}]," ativo ": verdadeiro," nome ": [{" usar ":" oficial "," família ":" preto "," fornecido ": [" Ruth "," C ",</span><span class="sxs-lookup"><span data-stu-id="64656-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="64656-160">]}], "telecomunicações": [{"System": "Phone", "value": "800-599-2739", "valor": "800-808-7785", "Use": "móvel", "valor": "", "Use": "celular", "valor" gênero ":" email "," valor ":" ruth.black@example.com "," ",", "gênero": "feminino", "DataDeNascimento": "1951-08-23", "endereço": [{"usar": "Home", "linha": ["26 South RdApt 22"], "cidade": "Sapulpa", "estado": "OK", "CEP": "74066", "país": "EUA"}]}, "localizar": {"Mode": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="64656-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="64656-161">Solicitação: Obtenha o <fhir>/patient/<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="64656-162">Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>", "identificador": [{"usar": "usual", "tipo": {"codificação": [{"sistema": "https://hl7.org/fhir/v2/0203", "código": "Sr",}], "texto": "número do registro médico"}, "valor": "1234567"}], "nome": [{"usar": "oficial", "família": "Adams", "determinado": ["Daniel", "X."</span><span class="sxs-lookup"><span data-stu-id="64656-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="64656-163">]}], "gênero": "macho", "Datadenascimentoe": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="64656-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="64656-164">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-164">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="64656-165">Observações</span><span class="sxs-lookup"><span data-stu-id="64656-165">Observation</span></span>

<span data-ttu-id="64656-166">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil Argonaut de sinais essenciais](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="64656-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="64656-167">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="64656-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="64656-168">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="64656-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="64656-169">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="64656-169">ValueQuantity.Value</span></span>

<span data-ttu-id="64656-170">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="64656-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="64656-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="64656-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="64656-172">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="64656-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="64656-173">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="64656-174">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-174">patient=\<patient id></span></span>
2. <span data-ttu-id="64656-175">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="64656-175">_sort=-date</span></span>
3. <span data-ttu-id="64656-176">Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.</span><span class="sxs-lookup"><span data-stu-id="64656-176">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="64656-177">Consulte este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="64656-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="64656-178">Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<paciente-ID>&categoria = sinais essenciais</span><span class="sxs-lookup"><span data-stu-id="64656-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="64656-179">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "observação", "ID": "<Resource-ID>", "categoria": [{"codificação": [{"sistema": "https://hl7.org/fhir/observation-category", "código": "código vital" Code ": {" Coding ": [{" System ":"http://loinc.org"," código ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valor ": 72,0," unidade ":" {batidas}/min "," sistema ":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="64656-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="64656-180">.</span><span class="sxs-lookup"><span data-stu-id="64656-180">.</span></span>
        <span data-ttu-id="64656-181">.</span><span class="sxs-lookup"><span data-stu-id="64656-181">.</span></span>
      <span data-ttu-id="64656-182">] }</span><span class="sxs-lookup"><span data-stu-id="64656-182">] }</span></span>

* * *

<span data-ttu-id="64656-183">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="64656-184">Condição</span><span class="sxs-lookup"><span data-stu-id="64656-184">Condition</span></span>

<span data-ttu-id="64656-185">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="64656-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="64656-186">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="64656-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="64656-187">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="64656-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="64656-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="64656-188">AssertedDate</span></span>
2. <span data-ttu-id="64656-189">Gravidade</span><span class="sxs-lookup"><span data-stu-id="64656-189">Severity</span></span>

<span data-ttu-id="64656-190">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="64656-191">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-191">patient=\<patient id></span></span>
2. <span data-ttu-id="64656-192">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="64656-192">_count=\<max results></span></span>

<span data-ttu-id="64656-193">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="64656-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="64656-194">Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="64656-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="64656-195">Resposta: {"resourceType": "Bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "total": 2, "entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "código": {"codificação": [{"sistema": "http://snomed.info/sct", "código": "185903001", "exibição": "precisa de imunização influenza",}]}, "severidade": {"codificação": [{"sistema":http://snomed.info/sct"", "código": "24484000", "exibir": "severado}]}," assertedDate ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="64656-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="64656-196">.</span><span class="sxs-lookup"><span data-stu-id="64656-196">.</span></span>
        <span data-ttu-id="64656-197">.</span><span class="sxs-lookup"><span data-stu-id="64656-197">.</span></span>
      <span data-ttu-id="64656-198">] }</span><span class="sxs-lookup"><span data-stu-id="64656-198">] }</span></span>

* * *
<span data-ttu-id="64656-199">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-199">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="64656-200">Encontrá</span><span class="sxs-lookup"><span data-stu-id="64656-200">Encounter</span></span>

<span data-ttu-id="64656-201">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="64656-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="64656-202">Situação</span><span class="sxs-lookup"><span data-stu-id="64656-202">Status</span></span>
2. <span data-ttu-id="64656-203">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="64656-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="64656-204">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:</span><span class="sxs-lookup"><span data-stu-id="64656-204">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="64656-205">Período. início</span><span class="sxs-lookup"><span data-stu-id="64656-205">Period.Start</span></span>
2. <span data-ttu-id="64656-206">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="64656-206">Location[0].Location.Display</span></span>

<span data-ttu-id="64656-207">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="64656-208">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-208">patient=\<patient id></span></span>
2. <span data-ttu-id="64656-209">_sort: desc =\<Field ex.</span><span class="sxs-lookup"><span data-stu-id="64656-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="64656-210">Data></span><span class="sxs-lookup"><span data-stu-id="64656-210">date></span></span>
3. <span data-ttu-id="64656-211">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="64656-211">_count=\<max results></span></span>

<span data-ttu-id="64656-212">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="64656-212">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="64656-213">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="64656-213">Each encounter references a location resource.</span></span> <span data-ttu-id="64656-214">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="64656-214">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="64656-215">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-215">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="64656-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="64656-216">AllergyIntolerance</span></span>

<span data-ttu-id="64656-217">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="64656-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="64656-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="64656-218">Code.Text</span></span>
2. <span data-ttu-id="64656-219">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="64656-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="64656-220">ClinicalStatus/VerificationStatus (Lemos)</span><span class="sxs-lookup"><span data-stu-id="64656-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="64656-221">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:</span><span class="sxs-lookup"><span data-stu-id="64656-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="64656-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="64656-222">AssertedDate</span></span>
2. <span data-ttu-id="64656-223">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="64656-223">Note.Text</span></span>
3. <span data-ttu-id="64656-224">Reação</span><span class="sxs-lookup"><span data-stu-id="64656-224">Reaction</span></span>
    1. <span data-ttu-id="64656-225">Substância (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="64656-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="64656-226">Manifestação (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="64656-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="64656-227">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="64656-228">Paciente = \<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-228">Patient =  \<patient id></span></span>

<span data-ttu-id="64656-229">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="64656-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="64656-230">Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="64656-231">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1 "," entry ": [{" Resource ": {" resourceType ":" AllergyIntolerance "," ID ":" verificationStatus-ID> "," clinicalStatus ":" ativo "," ":" confirmado "," código ": {" codificação ", <" ":" confirmadohttp://rxnav.nlm.nih.gov/REST/Ndfrt"," código ": {" codificação ": N0000175503", "exibir": "sulfonamide Antibacterial",}], "texto": "sulfonamide Antibacterial"}, "assertedDate": "2018-01-01T00:00:00-07:00", "reação": [{"manifestação": [{"Coding": [{"http://snomed.info/sctSystem": "", "código": "271807003", "display": "Skin rash",}], "texto": "Skin rash"}],}]</span><span class="sxs-lookup"><span data-stu-id="64656-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="64656-232">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-232">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="64656-233">Solicitação de medicação</span><span class="sxs-lookup"><span data-stu-id="64656-233">Medication Request</span></span>

<span data-ttu-id="64656-234">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="64656-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="64656-235">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="64656-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="64656-236">Medicação. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="64656-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="64656-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="64656-237">AuthoredOn</span></span>
4. <span data-ttu-id="64656-238">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="64656-238">Requester.Agent.Display</span></span>

<span data-ttu-id="64656-239">Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="64656-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="64656-240">DosageInstruction[..]. Textos</span><span class="sxs-lookup"><span data-stu-id="64656-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="64656-241">Textos</span><span class="sxs-lookup"><span data-stu-id="64656-241">Text</span></span>

<span data-ttu-id="64656-242">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="64656-243">paciente =\<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-243">patient=\<patient id></span></span>
2. <span data-ttu-id="64656-244">_count =\<máximo de resultados></span><span class="sxs-lookup"><span data-stu-id="64656-244">_count=\<max results></span></span>

<span data-ttu-id="64656-245">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="64656-246">Análise</span><span class="sxs-lookup"><span data-stu-id="64656-246">Coverage</span></span>

<span data-ttu-id="64656-247">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="64656-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="64656-248">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="64656-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="64656-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="64656-249">GroupDisplay</span></span>
    2. <span data-ttu-id="64656-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="64656-250">PlanDisplay</span></span>
2. <span data-ttu-id="64656-251">Período</span><span class="sxs-lookup"><span data-stu-id="64656-251">Period</span></span>
3. <span data-ttu-id="64656-252">Subscriberid</span><span class="sxs-lookup"><span data-stu-id="64656-252">SubscriberId</span></span>

<span data-ttu-id="64656-253">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64656-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="64656-254">Paciente = \<identificação do paciente></span><span class="sxs-lookup"><span data-stu-id="64656-254">Patient = \<patient id></span></span>

<span data-ttu-id="64656-255">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="64656-255">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
