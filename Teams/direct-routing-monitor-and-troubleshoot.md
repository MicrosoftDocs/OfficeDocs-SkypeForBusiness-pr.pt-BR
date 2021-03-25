---
title: Monitorar e solucionar problemas do Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como monitorar e solucionar problemas de configuração de Roteamento Direto, incluindo Controladores de Borda de Sessão, Componentes de Roteamento Direto e Troncos de Telecomunicações.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121399"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="6e816-103">Monitorar e solucionar problemas do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="6e816-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="6e816-104">Este artigo descreve como monitorar e solucionar problemas de sua configuração de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="6e816-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="6e816-105">A capacidade de fazer e receber chamadas usando Roteamento Direto envolve os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="6e816-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="6e816-106">Controladores de Borda de Sessão (SBCs)</span><span class="sxs-lookup"><span data-stu-id="6e816-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="6e816-107">Componentes de Roteamento Direto no Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="6e816-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="6e816-108">Troncos de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="6e816-108">Telecom trunks</span></span> 

<span data-ttu-id="6e816-109">Se você tiver dificuldades para solucionar problemas, poderá abrir um caso de suporte com o fornecedor SBC ou a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e816-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="6e816-110">A Microsoft está trabalhando no fornecimento de mais ferramentas para solução de problemas e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="6e816-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="6e816-111">Verifique periodicamente a documentação para atualizações.</span><span class="sxs-lookup"><span data-stu-id="6e816-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="6e816-112">Monitorando a disponibilidade de controladores de borda de sessão usando mensagens de opções SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="6e816-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="6e816-113">O Roteamento Direto usa opções SIP enviadas pelos Controladores de Borda de Sessão para monitorar a saúde do SBC.</span><span class="sxs-lookup"><span data-stu-id="6e816-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="6e816-114">Não há ações necessárias do administrador de locatários para habilitar o monitoramento de opções SIP.</span><span class="sxs-lookup"><span data-stu-id="6e816-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="6e816-115">As informações coletadas são levadas em consideração quando as decisões de roteamento são tomadas.</span><span class="sxs-lookup"><span data-stu-id="6e816-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="6e816-116">Por exemplo, se, para um usuário específico, houver vários SBCs disponíveis para rotear uma chamada, o Roteamento Direto considerará as informações de opções SIP recebidas de cada SBC para determinar o roteamento.</span><span class="sxs-lookup"><span data-stu-id="6e816-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="6e816-117">O diagrama a seguir mostra um exemplo da configuração:</span><span class="sxs-lookup"><span data-stu-id="6e816-117">The following diagram shows an example of the configuration:</span></span> 

![Exemplo de configuração de opções SIP](media/sip-options-config-example.png)

<span data-ttu-id="6e816-119">Quando um usuário faz uma chamada para o número +1 425, \<any seven digits> o Roteamento Direto avalia a rota.</span><span class="sxs-lookup"><span data-stu-id="6e816-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="6e816-120">Há dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6e816-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="6e816-121">Ambos os SBCs têm prioridade igual na rota.</span><span class="sxs-lookup"><span data-stu-id="6e816-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="6e816-122">Antes de escolher um SBC, o mecanismo de roteamento avalia a saúde dos SBCs com base em quando o SBC enviou as opções SIP da última vez.</span><span class="sxs-lookup"><span data-stu-id="6e816-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="6e816-123">Um SBC é considerado saudável se as estatísticas no momento do envio da chamada mostrarem que o SBC envia opções a cada minuto.</span><span class="sxs-lookup"><span data-stu-id="6e816-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="6e816-124">Quando uma chamada é feita, a seguinte lógica se aplica:</span><span class="sxs-lookup"><span data-stu-id="6e816-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="6e816-125">O SBC foi emparelhado às 11:00.</span><span class="sxs-lookup"><span data-stu-id="6e816-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="6e816-126">O SBC envia opções às 11:01, 11:02 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6e816-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="6e816-127">Às 11:15, um usuário faz uma chamada e o mecanismo de roteamento seleciona esse SBC.</span><span class="sxs-lookup"><span data-stu-id="6e816-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="6e816-128">O Roteamento Direto assume as opções de intervalo regular três vezes (o intervalo regular é de um minuto).</span><span class="sxs-lookup"><span data-stu-id="6e816-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="6e816-129">Se as opções foram enviar durante os últimos três minutos, o SBC será considerado saudável.</span><span class="sxs-lookup"><span data-stu-id="6e816-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="6e816-130">Se o SBC no exemplo enviou opções em qualquer período entre 11:12 e 11:15 (a hora em que a chamada foi feita), ela será considerada saudável.</span><span class="sxs-lookup"><span data-stu-id="6e816-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="6e816-131">Caso não seja, o SBC será rebaixado da rota.</span><span class="sxs-lookup"><span data-stu-id="6e816-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="6e816-132">Rebaixamento significa que o SBC não será tentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="6e816-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="6e816-133">Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com prioridade igual.</span><span class="sxs-lookup"><span data-stu-id="6e816-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="6e816-134">Se sbc1.contoso.com não enviar opções SIP em um intervalo regular conforme descrito anteriormente, ele será rebaixado.</span><span class="sxs-lookup"><span data-stu-id="6e816-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="6e816-135">Em seguida, sbc2.contoso.com tenta a chamada.</span><span class="sxs-lookup"><span data-stu-id="6e816-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="6e816-136">Se sbc2.contoso.con não puder entregar a chamada, a sbc1.contoso.com (rebaixada) será tentada novamente antes que uma falha seja gerada.</span><span class="sxs-lookup"><span data-stu-id="6e816-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="6e816-137">Se dois (ou mais) SBCs em uma rota são considerados ínteeis e iguais, Fisher-Yates embaralhar é aplicado para distribuir as chamadas entre os SBCs.</span><span class="sxs-lookup"><span data-stu-id="6e816-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="6e816-138">Monitorar painéis de Análise de Qualidade de Chamadas e logs SBC</span><span class="sxs-lookup"><span data-stu-id="6e816-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="6e816-139">Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados a erros de configuração dos SBCs ou do serviço de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="6e816-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="6e816-140">Você pode usar as seguintes ferramentas para monitorar sua configuração:</span><span class="sxs-lookup"><span data-stu-id="6e816-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="6e816-141">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="6e816-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="6e816-142">Logs SBC</span><span class="sxs-lookup"><span data-stu-id="6e816-142">SBC logs</span></span> 

<span data-ttu-id="6e816-143">O serviço de Roteamento Direto tem códigos de erro muito descritivos relatados ao Call Analytics ou aos logs SBC.</span><span class="sxs-lookup"><span data-stu-id="6e816-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="6e816-144">O Painel de Qualidade de Chamada fornece informações sobre qualidade e confiabilidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="6e816-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="6e816-145">Para saber mais sobre como solucionar problemas usando a Análise de Chamadas, consulte [Acione](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e use o Painel de Qualidade de Chamadas para o Microsoft Teams e o Skype for Business Online e Use a Análise de Chamadas para solucionar problemas de baixa qualidade de [chamada.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="6e816-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="6e816-146">Em caso de falhas de chamada, a Análise de Chamada fornece códigos SIP padrão para ajudá-lo na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="6e816-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Código SIP de exemplo para falha de chamada](media/failed-response-code.png)

<span data-ttu-id="6e816-148">No entanto, o Call Analytics só pode ajudar quando as chamadas chegam aos componentes internos do Roteamento Direto e falham.</span><span class="sxs-lookup"><span data-stu-id="6e816-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="6e816-149">Em caso de problemas com o emparelhamento SBC ou problemas em que SIP "Invite" foi rejeitado (por exemplo, o nome do FQDN do tronco está mal configurado), a Análise de Chamada não ajudará.</span><span class="sxs-lookup"><span data-stu-id="6e816-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="6e816-150">Nesse caso, consulte os logs SBC.</span><span class="sxs-lookup"><span data-stu-id="6e816-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="6e816-151">Roteamento Direto envia uma descrição detalhada de problemas para os SBCs; esses problemas podem ser lidos nos logs SBC.</span><span class="sxs-lookup"><span data-stu-id="6e816-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>