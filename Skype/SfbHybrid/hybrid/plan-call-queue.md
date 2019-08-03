---
title: Planejar uma fila de chamada em nuvem
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso de um atendedor automático na nuvem com o Skype for Business Server 2019.
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160401"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="fbf23-103">Planejar filas de chamada em nuvem</span><span class="sxs-lookup"><span data-stu-id="fbf23-103">Plan Cloud call queues</span></span>

<span data-ttu-id="fbf23-104">A fila de chamada em nuvem é um serviço que aceita chamadas de clientes, reproduz uma mensagem de saudação e, em seguida, coloca essas chamadas em uma fila de espera durante a pesquisa de uma lista de agentes pré-configurada para responder a essas chamadas.</span><span class="sxs-lookup"><span data-stu-id="fbf23-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="fbf23-105">Você pode definir o conjunto de agentes em listas de distribuição ou grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="fbf23-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="fbf23-106">Sua organização pode ter uma ou várias filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="fbf23-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="fbf23-107">As filas de chamadas normalmente são usadas em combinação com atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="fbf23-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="fbf23-108">Além disso, as filas de chamadas em nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="fbf23-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="fbf23-109">Música enquanto os chamadores estão aguardando em espera</span><span class="sxs-lookup"><span data-stu-id="fbf23-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="fbf23-110">Configurações personalizadas para o tamanho máximo, tempo limite e opções de tratamento de chamadas da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="fbf23-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="fbf23-111">Cada fila de chamada é atribuída a uma **conta de recurso** (consulte [Configure Resource](configure-onprem-ra.md)accounts) no seu sistema Skype for Business Server 2019 que será vinculada diretamente a uma fila de chamada no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fbf23-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fbf23-112">Consulte [criar uma fila de chamada em nuvem](/MicrosoftTeams/create-a-phone-system-call-queue) para obter mais detalhes sobre quais filas de chamadas são e quais opções e recursos existem para filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fbf23-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="fbf23-113">Você pode atribuir vários números de telefone a uma fila de chamadas, mas eles devem ser números de serviço da Microsoft ou números híbridos.</span><span class="sxs-lookup"><span data-stu-id="fbf23-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="fbf23-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbf23-114">Requirements</span></span>

<span data-ttu-id="fbf23-115">Os requisitos a seguir pressupõem que você já tenha o Skype for Business Server 2019 implantado em uma topologia com suporte.</span><span class="sxs-lookup"><span data-stu-id="fbf23-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="fbf23-116">Seus requisitos dependem do cenário:</span><span class="sxs-lookup"><span data-stu-id="fbf23-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="fbf23-117">Para uma nova configuração de filas de chamada em nuvem, siga as etapas descritas em [Configure Resource](configure-onprem-ra.md)accounts.</span><span class="sxs-lookup"><span data-stu-id="fbf23-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="fbf23-118">Você precisará criar contas de recurso online ou no Skype for Business Server 2019, e talvez também precise associar um número de telefone à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fbf23-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="fbf23-119">Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de fila de chamadas da nuvem da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="fbf23-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="fbf23-120">Conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="fbf23-120">Hybrid connectivity.</span></span> <span data-ttu-id="fbf23-121">Se você já tiver o Skype for Business Server implantado e quiser habilitar as filas de chamadas em nuvem para seus usuários locais, você deve garantir que a conectividade híbrida seja configurada entre seus ambientes locais e online.</span><span class="sxs-lookup"><span data-stu-id="fbf23-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="fbf23-122">Isso às vezes é chamado de configuração de domínio dividido.</span><span class="sxs-lookup"><span data-stu-id="fbf23-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="fbf23-123">Para saber mais, confira [planejar conectividade híbrida entre o Skype for Business Server e o office 365](plan-hybrid-connectivity.md) e [Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="fbf23-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="fbf23-124">Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefonia livre de custo.</span><span class="sxs-lookup"><span data-stu-id="fbf23-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="fbf23-125">Isso fornece recursos do sistema de telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendedor automático e fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fbf23-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="fbf23-126">Crie uma [conta de recurso](configure-onprem-ra.md) local para cada fila de chamadas e atribua uma licença e um número de telefone, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fbf23-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="fbf23-127">Recursos adicionais de planejamento</span><span class="sxs-lookup"><span data-stu-id="fbf23-127">Additional planning resources</span></span>

<span data-ttu-id="fbf23-128">O tutorial intitulado [Small Business exemplo-configurar um atendedor automático](/microsoftteams/tutorial-org-aa) passa pelo processo de coleta de informações sobre as necessidades do usuário, planejando uma estrutura de atendedores automáticos e usuários (e possivelmente filas de chamadas), gravando os prompts de menu e implementar o plano no centro de administração online.</span><span class="sxs-lookup"><span data-stu-id="fbf23-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="fbf23-129">revisar o tutorial e usar os exercícios não crie seu plano.</span><span class="sxs-lookup"><span data-stu-id="fbf23-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="fbf23-130">Quando você tem uma estrutura sólida que atende às suas necessidades e um script que orienta os clientes com eficiência, prossiga para [Configurar contas de recursos](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="fbf23-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf23-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="fbf23-131">See Also</span></span>

[<span data-ttu-id="fbf23-132">Configurar contas de recurso</span><span class="sxs-lookup"><span data-stu-id="fbf23-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="fbf23-133">Habilitar gravação de prompt personalizado usando a interface do usuário de telefone</span><span class="sxs-lookup"><span data-stu-id="fbf23-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="fbf23-134">O que são atendedores automáticos de nuvem?</span><span class="sxs-lookup"><span data-stu-id="fbf23-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="fbf23-135">Configurar um atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="fbf23-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="fbf23-136">Planejar a conectividade híbrida entre o Skype for Business Server e o Office 365</span><span class="sxs-lookup"><span data-stu-id="fbf23-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="fbf23-137">Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365</span><span class="sxs-lookup"><span data-stu-id="fbf23-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="fbf23-138">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fbf23-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
