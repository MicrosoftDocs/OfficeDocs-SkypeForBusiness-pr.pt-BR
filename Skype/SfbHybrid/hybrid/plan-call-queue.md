---
title: Planejar uma fila de chamada na nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso de um assistente automático na nuvem com o Skype for Business Server 2019.
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110487"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="36393-103">Planejar filas de chamadas da nuvem</span><span class="sxs-lookup"><span data-stu-id="36393-103">Plan Cloud call queues</span></span>

<span data-ttu-id="36393-104">Fila de chamadas na nuvem é um serviço que aceita chamadas de clientes, reproduz uma mensagem de saudação e coloca essas chamadas em uma fila de espera enquanto pesquisa uma lista pré-configurada de agentes para atender a essas chamadas.</span><span class="sxs-lookup"><span data-stu-id="36393-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="36393-105">Você pode definir o conjunto de agentes em listas de distribuição habilitadas para email ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="36393-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="36393-106">Sua organização pode ter uma ou muitas filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="36393-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="36393-107">Filas de chamada geralmente são usadas em combinação com os atendimentos automáticos.</span><span class="sxs-lookup"><span data-stu-id="36393-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="36393-108">Além disso, as filas de chamada na nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="36393-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="36393-109">Música enquanto os chamadores aguardam em espera</span><span class="sxs-lookup"><span data-stu-id="36393-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="36393-110">Configurações personalizadas para o tamanho máximo da fila de chamada, tempo limite e opções de tratamento de chamada</span><span class="sxs-lookup"><span data-stu-id="36393-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="36393-111">Cada fila de chamadas é atribuída **a** uma conta de recurso (consulte [Configurar](configure-onprem-ra.md)contas de recursos ) em seu sistema do Skype for Business Server 2019 que será vinculado diretamente a uma fila de chamadas no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36393-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="36393-112">Consulte [Criar uma fila de chamada na](/MicrosoftTeams/create-a-phone-system-call-queue) nuvem para obter mais detalhes sobre quais filas de chamada são e quais opções e recursos existem para filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="36393-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="36393-113">Você pode atribuir vários números de telefone a uma fila de chamadas, mas eles devem ser números de serviço da Microsoft, números de Roteamento Direto ou números híbridos.</span><span class="sxs-lookup"><span data-stu-id="36393-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="36393-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36393-114">Requirements</span></span>

<span data-ttu-id="36393-115">Os requisitos a seguir pressuem que você já tenha o Skype for Business Server 2019 implantado em uma topologia com suporte.</span><span class="sxs-lookup"><span data-stu-id="36393-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="36393-116">Seus requisitos dependem do cenário:</span><span class="sxs-lookup"><span data-stu-id="36393-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="36393-117">Para uma nova configuração de filas de chamada na nuvem, siga as etapas descritas em [Configure resource accounts](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="36393-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="36393-118">Você precisará criar contas de recursos online ou no Skype for Business Server 2019, e talvez também seja necessário associar um número de telefone à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="36393-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="36393-119">Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de fila de chamada do Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="36393-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="36393-120">Conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="36393-120">Hybrid connectivity.</span></span> <span data-ttu-id="36393-121">Se você já tiver o Skype for Business Server implantado e quiser habilitar filas de chamadas na nuvem para seus usuários locais, você deve garantir que você tenha a conectividade híbrida configurada entre seus ambientes locais e online.</span><span class="sxs-lookup"><span data-stu-id="36393-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="36393-122">Às vezes, isso é chamado de configuração de domínio dividido.</span><span class="sxs-lookup"><span data-stu-id="36393-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="36393-123">Para obter mais informações, consulte Plan [hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="36393-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="36393-124">Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefonia sem custo.</span><span class="sxs-lookup"><span data-stu-id="36393-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="36393-125">Isso fornece recursos do Sistema de Telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendimento automático e fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="36393-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="36393-126">Crie uma conta de recurso local [para](configure-onprem-ra.md) cada fila de chamadas e atribua uma licença e um número de telefone, se necessário.</span><span class="sxs-lookup"><span data-stu-id="36393-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="36393-127">Quando você tiver uma estrutura sólida que atenda às suas necessidades e um script que orienta os clientes com eficiência, prossiga para [Configurar contas de recursos.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="36393-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36393-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="36393-128">See Also</span></span>

[<span data-ttu-id="36393-129">Configurar contas de recurso</span><span class="sxs-lookup"><span data-stu-id="36393-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="36393-130">Habilitar gravação de prompt personalizado usando a interface do usuário de telefone</span><span class="sxs-lookup"><span data-stu-id="36393-130">Enable custom prompt recording using the telephone user interface</span></span>](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="36393-131">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="36393-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="36393-132">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="36393-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="36393-133">Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="36393-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="36393-134">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="36393-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="36393-135">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36393-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)