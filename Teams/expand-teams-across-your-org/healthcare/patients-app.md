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
description: Saiba mais sobre como integrar os registros eletrônicos de assistência médica ao aplicativo Microsoft Teams pacientes usando APIs FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: c80560cb0df48d5c95cf5db2e7bed14a2e0f047d
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772242"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="8288d-103">Integração dos Registros Eletrônicos de Saúde no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8288d-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="8288d-104">A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="8288d-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="8288d-105">Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente.</span><span class="sxs-lookup"><span data-stu-id="8288d-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="8288d-106">Confira o modelo pacientes em listas para começar.</span><span class="sxs-lookup"><span data-stu-id="8288d-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="8288d-107">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="8288d-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="8288d-108">Este artigo destina-se a um desenvolvedor geral de ti de assistência médica interessado em usar APIs do FHIR sobre um sistema de informações médicas para se conectar ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8288d-108">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="8288d-109">Isso permitiria cenários de coordenação que correspondam às necessidades de uma organização de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="8288d-109">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="8288d-110">Artigos vinculados documente as especificações de interface FHIR para o aplicativo Microsoft Teams pacientes, e as seções a seguir explicam o que é necessário para configurar um servidor FHIR e se conectar ao aplicativo pacientes em seu ambiente de desenvolvimento ou locatário.</span><span class="sxs-lookup"><span data-stu-id="8288d-110">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="8288d-111">Também será preciso estar familiarizado com a documentação do servidor FHIR que você escolheu, que deve ser uma das opções com suporte:</span><span class="sxs-lookup"><span data-stu-id="8288d-111">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="8288d-112">Datica (por meio da oferta [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="8288d-112">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="8288d-113">Infor Cloverleaf (por meio da [ponte infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="8288d-113">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="8288d-114">Redox (por meio do [servidor R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="8288d-114">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="8288d-115">Dapasoft (por meio [de Corolar em FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="8288d-115">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="8288d-116">Esse processo não inclui etapas que usam o centro de administração do Microsoft Teams ou cmdlets do PowerShell para habilitar recursos.</span><span class="sxs-lookup"><span data-stu-id="8288d-116">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="8288d-117">A configuração é realizada completamente no lado do servidor/serviço do FHIR e no cliente do aplicativo pacientes.</span><span class="sxs-lookup"><span data-stu-id="8288d-117">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="8288d-118">Mostrado abaixo é a arquitetura do aplicativo pacientes:</span><span class="sxs-lookup"><span data-stu-id="8288d-118">Illustrated below is the architecture of the Patients app:</span></span>

![Diagrama da arquitetura do aplicativo pacientes](../../media/patients-app-architecture.png)

<span data-ttu-id="8288d-120">As seções a seguir explicam os requisitos da camada de acesso a dados somente FHIR para o aplicativo pacientes que um servidor FHIR (ou APIs de FHIR habilitadas para o EHR) devem atender para que você possa se integrar ao aplicativo pacientes, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8288d-120">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="8288d-121">Expectativas em relação à autenticação de usuários</span><span class="sxs-lookup"><span data-stu-id="8288d-121">Expectations around user authentication</span></span>
- <span data-ttu-id="8288d-122">Requisitos técnicos e funcionais da interface de integração</span><span class="sxs-lookup"><span data-stu-id="8288d-122">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="8288d-123">Expectativas em relação ao desempenho e à confiabilidade</span><span class="sxs-lookup"><span data-stu-id="8288d-123">Expectations around performance and reliability</span></span>
- <span data-ttu-id="8288d-124">Expectativas em relação a recursos de FHIR para serem compatíveis com o aplicativo pacientes</span><span class="sxs-lookup"><span data-stu-id="8288d-124">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="8288d-125">Processo de integração e o modelo de compromisso esperado</span><span class="sxs-lookup"><span data-stu-id="8288d-125">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="8288d-126">Como começar a usar o FHIR e alguns desafios comuns enfrentados com o aplicativo pacientes</span><span class="sxs-lookup"><span data-stu-id="8288d-126">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="8288d-127">Requisitos futuros para a próxima iteração do aplicativo pacientes</span><span class="sxs-lookup"><span data-stu-id="8288d-127">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="8288d-128">Nas seções a seguir, a palavra "parceiro" ou "parceiro de interoperabilidade" é usada para fazer referência a qualquer organização de terceiros que habilite a integração a sistemas EHR para o aplicativo pacientes por meio do FHIR e está implementando um servidor FHIR para corresponder às especificações listadas.</span><span class="sxs-lookup"><span data-stu-id="8288d-128">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="8288d-129">Requisitos funcionais e técnicos</span><span class="sxs-lookup"><span data-stu-id="8288d-129">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="8288d-130">Autenticação</span><span class="sxs-lookup"><span data-stu-id="8288d-130">Authentication</span></span>  

<span data-ttu-id="8288d-131">A autorização em nível de aplicativo sem *suporte para a autorização em nível de usuário* é a maneira mais comum de executar transformações de dados e expor conexões a dados EHR por meio do FHIR, mesmo que o sistema EHR implemente a autorização em nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="8288d-131">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="8288d-132">O serviço de interoperabilidade (parceiro) obtém acesso elevado aos dados do EHR e, quando expõe os mesmos dados dos recursos FHIR apropriados, não há contexto de autorização aprovado para o consumidor do serviço de interoperabilidade (o aplicativo pacientes) com o serviço de interoperabilidade ou a plataforma.</span><span class="sxs-lookup"><span data-stu-id="8288d-132">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="8288d-133">O aplicativo pacientes não poderá impor a autorização no nível do usuário, mas dá suporte a aplicativos para autenticação de aplicativos entre o aplicativo pacientes e o serviço do parceiro de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="8288d-133">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="8288d-134">O aplicativo para o modelo de autenticação do aplicativo está descrito abaixo:</span><span class="sxs-lookup"><span data-stu-id="8288d-134">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="8288d-135">A autenticação do serviço para o serviço deve ser feita por meio do [fluxo de credenciais do cliente](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0.</span><span class="sxs-lookup"><span data-stu-id="8288d-135">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="8288d-136">O serviço de parceiro precisa fornecer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8288d-136">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="8288d-137">O serviço de parceiro permite que o aplicativo pacientes crie uma conta com o parceiro, o que habilita o aplicativo pacientes a gerar e possuir client_id e client_secret, gerenciados por meio de um portal de registro de autenticação no servidor de autenticação do parceiro.</span><span class="sxs-lookup"><span data-stu-id="8288d-137">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="8288d-138">O serviço de parceiro pertence ao sistema de autenticação/autorização, que aceita e verifica (autentica) as credenciais de cliente fornecidas e retorna um token de acesso com dica de locatário em escopo, conforme descrito a seguir.</span><span class="sxs-lookup"><span data-stu-id="8288d-138">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="8288d-139">Por motivos de segurança ou em caso de uma violação secreta, o aplicativo pacientes pode regenerar o segredo e invalidar ou excluir o antigo segredo (exemplo do mesmo está disponível no portal do Azure – registro do aplicativo AAD).</span><span class="sxs-lookup"><span data-stu-id="8288d-139">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="8288d-140">O ponto de extremidade de metadados que hospeda a instrução de conformidade deve ser não autenticado, deve ser acessível sem token de autenticação.</span><span class="sxs-lookup"><span data-stu-id="8288d-140">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="8288d-141">O serviço de parceiro fornece o ponto de extremidade do token para que o aplicativo pacientes solicite um token de acesso usando um fluxo de credenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="8288d-141">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="8288d-142">A URL do token de acordo com o servidor de autorização deve fazer parte da instrução FHIR conformidade (funcionalidade) buscada pelos metadados no servidor FHIR como neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="8288d-142">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

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

<span data-ttu-id="8288d-143">Uma solicitação de um token de acesso consiste nos seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8288d-143">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="8288d-144">O serviço de parceiro fornece o client_id e o client_secret para aplicativo pacientes, gerenciados por meio de um portal de registro de autenticação no lado do parceiro.</span><span class="sxs-lookup"><span data-stu-id="8288d-144">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="8288d-145">O serviço de parceiro fornece o ponto de extremidade para solicitar o token de acesso usando um fluxo de credenciais de cliente.</span><span class="sxs-lookup"><span data-stu-id="8288d-145">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="8288d-146">Uma resposta bem-sucedida deve incluir os parâmetros token_type, access_token e expires_in.</span><span class="sxs-lookup"><span data-stu-id="8288d-146">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="8288d-147">Roteamento: mapeando o locatário do AAD para o ponto de extremidade do provedor</span><span class="sxs-lookup"><span data-stu-id="8288d-147">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="8288d-148">O aplicativo pacientes se conecta a um serviço de parceiro por meio de um único ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="8288d-148">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="8288d-149">O serviço de parceiro possui um mecanismo e mantém um mecanismo para mapear cada cliente da Microsoft (ID de locatário do AAD) para um provedor de assistência médica (servidor FHIR) com o qual o serviço de parceiro está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="8288d-149">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="8288d-150">O mapeamento do locatário AAD para um ponto de extremidade do provedor usa a ID de locatário (GUID) do AAD.</span><span class="sxs-lookup"><span data-stu-id="8288d-150">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="8288d-151">O aplicativo pacientes transmite a ID de locatário em escopo durante a solicitação de um token de acesso para cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="8288d-151">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="8288d-152">O serviço de parceiro mantém o mapeamento da ID de locatário para o ponto de extremidade do provedor e redireciona solicitações para um ponto de extremidade do provedor com base na ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="8288d-152">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="8288d-153">Para fazer isso, o parceiro aceita a configuração no final (manualmente ou por meio de um portal como parte do integração de organizações de provedores à plataforma de interoperabilidade).</span><span class="sxs-lookup"><span data-stu-id="8288d-153">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="8288d-154">O fluxo de trabalho de autenticação e roteamento é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="8288d-154">The Authentication and Routing workflow is shown below:</span></span>

![Diagrama do fluxo de trabalho de autenticação e roteamento](../../media/Patient-app-6.png)

1. <span data-ttu-id="8288d-156">Solicitação de token de acesso do aplicativo enviando:</span><span class="sxs-lookup"><span data-stu-id="8288d-156">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="8288d-157">Responda com um token de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="8288d-157">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="8288d-158">Solicitar dados protegidos com token de acesso.</span><span class="sxs-lookup"><span data-stu-id="8288d-158">Request protected data with Access token.</span></span>

4. <span data-ttu-id="8288d-159">Mensagem de autorização: selecione o servidor FHIR apropriado para direcionar a partir da ID de locatário no escopo.</span><span class="sxs-lookup"><span data-stu-id="8288d-159">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="8288d-160">Envia os dados protegidos do aplicativo do servidor FHIR autorizado após a autenticação com o token do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8288d-160">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="8288d-161">Classes</span><span class="sxs-lookup"><span data-stu-id="8288d-161">Interfaces</span></span>

<span data-ttu-id="8288d-162">As chamadas e os campos específicos usados pelo aplicativo pacientes são documentados nos artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="8288d-162">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="8288d-163">Selecione a interface aplicável às APIs do FHIR Server/FHIR.</span><span class="sxs-lookup"><span data-stu-id="8288d-163">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="8288d-164">Especificação de interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="8288d-164">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="8288d-165">Especificação de interface STU3</span><span class="sxs-lookup"><span data-stu-id="8288d-165">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="8288d-166">Desempenho e confiabilidade</span><span class="sxs-lookup"><span data-stu-id="8288d-166">Performance and Reliability</span></span>

<span data-ttu-id="8288d-167">Enquanto o aplicativo pacientes está em visualização particular, não há garantias sobre o desempenho de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="8288d-167">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="8288d-168">Fatores em desempenho incluem as latências relativas de todos os saltos envolvidos no fluxo de trabalho, começando pelo EHR no ambiente do sistema de integridade, ao parceiro de interoperabilidade e sua infra-estrutura, incluindo o servidor FHIR e entre o aplicativo Office 365 ecossistema e pacientes.</span><span class="sxs-lookup"><span data-stu-id="8288d-168">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Ilustração do desempenho de parceiros de interoperabilidade](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="8288d-170">Comece a usar o FHIR</span><span class="sxs-lookup"><span data-stu-id="8288d-170">Get started with FHIR</span></span>  

<span data-ttu-id="8288d-171">Se você não tem experiência com o FHIR e precisa de acesso fácil a um servidor FHIR que você possa expor à interface de integração do EHR do Microsoft Teams, a Microsoft tem um servidor FHIR de código-fonte aberto disponível para todos os desenvolvedores usarem.</span><span class="sxs-lookup"><span data-stu-id="8288d-171">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="8288d-172">Consulte o artigo o [que é FHIR Server para Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para saber mais sobre o servidor de fonte de FHIR aberto disponível na Microsoft e implementá-lo para suas organizações.</span><span class="sxs-lookup"><span data-stu-id="8288d-172">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="8288d-173">Você também pode usar o ambiente do EHR da área restrita do HSPC aberto para criar um EHR que também ofereça suporte a um servidor FHIR aberto e usá-lo para brincar com o aplicativo pacientes.</span><span class="sxs-lookup"><span data-stu-id="8288d-173">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="8288d-174">Recomendamos que você leia a [documentação da área restrita do HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span><span class="sxs-lookup"><span data-stu-id="8288d-174">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="8288d-175">Além disso, a área restrita fornece uma maneira fácil, orientada à interface do usuário e fácil de criar, adicionar e editar pacientes, além de oferecer várias amostras para começar.</span><span class="sxs-lookup"><span data-stu-id="8288d-175">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
