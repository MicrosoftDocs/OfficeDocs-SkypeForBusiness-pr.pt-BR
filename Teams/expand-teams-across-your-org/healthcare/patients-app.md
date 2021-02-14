---
title: Visão geral do aplicativo de pacientes
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
description: Saiba mais sobre como integrar registros de assistência médica eletrônica ao aplicativo Pacientes do Microsoft Teams usando APIs FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803539"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="01d91-103">Integração dos Registros Eletrônicos de Saúde no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01d91-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="01d91-104">A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="01d91-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="01d91-105">Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe.</span><span class="sxs-lookup"><span data-stu-id="01d91-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="01d91-106">Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="01d91-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="01d91-107">Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="01d91-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="01d91-108">Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes.</span><span class="sxs-lookup"><span data-stu-id="01d91-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="01d91-109">Confira o modelo Pacientes em Listas para começar.</span><span class="sxs-lookup"><span data-stu-id="01d91-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="01d91-110">Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="01d91-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="01d91-111">Este artigo destina-se a um desenvolvedor geral de SERVIÇOS de SAÚDE interessado em usar APIs FHIR na parte superior de um sistema de informações médicas para se conectar ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01d91-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="01d91-112">Isso habilitaria cenários de coordenação de atendimento que corresponderem às necessidades de uma organização de saúde.</span><span class="sxs-lookup"><span data-stu-id="01d91-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="01d91-113">Os artigos vinculados documentam as especificações de interface FHIR do aplicativo Pacientes do Microsoft Teams e as seções a seguir explicam o que é necessário para configurar um servidor FHIR e conectar-se ao aplicativo Pacientes em seu ambiente de desenvolvimento ou locatário.</span><span class="sxs-lookup"><span data-stu-id="01d91-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="01d91-114">Você também precisará estar familiarizado com a documentação do servidor FHIR que você escolheu, que deve ser uma das opções com suporte:</span><span class="sxs-lookup"><span data-stu-id="01d91-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="01d91-115">Datica (por meio de sua oferta [de CMI)](https://datica.com/compliant-managed-integration/)</span><span class="sxs-lookup"><span data-stu-id="01d91-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="01d91-116">Infor Ltda (através da Ponte [Infor FHIR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="01d91-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="01d91-117">Redox (por meio do [servidor R^FHIR)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="01d91-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="01d91-118">Dapasoft (por [meio deLalar em FHIR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="01d91-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="01d91-119">Esse processo não inclui etapas que usam o centro de administração do Microsoft Teams ou cmdlets do PowerShell para habilitar recursos.</span><span class="sxs-lookup"><span data-stu-id="01d91-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="01d91-120">A configuração é totalmente feita no lado do servidor/serviço FHIR e no cliente do aplicativo Pacientes.</span><span class="sxs-lookup"><span data-stu-id="01d91-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="01d91-121">Ilustrado abaixo está a arquitetura do aplicativo Pacientes:</span><span class="sxs-lookup"><span data-stu-id="01d91-121">Illustrated below is the architecture of the Patients app:</span></span>

![Diagrama da arquitetura do aplicativo Pacientes](../../media/patients-app-architecture.png)

<span data-ttu-id="01d91-123">As seções a seguir explicam os requisitos da camada de acesso de dados somente FHIR para o aplicativo Pacientes que um servidor FHIR (ou APIs FHR habilitadas para FHIR) devem atender para integrar-se ao aplicativo Pacientes, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="01d91-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="01d91-124">Expectativas em relação à autenticação do usuário</span><span class="sxs-lookup"><span data-stu-id="01d91-124">Expectations around user authentication</span></span>
- <span data-ttu-id="01d91-125">Requisitos funcionais e técnicos da interface de integração</span><span class="sxs-lookup"><span data-stu-id="01d91-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="01d91-126">Expectativas em relação ao desempenho e à confiabilidade</span><span class="sxs-lookup"><span data-stu-id="01d91-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="01d91-127">Expectativas em torno dos recursos FHIR para serem suportados para o aplicativo Pacientes</span><span class="sxs-lookup"><span data-stu-id="01d91-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="01d91-128">Processo de integração e o modelo de compromisso esperado</span><span class="sxs-lookup"><span data-stu-id="01d91-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="01d91-129">Como começar a usar o FHIR e alguns desafios comuns com o aplicativo Pacientes</span><span class="sxs-lookup"><span data-stu-id="01d91-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="01d91-130">Requisitos futuros para a próxima iteração do aplicativo Pacientes</span><span class="sxs-lookup"><span data-stu-id="01d91-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="01d91-131">Nas seções a seguir, a palavra "parceiro" ou "parceiro Interop" é usada para se referir a qualquer Organização de terceiros que permita a integração com sistemas EHR para o aplicativo Pacientes por meio de FHIR e está implementando um Servidor FHIR para corresponder às especificações listadas.</span><span class="sxs-lookup"><span data-stu-id="01d91-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="01d91-132">Requisitos técnicos e funcionais</span><span class="sxs-lookup"><span data-stu-id="01d91-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="01d91-133">Autenticação</span><span class="sxs-lookup"><span data-stu-id="01d91-133">Authentication</span></span>  

<span data-ttu-id="01d91-134">A autorização  em nível de aplicativo sem suporte para autorização em nível de usuário é a maneira mais comumente suportada de realizar transformações de dados e expor conexões a dados de EHR por meio de FHIR, mesmo que o sistema EHR possa implementar a autorização no nível do usuário.</span><span class="sxs-lookup"><span data-stu-id="01d91-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="01d91-135">O Serviço Interop (Parceiro) obtém acesso elevado aos dados de EHR e, quando eles expõem os mesmos dados que os recursos FHIR apropriados, não há contexto de autorização passado para o Consumidor do Serviço Interop (o aplicativo Pacientes) integrar com o Serviço ou Plataforma Interop.</span><span class="sxs-lookup"><span data-stu-id="01d91-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="01d91-136">O aplicativo Pacientes não poderá impor a autorização no nível do usuário, mas dá suporte ao aplicativo para autenticação de aplicativos entre o aplicativo Pacientes e o serviço do parceiro Interop.</span><span class="sxs-lookup"><span data-stu-id="01d91-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="01d91-137">O modelo de autenticação de Aplicativo para Aplicativo é descrito abaixo:</span><span class="sxs-lookup"><span data-stu-id="01d91-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="01d91-138">A autenticação de serviço para serviço deve ser [](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)feita por meio do fluxo de Credenciais do Cliente OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="01d91-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="01d91-139">O serviço de parceiro precisa fornecer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="01d91-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="01d91-140">O serviço Parceiro permite que o aplicativo Pacientes crie uma conta com o Parceiro, que permite que o aplicativo Pacientes gere e possui o client_id e o client_secret, gerenciados por meio de um portal de registro autenticado no servidor autenticação do parceiro.</span><span class="sxs-lookup"><span data-stu-id="01d91-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="01d91-141">O serviço parceiro é proprietário do sistema autenticação/autorização, que aceita e verifica (autentica) as credenciais do cliente fornecidas e fornece um token de acesso com dica de locatário no escopo, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="01d91-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="01d91-142">Por motivos de segurança ou em caso de violação secreta, o aplicativo Pacientes pode gerar o segredo e invalidar ou excluir o antigo segredo (exemplo do mesmo está disponível no Portal do Azure – Registro de Aplicativo do AAD).</span><span class="sxs-lookup"><span data-stu-id="01d91-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="01d91-143">O ponto de extremidade de metadados que hospeda a instrução de conformidade deve ser não autenticado, deve ser acessível sem token de autenticação.</span><span class="sxs-lookup"><span data-stu-id="01d91-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="01d91-144">O serviço parceiro fornece o ponto de extremidade de token para o aplicativo Pacientes solicitar um token de acesso usando um fluxo de credenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="01d91-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="01d91-145">A URL do token conforme o servidor de autorização deve fazer parte da instrução de conformidade (recurso) FHIR buscada de metadados no servidor FHIR, como neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="01d91-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="01d91-146">Uma solicitação para um token de acesso consiste nos seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="01d91-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="01d91-147">O serviço parceiro fornece o client_id e o client_secret para Pacientes, gerenciados por meio de um portal de registro Auth no lado do parceiro.</span><span class="sxs-lookup"><span data-stu-id="01d91-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="01d91-148">O serviço parceiro fornece o ponto de extremidade para solicitar token de acesso usando um fluxo de credenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="01d91-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="01d91-149">Uma resposta bem-sucedida deve incluir os token_type, access_token e expires_in parâmetros.</span><span class="sxs-lookup"><span data-stu-id="01d91-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="01d91-150">Roteamento: Mapeando o locatário do AAD para o ponto de extremidade do provedor</span><span class="sxs-lookup"><span data-stu-id="01d91-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="01d91-151">O aplicativo Pacientes conecta-se a um serviço de parceiro por meio de um único ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="01d91-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="01d91-152">O serviço de parceiro possui e mantém um mecanismo para mapear cada cliente da Microsoft (ID de Locatário do AAD) para um respectivo provedor de saúde (servidor FHIR) com o que o serviço de parceiro está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="01d91-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="01d91-153">O mapeamento do locatário do AAD para um ponto de extremidade do provedor usa a ID de Locatário do AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="01d91-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="01d91-154">O aplicativo Pacientes passa pela ID do Locatário no escopo, ao solicitar um token de acesso para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="01d91-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="01d91-155">O serviço parceiro mantém o mapeamento da ID do Locatário para o ponto de extremidade do provedor e redireciona solicitações para um ponto de extremidade do provedor com base na ID do Locatário.</span><span class="sxs-lookup"><span data-stu-id="01d91-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="01d91-156">Para fazer isso, o parceiro dá suporte à configuração em sua extremidade (manualmente ou por meio de um portal como parte da integração de organizações de provedores em sua Plataforma Interop).</span><span class="sxs-lookup"><span data-stu-id="01d91-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="01d91-157">O fluxo de trabalho Autenticação e Roteamento é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="01d91-157">The Authentication and Routing workflow is shown below:</span></span>

![Diagrama do fluxo de trabalho Autenticação e Roteamento](../../media/Patient-app-6.png)

1. <span data-ttu-id="01d91-159">Solicite o token de acesso ao aplicativo enviando:</span><span class="sxs-lookup"><span data-stu-id="01d91-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="01d91-160">Responder com um token de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="01d91-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="01d91-161">Solicite dados protegidos com o token do Access.</span><span class="sxs-lookup"><span data-stu-id="01d91-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="01d91-162">Mensagem de autorização: selecione o servidor FHIR apropriado para roteá-lo da ID do locatário no escopo.</span><span class="sxs-lookup"><span data-stu-id="01d91-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="01d91-163">Envia os dados protegidos do aplicativo do servidor FHIR autorizado após a autenticação com o token de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="01d91-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="01d91-164">Interfaces</span><span class="sxs-lookup"><span data-stu-id="01d91-164">Interfaces</span></span>

<span data-ttu-id="01d91-165">Chamadas e campos específicos usados pelo aplicativo Pacientes são documentados nos artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="01d91-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="01d91-166">Selecione a interface aplicável ao seu servidor FHIR/APIs FHIR.</span><span class="sxs-lookup"><span data-stu-id="01d91-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="01d91-167">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="01d91-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="01d91-168">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="01d91-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="01d91-169">Desempenho e confiabilidade</span><span class="sxs-lookup"><span data-stu-id="01d91-169">Performance and Reliability</span></span>

<span data-ttu-id="01d91-170">Enquanto o aplicativo Pacientes está em visualização privada, não há garantias sobre o desempenho de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="01d91-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="01d91-171">Os fatores de desempenho incluem as latências relativas de todos os saltos envolvidos no fluxo de trabalho, começando pelo EHR no ambiente do sistema de saúde, até o parceiro Interop e seu infra, incluindo o Servidor FHIR e até o ecossistema e o aplicativo Pacientes do Office 365.</span><span class="sxs-lookup"><span data-stu-id="01d91-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Ilustração do desempenho dos parceiros Interop](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="01d91-173">Começar a trabalhar com FHIR</span><span class="sxs-lookup"><span data-stu-id="01d91-173">Get started with FHIR</span></span>  

<span data-ttu-id="01d91-174">Se você for novo na FHIR e precisar de acesso fácil a um Servidor FHIR que possa expor à interface de integração do Microsoft Teams EHR, a Microsoft tem um servidor FHIR de código aberto disponível para todos os desenvolvedores usarem.</span><span class="sxs-lookup"><span data-stu-id="01d91-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="01d91-175">Confira o artigo O que é o FHIR Server para [Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para saber mais sobre o servidor FHIR de código aberto disponível na Microsoft e implantá-lo para suas organizações.</span><span class="sxs-lookup"><span data-stu-id="01d91-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="01d91-176">Você também pode usar o ambiente HSPC Open sandbox EHR para criar um EHR que também oferece suporte a um servidor FHIR aberto e usá-lo para brincar com o aplicativo Pacientes.</span><span class="sxs-lookup"><span data-stu-id="01d91-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="01d91-177">Recomendamos que você leia a documentação [da área de trabalho HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="01d91-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="01d91-178">Além de oferecer uma maneira fácil, voltada para a interface do usuário e fácil de criar, adicionar e editar Pacientes, a área de trabalho oferece várias amostras para começar.</span><span class="sxs-lookup"><span data-stu-id="01d91-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
