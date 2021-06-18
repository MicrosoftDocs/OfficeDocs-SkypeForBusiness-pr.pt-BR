## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="6cf11-101">Modelos de integração para provedores de soluções</span><span class="sxs-lookup"><span data-stu-id="6cf11-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="6cf11-102">Como provedor de soluções de central de contatos, há três modelos a escolher para integrar sua solução de central de contatos conectada ao Teams:</span><span class="sxs-lookup"><span data-stu-id="6cf11-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="6cf11-103">Se você quiser usar SBCs certificados e Roteamento Direto para conectar uma solução de central de contatos ao Teams, consulte o [modelo Connect](?tabs=connect#steps).</span><span class="sxs-lookup"><span data-stu-id="6cf11-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="6cf11-104">Se você quiser usar bots do Azure e as APIs de Comunicação do Microsoft Graph para habilitar provedores de soluções para criar aplicativos do Teams, consulte o modelo [extend](?tabs=extend#steps).</span><span class="sxs-lookup"><span data-stu-id="6cf11-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="6cf11-105">Se você quiser usar um SDK que habilita os provedores de soluções a compartilhar experiências nativas do Teams em seu Aplicativo, consulte o [modelo power](?tabs=power#steps).</span><span class="sxs-lookup"><span data-stu-id="6cf11-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="6cf11-106">As soluções de energia serão possíveis quando o SDK estiver disponível, no final de 2021.</span><span class="sxs-lookup"><span data-stu-id="6cf11-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="6cf11-107">**O modelo Connect**</span><span class="sxs-lookup"><span data-stu-id="6cf11-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="6cf11-108">O modelo Connect usa SBCs certificados pela Microsoft e Roteamento Direto para conectar soluções de contact center à infraestrutura do sistema de telefonia do Teams, habilitando o roteamento, a configuração e as percepções do sistema aprimoradas.</span><span class="sxs-lookup"><span data-stu-id="6cf11-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="6cf11-109">Os agentes podem configurar assistentes virtuais automatizados e filas de roteamento baseadas em habilidades para coletar informações e conectar clientes com especialistas no assunto.</span><span class="sxs-lookup"><span data-stu-id="6cf11-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="6cf11-110">**Destaques do recurso:**</span><span class="sxs-lookup"><span data-stu-id="6cf11-110">**Feature highlights:**</span></span>

<span data-ttu-id="6cf11-111">Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:</span><span class="sxs-lookup"><span data-stu-id="6cf11-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="6cf11-112">AuthN do Office 365 para que os agentes se conectem ao locatário da Microsoft a partir do cliente CCaaS integrado</span><span class="sxs-lookup"><span data-stu-id="6cf11-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="6cf11-113">Veja quando os agentes estão disponíveis com o Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="6cf11-114">Transferências e suporte a chamada de grupo com o Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="6cf11-115">APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="6cf11-116">Tronco SIP de vários locatários para dar suporte a vários clientes no SBC do provedor de soluções.</span><span class="sxs-lookup"><span data-stu-id="6cf11-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="6cf11-117">Provedores de soluções para usar o [ <span class="underline">controlador de borda de sessão certificado pela Microsoft (SBC)</span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="6cf11-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="6cf11-118">**O modelo Extend**</span><span class="sxs-lookup"><span data-stu-id="6cf11-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="6cf11-119">O modelo Extend se integra ao cliente do Teams usando a plataforma cliente [do Teams,](/microsoftteams/platform/overview) [APIs do Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e API de [Comunicações na Nuvem no Microsoft Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="6cf11-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="6cf11-120">O modelo Extend também usa o sistema de telefonia do Teams para todas as chamadas e experiências de controle de chamadas da central de contatos, e o provedor de soluções do centro de contatos atua como uma operadora de telefonia juntamente com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6cf11-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="6cf11-121">Os agentes podem usar o Teams para colaboração interna e comunicação externa e podem se beneficiar de notas contextuais dinâmicas correlacionando dados de vários sistemas antes de iniciar um envolvimento e, em seguida, evitar a alternência de contexto custosa.</span><span class="sxs-lookup"><span data-stu-id="6cf11-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="6cf11-122">As organizações podem projetar fluxos de trabalho e configurações de roteamento avançadas para o indivíduo e medir a qualidade de seu sistema e interações.</span><span class="sxs-lookup"><span data-stu-id="6cf11-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="6cf11-123">**Destaques do recurso:**</span><span class="sxs-lookup"><span data-stu-id="6cf11-123">**Feature highlights:**</span></span>

<span data-ttu-id="6cf11-124">Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:</span><span class="sxs-lookup"><span data-stu-id="6cf11-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="6cf11-125">APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="6cf11-126">Aplicativo baseado no Teams para experiências de agente</span><span class="sxs-lookup"><span data-stu-id="6cf11-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="6cf11-127">Teams como o ponto de extremidade de chamada principal para os agentes</span><span class="sxs-lookup"><span data-stu-id="6cf11-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="6cf11-128">Cliente teams chamando todos os controles de chamada</span><span class="sxs-lookup"><span data-stu-id="6cf11-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="6cf11-129">Aplicativo de experiência de agente para cliente web e móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="6cf11-130">Análise, gerenciamento de fluxo de trabalho, experiências baseadas em função para agentes no aplicativo CCaaS no Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="6cf11-131">Experiências de chat e colaboração integradas aos clientes do Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="6cf11-132">Preservar o desempenho e a qualidade das experiências do cliente do Teams em todos os aplicativos</span><span class="sxs-lookup"><span data-stu-id="6cf11-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="6cf11-133">**O modelo Power**</span><span class="sxs-lookup"><span data-stu-id="6cf11-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="6cf11-134">O modelo Power permite que provedores de soluções criem aplicativos de voz nativos baseados no Azure usando a infraestrutura de chamadas do Teams e a plataforma de cliente para fornecer soluções modernas e inteligentes para conexão colaborativa de cliente e agente.</span><span class="sxs-lookup"><span data-stu-id="6cf11-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="6cf11-135">O objetivo do modelo Power é fornecer uma experiência de central de contatos de um aplicativo com uma tela.</span><span class="sxs-lookup"><span data-stu-id="6cf11-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="6cf11-136">**Destaques do recurso:**</span><span class="sxs-lookup"><span data-stu-id="6cf11-136">**Feature highlights:**</span></span>

<span data-ttu-id="6cf11-137">Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:</span><span class="sxs-lookup"><span data-stu-id="6cf11-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="6cf11-138">Experiências de agente formais habilitadas de forma nativa para comunicação omnicanal por meio do SDK do Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="6cf11-139">Usar os serviços de colaboração do Teams para colaboração de agentes e interações do cliente</span><span class="sxs-lookup"><span data-stu-id="6cf11-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="6cf11-140">Provisionamento rápido de serviços de nuvem, implantar em qualquer lugar</span><span class="sxs-lookup"><span data-stu-id="6cf11-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="6cf11-141">Controle de conversa direta e interação com usuários durante conversas do Teams</span><span class="sxs-lookup"><span data-stu-id="6cf11-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="6cf11-142">O modelo Power estará disponível no final de 2021.</span><span class="sxs-lookup"><span data-stu-id="6cf11-142">The Power model will be available towards the end of 2021.</span></span>
