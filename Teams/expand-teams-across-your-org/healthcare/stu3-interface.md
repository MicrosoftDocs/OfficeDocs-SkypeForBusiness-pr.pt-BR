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
ms.openlocfilehash: 177d8d9bb1a05e7fc871b8c11771708099347914
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367641"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="c1180-103">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="c1180-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1180-104">**A partir de 30 de outubro de 2020, o aplicativo pacientes será preterido, e os usuários não poderão mais instalá-lo na App Store da equipe. Recomendamos que você comece a usar o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Microsoft Teams hoje mesmo.**</span><span class="sxs-lookup"><span data-stu-id="c1180-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="c1180-105">Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe.</span><span class="sxs-lookup"><span data-stu-id="c1180-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="c1180-106">Quando o aplicativo pacientes é desativado, todos os dados associados a ele serão mantidos nesse grupo, mas não poderão mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c1180-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="c1180-107">Os usuários atuais podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="c1180-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="c1180-108">O [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal.</span><span class="sxs-lookup"><span data-stu-id="c1180-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="c1180-109">Com listas, o cuidado com equipes pode criar listas de pacientes usando o modelo de pacientes incorporado, do zero ou importando dados para o Excel.</span><span class="sxs-lookup"><span data-stu-id="c1180-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="c1180-110">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="c1180-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="c1180-111">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="c1180-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="c1180-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="c1180-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="c1180-113">Aguarde</span><span class="sxs-lookup"><span data-stu-id="c1180-113">Patient</span></span>](#patient)
- [<span data-ttu-id="c1180-114">Observações</span><span class="sxs-lookup"><span data-stu-id="c1180-114">Observation</span></span>](#observation)
- [<span data-ttu-id="c1180-115">Condição</span><span class="sxs-lookup"><span data-stu-id="c1180-115">Condition</span></span>](#condition)
- [<span data-ttu-id="c1180-116">Encontrá</span><span class="sxs-lookup"><span data-stu-id="c1180-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="c1180-117">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="c1180-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="c1180-118">Análise</span><span class="sxs-lookup"><span data-stu-id="c1180-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="c1180-119">[Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="c1180-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="c1180-120">Local (as informações necessárias deste recurso podem ser incluídas em encontrar)</span><span class="sxs-lookup"><span data-stu-id="c1180-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="c1180-121">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1180-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="c1180-122">As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="c1180-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="c1180-123">O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="c1180-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="c1180-124">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="c1180-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="c1180-125">Declaração de recursos</span><span class="sxs-lookup"><span data-stu-id="c1180-125">Capability Statement</span></span>

<span data-ttu-id="c1180-126">Estes são os campos mínimos obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="c1180-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="c1180-127">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="c1180-127">REST</span></span>
   1. <span data-ttu-id="c1180-128">Modo</span><span class="sxs-lookup"><span data-stu-id="c1180-128">Mode</span></span>
   2. <span data-ttu-id="c1180-129">Haja</span><span class="sxs-lookup"><span data-stu-id="c1180-129">Interaction</span></span>
   3. <span data-ttu-id="c1180-130">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="c1180-130">Resource: Type</span></span>
   4. <span data-ttu-id="c1180-131">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="c1180-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="c1180-132">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)</span><span class="sxs-lookup"><span data-stu-id="c1180-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="c1180-133">Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="c1180-134">Aguarde</span><span class="sxs-lookup"><span data-stu-id="c1180-134">Patient</span></span>

<span data-ttu-id="c1180-135">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:</span><span class="sxs-lookup"><span data-stu-id="c1180-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="c1180-136">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="c1180-136">Name.Given</span></span>
2. <span data-ttu-id="c1180-137">Nome. família</span><span class="sxs-lookup"><span data-stu-id="c1180-137">Name.Family</span></span>
3. <span data-ttu-id="c1180-138">Sexo</span><span class="sxs-lookup"><span data-stu-id="c1180-138">Gender</span></span>
4. <span data-ttu-id="c1180-139">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="c1180-139">BirthDate</span></span>
5. <span data-ttu-id="c1180-140">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="c1180-140">MRN (Identifier)</span></span>

<span data-ttu-id="c1180-141">Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c1180-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1180-142">Name. Use</span><span class="sxs-lookup"><span data-stu-id="c1180-142">Name.Use</span></span>
2. <span data-ttu-id="c1180-143">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="c1180-143">Name.Prefix</span></span>
3. <span data-ttu-id="c1180-144">[GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)</span><span class="sxs-lookup"><span data-stu-id="c1180-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="c1180-145">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="c1180-146">%</span><span class="sxs-lookup"><span data-stu-id="c1180-146">id</span></span>
2. <span data-ttu-id="c1180-147">Family = (procura por todos os pacientes cujo nome de família contenha o valor)</span><span class="sxs-lookup"><span data-stu-id="c1180-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="c1180-148">especificado =\<substring></span><span class="sxs-lookup"><span data-stu-id="c1180-148">given=\<substring></span></span>
4. <span data-ttu-id="c1180-149">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="c1180-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="c1180-150">Gênero = (valores sendo um dos sexo administrativos)</span><span class="sxs-lookup"><span data-stu-id="c1180-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="c1180-151">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="c1180-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="c1180-152">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e da \_ contagem que será usado pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="c1180-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="c1180-153">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="c1180-153">identifier=\<mrn></span></span>

<span data-ttu-id="c1180-154">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c1180-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="c1180-155">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="c1180-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="c1180-156">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="c1180-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="c1180-157">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.</span><span class="sxs-lookup"><span data-stu-id="c1180-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="c1180-158">Nome</span><span class="sxs-lookup"><span data-stu-id="c1180-158">Name</span></span>
- <span data-ttu-id="c1180-159">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="c1180-159">Birthdate</span></span>

<span data-ttu-id="c1180-160">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="c1180-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="c1180-161">Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: dadas = Ruth&Family = preto</span><span class="sxs-lookup"><span data-stu-id="c1180-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="c1180-162">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"relation": "self", "URL": <fhir-Server>/patient/_search "}]," entry ": [{" fullUrl ": <fhir-Server>/patient/<> de identificação do paciente", "recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "texto": {"status": "gerado", "div", "div": "</span><span class="sxs-lookup"><span data-stu-id="c1180-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="c1180-163">\n</span><span class="sxs-lookup"><span data-stu-id="c1180-163">\n</span></span>        <p><span data-ttu-id="c1180-164">Ruth negro</span><span class="sxs-lookup"><span data-stu-id="c1180-164">Ruth Black</span></span></p><span data-ttu-id="c1180-165">\n</span><span class="sxs-lookup"><span data-stu-id="c1180-165">\n</span></span>      </div><span data-ttu-id="c1180-166">"}," identificador ": [{" Use ":" usual "," tipo ": {" codificação ": [{" sistema ":" https://hl7.org/fhir/v2/0203 "," código ":" Mr "," exibir ":" número do registro médico "," Userselected ": false}]," texto ":" número do registro médico "," sistema ":" http://hospital.smarthealthit.org "," valor ":" 1234567 "}]," ativo ": verdadeiro," nome ": [{" usar ":" oficial "," família ":" preto "," fornecido ": [" Ruth "," C ",</span><span class="sxs-lookup"><span data-stu-id="c1180-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="c1180-167">]}], "telecomunicações": [{"System": "Phone", "value": "800-599-2739", "valor": "800-808-7785", "Use": "móvel", "valor": "", "Use": "celular", "valor" gênero ":" email "," valor ":" ruth.black@example.com "," ",", "gênero": "feminino", "DataDeNascimento": "1951-08-23", "endereço": [{"usar": "Home", "linha": ["26 South RdApt 22"], "cidade": "Sapulpa", "estado": "OK", "CEP": "74066", "país": "EUA"}]}, "localizar": {"Mode": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="c1180-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="c1180-168">Solicitação: Obtenha o <fhir>/patient/<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="c1180-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="c1180-169">Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>", "identificador": [{"usar": "usual", "tipo": {"codificação": [{"sistema": " https://hl7.org/fhir/v2/0203 ", "código": "Sr",}], "texto": "número do registro médico"}, "valor": "1234567"}], "nome": [{"usar": "oficial", "família": "Adams", "determinado": ["Daniel", "X."</span><span class="sxs-lookup"><span data-stu-id="c1180-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="c1180-170">]}], "gênero": "macho", "Datadenascimentoe": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="c1180-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="c1180-171">Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="c1180-172">Observações</span><span class="sxs-lookup"><span data-stu-id="c1180-172">Observation</span></span>

<span data-ttu-id="c1180-173">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil Argonaut de sinais essenciais](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="c1180-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="c1180-174">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="c1180-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="c1180-175">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="c1180-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="c1180-176">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="c1180-176">ValueQuantity.Value</span></span>

<span data-ttu-id="c1180-177">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c1180-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1180-178">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="c1180-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="c1180-179">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="c1180-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="c1180-180">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1180-181">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c1180-181">patient=\<patient id></span></span>
2. <span data-ttu-id="c1180-182">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="c1180-182">_sort=-date</span></span>
3. <span data-ttu-id="c1180-183">Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.</span><span class="sxs-lookup"><span data-stu-id="c1180-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="c1180-184">Consulte este exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="c1180-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="c1180-185">Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<paciente-ID>&categoria = sinais essenciais</span><span class="sxs-lookup"><span data-stu-id="c1180-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="c1180-186">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "observação", "ID": "<Resource-ID>", "categoria": [{"codificação": [{"sistema": " https://hl7.org/fhir/observation-category ", "código": "código vital" Code ": {" Coding ": [{" System ":" http://loinc.org "," código ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valor ": 72,0," unidade ":" {batidas}/min "," sistema ":" http://unitsofmeasure.org ",}}},.</span><span class="sxs-lookup"><span data-stu-id="c1180-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="c1180-187">.</span><span class="sxs-lookup"><span data-stu-id="c1180-187">.</span></span>
        <span data-ttu-id="c1180-188">.</span><span class="sxs-lookup"><span data-stu-id="c1180-188">.</span></span>
      <span data-ttu-id="c1180-189">] }</span><span class="sxs-lookup"><span data-stu-id="c1180-189">] }</span></span>

* * *

<span data-ttu-id="c1180-190">Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="c1180-191">Condição</span><span class="sxs-lookup"><span data-stu-id="c1180-191">Condition</span></span>

<span data-ttu-id="c1180-192">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="c1180-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="c1180-193">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="c1180-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="c1180-194">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c1180-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1180-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="c1180-195">AssertedDate</span></span>
2. <span data-ttu-id="c1180-196">Gravidade</span><span class="sxs-lookup"><span data-stu-id="c1180-196">Severity</span></span>

<span data-ttu-id="c1180-197">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1180-198">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c1180-198">patient=\<patient id></span></span>
2. <span data-ttu-id="c1180-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c1180-199">_count=\<max results></span></span>

<span data-ttu-id="c1180-200">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="c1180-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c1180-201">Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="c1180-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="c1180-202">Resposta: {"resourceType": "Bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "total": 2, "entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "código": {"codificação": [{"sistema": " http://snomed.info/sct ", "código": "185903001", "exibição": "precisa de imunização influenza",}]}, "severidade": {"codificação": [{"sistema": " http://snomed.info/sct ", "código": "24484000", "exibir": "severado}]}," assertedDate ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="c1180-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="c1180-203">.</span><span class="sxs-lookup"><span data-stu-id="c1180-203">.</span></span>
        <span data-ttu-id="c1180-204">.</span><span class="sxs-lookup"><span data-stu-id="c1180-204">.</span></span>
      <span data-ttu-id="c1180-205">] }</span><span class="sxs-lookup"><span data-stu-id="c1180-205">] }</span></span>

* * *
<span data-ttu-id="c1180-206">Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="c1180-207">Encontrá</span><span class="sxs-lookup"><span data-stu-id="c1180-207">Encounter</span></span>

<span data-ttu-id="c1180-208">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .</span><span class="sxs-lookup"><span data-stu-id="c1180-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="c1180-209">Situação</span><span class="sxs-lookup"><span data-stu-id="c1180-209">Status</span></span>
2. <span data-ttu-id="c1180-210">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="c1180-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="c1180-211">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:</span><span class="sxs-lookup"><span data-stu-id="c1180-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="c1180-212">Período. início</span><span class="sxs-lookup"><span data-stu-id="c1180-212">Period.Start</span></span>
2. <span data-ttu-id="c1180-213">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="c1180-213">Location[0].Location.Display</span></span>

<span data-ttu-id="c1180-214">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1180-215">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c1180-215">patient=\<patient id></span></span>
2. <span data-ttu-id="c1180-216">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="c1180-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="c1180-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c1180-217">_count=\<max results></span></span>

<span data-ttu-id="c1180-218">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="c1180-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="c1180-219">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="c1180-219">Each encounter references a location resource.</span></span> <span data-ttu-id="c1180-220">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="c1180-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="c1180-221">Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="c1180-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="c1180-222">AllergyIntolerance</span></span>

<span data-ttu-id="c1180-223">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="c1180-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="c1180-224">Code. Text</span><span class="sxs-lookup"><span data-stu-id="c1180-224">Code.Text</span></span>
2. <span data-ttu-id="c1180-225">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="c1180-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="c1180-226">ClinicalStatus/VerificationStatus (Lemos)</span><span class="sxs-lookup"><span data-stu-id="c1180-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="c1180-227">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:</span><span class="sxs-lookup"><span data-stu-id="c1180-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="c1180-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="c1180-228">AssertedDate</span></span>
2. <span data-ttu-id="c1180-229">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="c1180-229">Note.Text</span></span>
3. <span data-ttu-id="c1180-230">Reação</span><span class="sxs-lookup"><span data-stu-id="c1180-230">Reaction</span></span>
    1. <span data-ttu-id="c1180-231">Substância (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="c1180-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="c1180-232">Manifestação (um elemento de codificação)</span><span class="sxs-lookup"><span data-stu-id="c1180-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="c1180-233">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1180-234">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="c1180-234">Patient =  \<patient id></span></span>

<span data-ttu-id="c1180-235">Consulte o seguinte exemplo da chamada:</span><span class="sxs-lookup"><span data-stu-id="c1180-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="c1180-236">Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="c1180-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="c1180-237">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1 "," entry ": [{" Resource ": {" resourceType ":" AllergyIntolerance "," ID ":" verificationStatus-ID> "," clinicalStatus ":" ativo "," ":" confirmado "," código ": {" codificação ", <" ":" confirmado "," código ": {" codificação ": http://rxnav.nlm.nih.gov/REST/Ndfrt N0000175503", "exibir": "sulfonamide Antibacterial",}], "texto": "sulfonamide Antibacterial"}, "assertedDate": "2018-01-01T00:00:00-07:00", "reação": [{"manifestação": [{"Coding": [{"System": " http://snomed.info/sct ", "código": "271807003", "display": "Skin rash",}], "texto": "Skin rash"}],}]</span><span class="sxs-lookup"><span data-stu-id="c1180-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="c1180-238">Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="c1180-239">Solicitação de medicação</span><span class="sxs-lookup"><span data-stu-id="c1180-239">Medication Request</span></span>

<span data-ttu-id="c1180-240">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="c1180-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="c1180-241">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="c1180-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="c1180-242">Medicação. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="c1180-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="c1180-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="c1180-243">AuthoredOn</span></span>
4. <span data-ttu-id="c1180-244">Solicitante. Agent. display</span><span class="sxs-lookup"><span data-stu-id="c1180-244">Requester.Agent.Display</span></span>

<span data-ttu-id="c1180-245">Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c1180-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1180-246">DosageInstruction[..]. Textos</span><span class="sxs-lookup"><span data-stu-id="c1180-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="c1180-247">Textos</span><span class="sxs-lookup"><span data-stu-id="c1180-247">Text</span></span>

<span data-ttu-id="c1180-248">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1180-249">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c1180-249">patient=\<patient id></span></span>
2. <span data-ttu-id="c1180-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c1180-250">_count=\<max results></span></span>

<span data-ttu-id="c1180-251">Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="c1180-252">Análise</span><span class="sxs-lookup"><span data-stu-id="c1180-252">Coverage</span></span>

<span data-ttu-id="c1180-253">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="c1180-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="c1180-254">Agrupamento, pelo menos um elemento com</span><span class="sxs-lookup"><span data-stu-id="c1180-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="c1180-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="c1180-255">GroupDisplay</span></span>
    2. <span data-ttu-id="c1180-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="c1180-256">PlanDisplay</span></span>
2. <span data-ttu-id="c1180-257">Período</span><span class="sxs-lookup"><span data-stu-id="c1180-257">Period</span></span>
3. <span data-ttu-id="c1180-258">Subscriberid</span><span class="sxs-lookup"><span data-stu-id="c1180-258">SubscriberId</span></span>

<span data-ttu-id="c1180-259">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c1180-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1180-260">Paciente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="c1180-260">Patient = \<patient id></span></span>

<span data-ttu-id="c1180-261">Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c1180-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
