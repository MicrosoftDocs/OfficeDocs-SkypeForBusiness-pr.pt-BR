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
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361451"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="6778b-103">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="6778b-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6778b-104">**A partir de 15 de outubro de 2020, o aplicativo pacientes será preterido e os usuários não poderão mais instalá-lo na App Store da equipe. Recomendamos que você comece a usar o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Microsoft Teams hoje mesmo.**</span><span class="sxs-lookup"><span data-stu-id="6778b-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="6778b-105">Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe.</span><span class="sxs-lookup"><span data-stu-id="6778b-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="6778b-106">Quando o aplicativo pacientes é desativado, todos os dados associados a ele serão mantidos nesse grupo, mas não poderão mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="6778b-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="6778b-107">Os usuários atuais podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="6778b-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="6778b-108">O [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal.</span><span class="sxs-lookup"><span data-stu-id="6778b-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="6778b-109">Com listas, o cuidado com equipes pode criar listas de pacientes usando o modelo de pacientes incorporado, do zero ou importando dados para o Excel.</span><span class="sxs-lookup"><span data-stu-id="6778b-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="6778b-110">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="6778b-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="6778b-111">A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar.</span><span class="sxs-lookup"><span data-stu-id="6778b-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="6778b-112">O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="6778b-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="6778b-113">Aguarde</span><span class="sxs-lookup"><span data-stu-id="6778b-113">Patient</span></span>](#patient)
- [<span data-ttu-id="6778b-114">Observações</span><span class="sxs-lookup"><span data-stu-id="6778b-114">Observation</span></span>](#observation)
- [<span data-ttu-id="6778b-115">Condição</span><span class="sxs-lookup"><span data-stu-id="6778b-115">Condition</span></span>](#condition)
- [<span data-ttu-id="6778b-116">Encontrá</span><span class="sxs-lookup"><span data-stu-id="6778b-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="6778b-117">Allergy intolerância</span><span class="sxs-lookup"><span data-stu-id="6778b-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="6778b-118">Análise</span><span class="sxs-lookup"><span data-stu-id="6778b-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="6778b-119">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="6778b-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="6778b-120">Local</span><span class="sxs-lookup"><span data-stu-id="6778b-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="6778b-121">O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado.</span><span class="sxs-lookup"><span data-stu-id="6778b-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="6778b-122">No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6778b-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="6778b-123">Consultas do aplicativo Microsoft Teams pacientes para mais de um recurso poste um pacote (lote) de solicitações para a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="6778b-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="6778b-124">O servidor processa cada solicitação e retorna um pacote dos recursos correspondentes a cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="6778b-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="6778b-125">Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="6778b-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="6778b-126">Todos os recursos de FHIR a seguir devem ser acessíveis pela referência a recursos diretos.</span><span class="sxs-lookup"><span data-stu-id="6778b-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="6778b-127">Conjunto de campos obrigatórios mínimos de conformidade</span><span class="sxs-lookup"><span data-stu-id="6778b-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="6778b-128">O servidor FHIR deve implementar a instrução de conformidade para que possamos ter um resumo factual de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="6778b-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="6778b-129">Esperamos os parâmetros a seguir em um servidor FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="6778b-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="6778b-130">DEIXAR</span><span class="sxs-lookup"><span data-stu-id="6778b-130">REST</span></span>
   1. <span data-ttu-id="6778b-131">Modo</span><span class="sxs-lookup"><span data-stu-id="6778b-131">Mode</span></span>
   2. <span data-ttu-id="6778b-132">Haja</span><span class="sxs-lookup"><span data-stu-id="6778b-132">Interaction</span></span>
   3. <span data-ttu-id="6778b-133">Recurso: tipo</span><span class="sxs-lookup"><span data-stu-id="6778b-133">Resource: Type</span></span>
   4. <span data-ttu-id="6778b-134">Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="6778b-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="6778b-135">FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotá-lo como suporte a várias versões.)</span><span class="sxs-lookup"><span data-stu-id="6778b-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="6778b-136">Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="6778b-137">Aguarde</span><span class="sxs-lookup"><span data-stu-id="6778b-137">Patient</span></span>

<span data-ttu-id="6778b-138">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de [perfil do paciente do Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="6778b-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="6778b-139">Nome. família</span><span class="sxs-lookup"><span data-stu-id="6778b-139">Name.Family</span></span>
2. <span data-ttu-id="6778b-140">Nome. fornecido</span><span class="sxs-lookup"><span data-stu-id="6778b-140">Name.Given</span></span>
3. <span data-ttu-id="6778b-141">Sexo</span><span class="sxs-lookup"><span data-stu-id="6778b-141">Gender</span></span>
4. <span data-ttu-id="6778b-142">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="6778b-142">BirthDate</span></span>
5. <span data-ttu-id="6778b-143">MRN (identificador)</span><span class="sxs-lookup"><span data-stu-id="6778b-143">MRN (Identifier)</span></span>

<span data-ttu-id="6778b-144">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="6778b-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="6778b-145">Name. Use</span><span class="sxs-lookup"><span data-stu-id="6778b-145">Name.Use</span></span>
2. <span data-ttu-id="6778b-146">Name. Prefix</span><span class="sxs-lookup"><span data-stu-id="6778b-146">Name.Prefix</span></span>
3. <span data-ttu-id="6778b-147">Cuidado: (essa referência ao recurso do paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)</span><span class="sxs-lookup"><span data-stu-id="6778b-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="6778b-148">Solicitação: Obtenha o <fhir>/patient/<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="6778b-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="6778b-149">Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>",.</span><span class="sxs-lookup"><span data-stu-id="6778b-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="6778b-150">.</span><span class="sxs-lookup"><span data-stu-id="6778b-150">.</span></span>
      <span data-ttu-id="6778b-151">.</span><span class="sxs-lookup"><span data-stu-id="6778b-151">.</span></span>
      <span data-ttu-id="6778b-152">"nome": [{"Use": "Official", "prefix": ["Sr"], "família": ["Chau"], "atribuído": ["Hugh"]}], "identificador": [{"usar": "oficial", "digite": {"codificação": [{"System": " https://hl7.org/fhir/v2/0203 ", "código": "Mr"}]}, "valor": "1234567", "cuidadosprovider": "macho", "datadenascimentoe": "1957-06-05", "cuidadosprovider": [{"display": "Jane Doe"}],}</span><span class="sxs-lookup"><span data-stu-id="6778b-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="6778b-153">Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="6778b-154">%</span><span class="sxs-lookup"><span data-stu-id="6778b-154">id</span></span>
2. <span data-ttu-id="6778b-155">Family: Contains = (procura por todos os pacientes cujo nome de família contenha o valor.)</span><span class="sxs-lookup"><span data-stu-id="6778b-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="6778b-156">especificado =\<substring></span><span class="sxs-lookup"><span data-stu-id="6778b-156">given=\<substring></span></span>
4. <span data-ttu-id="6778b-157">nome =\<substring></span><span class="sxs-lookup"><span data-stu-id="6778b-157">name=\<substring></span></span>
5. <span data-ttu-id="6778b-158">DataDeNascimento = (correspondência exata)</span><span class="sxs-lookup"><span data-stu-id="6778b-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="6778b-159">\_contagem (número máximo de resultados que devem ser retornados)</span><span class="sxs-lookup"><span data-stu-id="6778b-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="6778b-160">A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a \_ contagem será usada pelo PatientsApp para limitar o número de registros retornados.</span><span class="sxs-lookup"><span data-stu-id="6778b-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="6778b-161">identificador =\<mrn></span><span class="sxs-lookup"><span data-stu-id="6778b-161">identifier=\<mrn></span></span>

<span data-ttu-id="6778b-162">O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6778b-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="6778b-163">ID: essa é a ID do recurso que cada recurso no FHIR tem.</span><span class="sxs-lookup"><span data-stu-id="6778b-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="6778b-164">MRN: esse é o identificador real do paciente que a equipe clínica saberia.</span><span class="sxs-lookup"><span data-stu-id="6778b-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="6778b-165">Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR</span><span class="sxs-lookup"><span data-stu-id="6778b-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="6778b-166">Nome</span><span class="sxs-lookup"><span data-stu-id="6778b-166">Name</span></span>
- <span data-ttu-id="6778b-167">DataDeNascimento</span><span class="sxs-lookup"><span data-stu-id="6778b-167">Birthdate</span></span>

<span data-ttu-id="6778b-168">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="6778b-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="6778b-169">Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: especificado = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="6778b-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="6778b-170">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>",.</span><span class="sxs-lookup"><span data-stu-id="6778b-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="6778b-171">.</span><span class="sxs-lookup"><span data-stu-id="6778b-171">.</span></span>
      <span data-ttu-id="6778b-172">.</span><span class="sxs-lookup"><span data-stu-id="6778b-172">.</span></span>
      <span data-ttu-id="6778b-173">"entrada": [{"recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "nome": [{"texto": "Hugh Chau", "família": ["Chau"], "determinado": ["Hugh"]}], "gênero": "macho", "Datadenascimentoe": "1957-06-05"}, "localizar": {"Mode": "matching"}}]}</span><span class="sxs-lookup"><span data-stu-id="6778b-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="6778b-174">Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="6778b-175">Observações</span><span class="sxs-lookup"><span data-stu-id="6778b-175">Observation</span></span>

<span data-ttu-id="6778b-176">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil de sinais Argonaut vital:</span><span class="sxs-lookup"><span data-stu-id="6778b-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="6778b-177">Efetivo (data e hora ou ponto)</span><span class="sxs-lookup"><span data-stu-id="6778b-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="6778b-178">Code. Coding. Code</span><span class="sxs-lookup"><span data-stu-id="6778b-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="6778b-179">Valor de ValueQuantity. valor</span><span class="sxs-lookup"><span data-stu-id="6778b-179">ValueQuantity.Value</span></span>

<span data-ttu-id="6778b-180">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="6778b-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="6778b-181">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="6778b-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="6778b-182">ValueQuantity. unidade</span><span class="sxs-lookup"><span data-stu-id="6778b-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="6778b-183">Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.</span><span class="sxs-lookup"><span data-stu-id="6778b-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="6778b-184">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6778b-185">paciente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="6778b-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="6778b-186">classificar: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="6778b-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="6778b-187">O objetivo é poder recuperar os mais recentes sinais essenciais para um paciente, [VitalSigns. DSTU. Saz] (observação?).</span><span class="sxs-lookup"><span data-stu-id="6778b-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="6778b-188">Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<o ID do paciente>&_sort:d ESC = data&Category = sinais essenciais</span><span class="sxs-lookup"><span data-stu-id="6778b-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="6778b-189">Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "digite": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "reobservação", "ID": "<Resource-ID>", "categoria": {"codificação": "código": "informativo-sinais"}],}, "código": {"codificação": [{"System": " http://loinc.org ", "código": "39156-5", "display": "BMI"}],}, "effectiveDateTime": "2009-12-01", "valueQuantity": {"valor": 34,4, "unidade": "kg/m2", "sistema": " http://unitsofmeasure.org ", "código": "kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="6778b-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="6778b-190">.</span><span class="sxs-lookup"><span data-stu-id="6778b-190">.</span></span>
        <span data-ttu-id="6778b-191">.</span><span class="sxs-lookup"><span data-stu-id="6778b-191">.</span></span>
      <span data-ttu-id="6778b-192">] }</span><span class="sxs-lookup"><span data-stu-id="6778b-192">] }</span></span>

* * *

<span data-ttu-id="6778b-193">Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="6778b-194">Condição</span><span class="sxs-lookup"><span data-stu-id="6778b-194">Condition</span></span>

<span data-ttu-id="6778b-195">Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="6778b-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="6778b-196">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="6778b-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="6778b-197">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="6778b-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="6778b-198">Data de gravação</span><span class="sxs-lookup"><span data-stu-id="6778b-198">Date Recorded</span></span>
2. <span data-ttu-id="6778b-199">Gravidade</span><span class="sxs-lookup"><span data-stu-id="6778b-199">Severity</span></span>

<span data-ttu-id="6778b-200">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6778b-201">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6778b-201">patient=\<patient id></span></span>
2. <span data-ttu-id="6778b-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6778b-202">_count=\<max results></span></span>

<span data-ttu-id="6778b-203">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="6778b-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="6778b-204">Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="6778b-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="6778b-205">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": "ID": "<Resource-ID": {"resourceType": "Condition", "ID": "Resource-ID>", "código": {"codificação": [{"sistema": " http://snomed.info/sct ", "código": "386033004", "vídeo": "2018-09-17", ","}]}, "dateRecorded": "", "Severity": {"Coding": [{"System": " http://snomed.info/sct ", "código": "24484000", "display": "severado}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="6778b-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="6778b-206">Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="6778b-207">Encontrá</span><span class="sxs-lookup"><span data-stu-id="6778b-207">Encounter</span></span>

<span data-ttu-id="6778b-208">Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos perfil do núcleo dos EUA "deve ter":</span><span class="sxs-lookup"><span data-stu-id="6778b-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="6778b-209">Situação</span><span class="sxs-lookup"><span data-stu-id="6778b-209">Status</span></span>
2. <span data-ttu-id="6778b-210">Digite [0]. Codificação [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="6778b-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="6778b-211">Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil principal</span><span class="sxs-lookup"><span data-stu-id="6778b-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="6778b-212">Período. início</span><span class="sxs-lookup"><span data-stu-id="6778b-212">Period.Start</span></span>
2. <span data-ttu-id="6778b-213">Local [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="6778b-213">Location[0].Location.Display</span></span>

<span data-ttu-id="6778b-214">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6778b-215">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6778b-215">patient=\<patient id></span></span>
2. <span data-ttu-id="6778b-216">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="6778b-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="6778b-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6778b-217">_count=\<max results></span></span>

<span data-ttu-id="6778b-218">O objetivo é poder recuperar o último local conhecido do paciente.</span><span class="sxs-lookup"><span data-stu-id="6778b-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="6778b-219">Cada encontro faz referência a um recurso de localização.</span><span class="sxs-lookup"><span data-stu-id="6778b-219">Each encounter references a location resource.</span></span> <span data-ttu-id="6778b-220">A referência também incluirá o campo de exibição do local.</span><span class="sxs-lookup"><span data-stu-id="6778b-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="6778b-221">Consulte o exemplo a seguir desta chamada.</span><span class="sxs-lookup"><span data-stu-id="6778b-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="6778b-222">Solicitação: Obtenha o <fhir-Server>/Encounter? paciente =<o ID do paciente>&_sort:d ESC = data&_count = 1</span><span class="sxs-lookup"><span data-stu-id="6778b-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="6778b-223">Resposta: {"resourceType": "Bundle", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "encontrar", "ID": "<Resource-ID>", "identificador": [{"usar": "oficial", "valor": " <id> "}], "status": "chegado", "tipo": [{"codificação": [{"exibir": "compromisso"}],}], "paciente": {"referência": "paciente/<paciente-id>"}, "período": {"Iniciar": "09/17/2018 1:00:00 PM"}, "local": [{"Location": {"display": "Clinic-ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="6778b-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="6778b-224">Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="6778b-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="6778b-225">AllergyIntolerance</span></span>

<span data-ttu-id="6778b-226">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="6778b-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="6778b-227">Code. Text</span><span class="sxs-lookup"><span data-stu-id="6778b-227">Code.Text</span></span>
2. <span data-ttu-id="6778b-228">Code. Coding [0]. Mostrar</span><span class="sxs-lookup"><span data-stu-id="6778b-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="6778b-229">Situação</span><span class="sxs-lookup"><span data-stu-id="6778b-229">Status</span></span>

<span data-ttu-id="6778b-230">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="6778b-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="6778b-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="6778b-231">RecordedDate</span></span>
2. <span data-ttu-id="6778b-232">Observação. texto</span><span class="sxs-lookup"><span data-stu-id="6778b-232">Note.Text</span></span>
3. <span data-ttu-id="6778b-233">Reação [..]. Substância. Text</span><span class="sxs-lookup"><span data-stu-id="6778b-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="6778b-234">Reação [..]. Manifestação [..]. Textos</span><span class="sxs-lookup"><span data-stu-id="6778b-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="6778b-235">Text. div</span><span class="sxs-lookup"><span data-stu-id="6778b-235">Text.Div</span></span>

<span data-ttu-id="6778b-236">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6778b-237">Paciente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="6778b-237">Patient =  \<patient id></span></span>

<span data-ttu-id="6778b-238">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="6778b-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="6778b-239">Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="6778b-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="6778b-240">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": "ID": "<Resource-ID": {"resourceType": "AllergyIntolerance", "ID": "Resource-ID>", "recordedDate": "2018-09-17T07:00:00.000 Z", "substância": {"texto": "Cashew porcas"}, "status": "confirmado", "reação": [{"substância": {"texto": "Cashew porca allergenic extrair produto injetado"}, "manifestoing": [{"texto": "anaphylactic reação"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="6778b-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="6778b-241">Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="6778b-242">Pedido de medicação</span><span class="sxs-lookup"><span data-stu-id="6778b-242">Medication Order</span></span>

<span data-ttu-id="6778b-243">Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="6778b-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="6778b-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="6778b-244">DateWritten</span></span>
2. <span data-ttu-id="6778b-245">Preparador. exibição</span><span class="sxs-lookup"><span data-stu-id="6778b-245">Prescriber.Display</span></span>
3. <span data-ttu-id="6778b-246">Medicação. display (se referência)</span><span class="sxs-lookup"><span data-stu-id="6778b-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="6778b-247">Medicação. Text (se conceito)</span><span class="sxs-lookup"><span data-stu-id="6778b-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="6778b-248">Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="6778b-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="6778b-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="6778b-249">DateEnded</span></span>
2. <span data-ttu-id="6778b-250">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="6778b-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="6778b-251">Text. div</span><span class="sxs-lookup"><span data-stu-id="6778b-251">Text.Div</span></span>

<span data-ttu-id="6778b-252">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6778b-253">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6778b-253">patient=\<patient id></span></span>
2. <span data-ttu-id="6778b-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6778b-254">_count=\<max results></span></span>

<span data-ttu-id="6778b-255">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="6778b-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="6778b-256">Solicitação: Obtenha o <fhir-Server>/MedicationOrder? paciente =<paciente-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="6778b-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="6778b-257">Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"texto": "Janete-Tablet MG"}, "preparador": {"exibir": "Janete"}, "dosageInstruction": [{"texto": "1 diário"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="6778b-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="6778b-258">Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="6778b-259">Análise</span><span class="sxs-lookup"><span data-stu-id="6778b-259">Coverage</span></span>

<span data-ttu-id="6778b-260">Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:</span><span class="sxs-lookup"><span data-stu-id="6778b-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="6778b-261">Payor</span><span class="sxs-lookup"><span data-stu-id="6778b-261">Payor</span></span>

<span data-ttu-id="6778b-262">Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6778b-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="6778b-263">paciente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6778b-263">patient=\<patient id></span></span>

<span data-ttu-id="6778b-264">Consulte o seguinte exemplo desta chamada:</span><span class="sxs-lookup"><span data-stu-id="6778b-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="6778b-265">Solicitação: Obtenha o <fhir-Server>/Coverage? paciente =<o ID do paciente></span><span class="sxs-lookup"><span data-stu-id="6778b-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="6778b-266">Resposta: {"resourceType": "pacote", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "Coverage", "ID": "<Resource-ID>", "plano": "não há seguro principal", "assinante": {"referência": "paciente/<paciente-identificação>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="6778b-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="6778b-267">Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="6778b-268">Local</span><span class="sxs-lookup"><span data-stu-id="6778b-268">Location</span></span>

<span data-ttu-id="6778b-269">Esse recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="6778b-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="6778b-270">Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obter outros detalhes sobre esse conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="6778b-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
