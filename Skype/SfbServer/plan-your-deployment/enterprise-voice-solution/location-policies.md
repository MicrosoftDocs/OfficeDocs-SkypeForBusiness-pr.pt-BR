---
title: Planejar políticas de local Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência avançado (E9-1-1) no Skype Business Server Enterprise Voice.
ms.openlocfilehash: 6717d6b7940ccf9cf7de403797d8bd4712f18144
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878018"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="af431-103">Planejar políticas de local Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="af431-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="af431-104">Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência avançado (E9-1-1) no Skype Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="af431-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="af431-105">Skype para Business Server agora oferece suporte a configuração de vários números de emergências para um cliente.</span><span class="sxs-lookup"><span data-stu-id="af431-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="af431-106">Se você deseja configurar vários números de emergências, você deve seguir as informações em [vários números de emergências Skype para Business Server planejar](multiple-emergency-numbers.md) e [Configurar vários números de emergências Skype para negócios](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="af431-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="af431-107">Crie políticas de local usando o Skype para painel de controle corporativos ou usando o cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="af431-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="af431-108">Para obter mais informações, consulte [criar políticas de local no Skype para Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="af431-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="af431-109">Cada política de local contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="af431-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="af431-110">**Habilitar E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="af431-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="af431-111">Quando este valor é habilitado, o cliente está habilitado para os serviços de emergência E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="af431-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="af431-112">Quando um cliente registra, ele tenta adquirir uma localização do serviço de informações de local e incluirá as informações de localização como parte de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="af431-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="af431-113">**Local**</span><span class="sxs-lookup"><span data-stu-id="af431-113">**Location**</span></span>
  
<span data-ttu-id="af431-114">Esta configuração é usada somente quando a opção **Habilitar E9-1-1** está habilitada. </span><span class="sxs-lookup"><span data-stu-id="af431-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="af431-115">Você pode configurar o \*\*Local \*\* para definir o comportamento do cliente, como a seguir:   </span><span class="sxs-lookup"><span data-stu-id="af431-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="af431-116">Definir o valor como **Não** significa que o usuário não receberá uma solicitação de local.</span><span class="sxs-lookup"><span data-stu-id="af431-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="af431-117">Definir o valor como **Sim** significa que o usuário receberá uma solicitação de local, mas poderá ignorá-la.</span><span class="sxs-lookup"><span data-stu-id="af431-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="af431-p104">Definir o valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação de local e um aviso de isenção de responsabilidade caso tente ignorar a solicitação. De qualquer forma, o usuário pode continuar utilizando o cliente.</span><span class="sxs-lookup"><span data-stu-id="af431-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="af431-p105">O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade. </span><span class="sxs-lookup"><span data-stu-id="af431-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="af431-122">**Aviso de Isenção de Responsabilidade do Serviço de Emergência Avançado**</span><span class="sxs-lookup"><span data-stu-id="af431-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="af431-123">Esta configuração especifica o aviso de isenção de responsabilidade que o usuário verá caso ignore a solicitação de local.</span><span class="sxs-lookup"><span data-stu-id="af431-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="af431-124">No Skype para Business Server, você pode usar a política de local para definir avisos de isenção diferentes para diferentes grupos de usuários ou de diferentes localidades.</span><span class="sxs-lookup"><span data-stu-id="af431-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="af431-125">**Cadeia de Discagem de Emergência (número de discagem para E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="af431-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="af431-126">Esta cadeia de caracteres de discagem (menos o prefixo "+", mas incluindo qualquer normalização feita pelo plano de discagem do usuário) significa que uma chamada é uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="af431-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="af431-127">A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="af431-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af431-128">Se sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma correspondente plano de discagem da regra de normalização que adiciona um "+" para a cadeia de caracteres 911 antes de enviar a chamada para o roteamento de saída em um servidor executando o Skype para Business Server; o "+" será colocada automaticamente antes pelo Skype para clientes corporativos como resultado a política de local.</span><span class="sxs-lookup"><span data-stu-id="af431-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="af431-129">No entanto, se o seu site usa um prefixo de acesso externo, você precisará adicionar uma regra de normalização para a política de plano de discagem aplicável que retira o prefixo de acesso externo e adiciona o "+".</span><span class="sxs-lookup"><span data-stu-id="af431-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="af431-130">Por exemplo, se seu local usa um prefixo de acesso externo de 9 e um usuário disca 9 911 para colocar uma chamada de emergência, o cliente usará sua política de plano de discagem normalizar isso para +911 antes que o número discado é avaliado com as rotas no perfil da localidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="af431-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="af431-131">**Máscaras de Cadeia de Discagem de Emergência (máscara de discagem para E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="af431-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="af431-132">Uma-vírgula lista de cadeias de caracteres de discagem que é convertida em **Cadeia de caracteres de discagem de emergência**especificada.</span><span class="sxs-lookup"><span data-stu-id="af431-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="af431-133">Por exemplo, convém adicionar 112, que é o número de serviço de emergência para a maioria dos Europa.</span><span class="sxs-lookup"><span data-stu-id="af431-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="af431-134">Um visitante Skype para o usuário de negócios da Europa talvez não saiba que 911 é o número de emergência EUA, mas eles possam discar 112 e obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="af431-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="af431-135">Conforme com a cadeia de caracteres de discagem de emergência, não incluir um "+" antes de cada número, e se você usar códigos de acesso de linha externa, certifique-se de que há regras de normalização na política de plano de discagem do usuário para retirar desativa o dígito do código de acesso.</span><span class="sxs-lookup"><span data-stu-id="af431-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="af431-136">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="af431-136">**PSTN usage**</span></span>
  
<span data-ttu-id="af431-137">O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="af431-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af431-138">É possível atribuir apenas um Uso a uma política de local.</span><span class="sxs-lookup"><span data-stu-id="af431-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="af431-139">Este uso de PSTN substitui os usos da PSTN atribuídos à política de voz do usuário, mas se aplica somente às chamadas feitas para a cadeia de caracteres de discagem de emergência ou para uma das máscaras de cadeia de caracteres de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="af431-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="af431-140">**URI de notificação**</span><span class="sxs-lookup"><span data-stu-id="af431-140">**Notification URI**</span></span>
  
<span data-ttu-id="af431-p111">Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de IM (Sistema de Mensagens Instantâneas) quando uma chamada de emergência for realizada. Há suporte para grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="af431-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="af431-143">**URI de Conferência**</span><span class="sxs-lookup"><span data-stu-id="af431-143">**Conference URI**</span></span>
  
<span data-ttu-id="af431-144">Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.  </span><span class="sxs-lookup"><span data-stu-id="af431-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="af431-145">**Modo de Conferência**</span><span class="sxs-lookup"><span data-stu-id="af431-145">**Conference Mode**</span></span>
  
<span data-ttu-id="af431-146">Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias. </span><span class="sxs-lookup"><span data-stu-id="af431-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="af431-147">**Intervalo de Atualização de Local**</span><span class="sxs-lookup"><span data-stu-id="af431-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="af431-148">Especifica a quantidade de tempo (em horas) entre as solicitações de cliente para uma atualização local do serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="af431-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="af431-149">O valor pode ser definido para qualquer valor entre 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="af431-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="af431-150">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="af431-150">The default value is 4.</span></span>
  

