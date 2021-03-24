---
title: Planejar políticas de localização para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência aprimorados (E9-1-1) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101447"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="2aea1-103">Planejar políticas de localização para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2aea1-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="2aea1-104">Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência aprimorados (E9-1-1) no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2aea1-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2aea1-105">O Skype for Business Server agora dá suporte à configuração de vários números de emergência para um cliente.</span><span class="sxs-lookup"><span data-stu-id="2aea1-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="2aea1-106">Se você quiser configurar vários números de emergência, siga as informações em Plan for multiple [emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) e Configure multiple emergency numbers in Skype for [Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="2aea1-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="2aea1-107">Crie políticas de local usando o Painel de Controle do Skype for Business ou usando o cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2aea1-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="2aea1-108">Para obter mais informações, consulte [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2aea1-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="2aea1-109">Cada política de local contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="2aea1-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="2aea1-110">**Habilitar o 9-1-1 aprimorado**</span><span class="sxs-lookup"><span data-stu-id="2aea1-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="2aea1-111">Quando esse valor é habilitado, o cliente é habilitado para serviços de emergência aprimorados (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="2aea1-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="2aea1-112">Quando um cliente se registra, ele tenta adquirir um local do serviço de Informações de Local e incluirá as informações de local como parte de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="2aea1-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="2aea1-113">**Localização**</span><span class="sxs-lookup"><span data-stu-id="2aea1-113">**Location**</span></span>
  
<span data-ttu-id="2aea1-114">Essa configuração é usada somente quando **Enable Enhanced 9-1-1** está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2aea1-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="2aea1-115">Você pode configurar a **configuração Local** para definir o comportamento do cliente da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="2aea1-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="2aea1-116">A definição do valor como **Não** significa que o usuário não receberá uma solicitação de local.</span><span class="sxs-lookup"><span data-stu-id="2aea1-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="2aea1-117">A definição do valor como **Sim** significa que o usuário receberá uma solicitação por um local, mas poderá ignorar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="2aea1-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="2aea1-118">A definição do valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação por um local e mostrará um aviso de isenção de responsabilidade caso ele tente ignorar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="2aea1-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="2aea1-119">Em todos os casos, o usuário pode continuar a usar o cliente.</span><span class="sxs-lookup"><span data-stu-id="2aea1-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2aea1-p105">O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="2aea1-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="2aea1-122">**Isenção de Responsabilidade do Serviço de Emergência Avançado**</span><span class="sxs-lookup"><span data-stu-id="2aea1-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="2aea1-123">Esta configuração especifica o aviso de isenção que o usuário ver se ignorar o aviso em um local.</span><span class="sxs-lookup"><span data-stu-id="2aea1-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="2aea1-124">No Skype for Business Server, você pode usar a política de local para definir avisos de isenção de responsabilidade diferentes para localidades diferentes ou conjuntos diferentes de usuários.</span><span class="sxs-lookup"><span data-stu-id="2aea1-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="2aea1-125">**Cadeia de caracteres de discagem de emergência (número de discagem E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="2aea1-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="2aea1-126">Essa cadeia de caracteres de discagem (menos o "+" principal, mas incluindo qualquer normalização feita pelo Plano de Discagem do usuário) significa que uma chamada é uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="2aea1-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="2aea1-127">A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="2aea1-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2aea1-128">Se sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma regra de normalização correspondente do Plano de Discagem que adiciona um "+" à cadeia de caracteres 911 antes de enviar a chamada para Roteamento de Saída em um servidor executando o Skype for Business Server; o "+" será automaticamente prependido pelo cliente skype for Business como resultado da política de local.</span><span class="sxs-lookup"><span data-stu-id="2aea1-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="2aea1-129">No entanto, se seu site usar um prefixo de acesso externo, você precisará adicionar uma regra de normalização à política de Plano de Discagem aplicável que desmarque o prefixo de acesso externo e adicione o "+".</span><span class="sxs-lookup"><span data-stu-id="2aea1-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="2aea1-130">Por exemplo, se sua localização usa um prefixo de acesso externo 9 e um usuário disca 9 911 para fazer uma chamada de emergência, o cliente usará sua política de Plano de Discagem para normalizar isso para +911 antes que o número discado seja avaliado pelas rotas no perfil de localização do chamador.</span><span class="sxs-lookup"><span data-stu-id="2aea1-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="2aea1-131">**Máscaras de cadeia de caracteres de discagem de emergência (máscara de discagem E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="2aea1-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="2aea1-132">Uma lista separada por ponto e vírgula de sequências de discagem a serem traduzidas para a **Sequência de discagem de emergência**.</span><span class="sxs-lookup"><span data-stu-id="2aea1-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="2aea1-133">Por exemplo, você pode querer adicionar 112, que é o número do serviço de emergência em grande parte da Europa.</span><span class="sxs-lookup"><span data-stu-id="2aea1-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="2aea1-134">Um usuário do Skype for Business visitante da Europa pode não saber que o 911 é o número de emergência dos EUA, mas pode discar 112 e obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="2aea1-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="2aea1-135">Como acontece com a Cadeia de Caracteres de Discagem de Emergência, não inclua um "+" antes de cada número e, se você usar códigos de acesso de linha externa, certifique-se de que há regras de normalização na política de Plano de Discagem do usuário para desagrecar o dígito do código de acesso.</span><span class="sxs-lookup"><span data-stu-id="2aea1-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="2aea1-136">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="2aea1-136">**PSTN usage**</span></span>
  
<span data-ttu-id="2aea1-137">O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="2aea1-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2aea1-138">É possível atribuir apenas um Uso a uma política de local.</span><span class="sxs-lookup"><span data-stu-id="2aea1-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="2aea1-139">Esse Uso de PSTN substitui os Usos PSTN atribuídos à política de voz do usuário, mas se aplica apenas a chamadas feitas à Cadeia de Caracteres de Discagem de Emergência ou a uma das Máscaras de Cadeia de Caracteres de Discagem de Emergência.</span><span class="sxs-lookup"><span data-stu-id="2aea1-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="2aea1-140">**URI de notificação**</span><span class="sxs-lookup"><span data-stu-id="2aea1-140">**Notification URI**</span></span>
  
<span data-ttu-id="2aea1-p111">Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de mensagem instantânea (IM) quando uma chamada de emergência for realizada. Os grupos de distribuição são suportados.</span><span class="sxs-lookup"><span data-stu-id="2aea1-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="2aea1-143">**URI de conferência**</span><span class="sxs-lookup"><span data-stu-id="2aea1-143">**Conference URI**</span></span>
  
<span data-ttu-id="2aea1-144">Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="2aea1-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="2aea1-145">**Modo de conferência**</span><span class="sxs-lookup"><span data-stu-id="2aea1-145">**Conference Mode**</span></span>
  
<span data-ttu-id="2aea1-146">Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias.</span><span class="sxs-lookup"><span data-stu-id="2aea1-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="2aea1-147">**Intervalo de atualização de local**</span><span class="sxs-lookup"><span data-stu-id="2aea1-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="2aea1-148">Especifica a quantidade de tempo (em horas) entre as solicitações do cliente para uma atualização de local do serviço de Informações de Local.</span><span class="sxs-lookup"><span data-stu-id="2aea1-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="2aea1-149">O valor pode ser definido para qualquer valor entre 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="2aea1-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="2aea1-150">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="2aea1-150">The default value is 4.</span></span>
