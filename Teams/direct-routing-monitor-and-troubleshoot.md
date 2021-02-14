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
description: Saiba como monitorar e solucionar problemas de configuração de Roteamento Direto, incluindo Controladores de Borda de Sessão, componentes de Roteamento Direto e troncos de Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901906"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="71ef8-103">Monitorar e solucionar problemas do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="71ef8-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="71ef8-104">Este artigo descreve como monitorar e solucionar problemas de sua configuração de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="71ef8-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="71ef8-105">A capacidade de fazer e receber chamadas usando o Roteamento Direto envolve os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="71ef8-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="71ef8-106">Controladores de Borda de Sessão (SBCs)</span><span class="sxs-lookup"><span data-stu-id="71ef8-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="71ef8-107">Componentes de Roteamento Direto no Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="71ef8-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="71ef8-108">Troncos de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="71ef8-108">Telecom trunks</span></span> 

<span data-ttu-id="71ef8-109">Se você tiver dificuldades para solucionar problemas, poderá abrir um caso de suporte com seu fornecedor SBC ou a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71ef8-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="71ef8-110">A Microsoft está trabalhando para fornecer mais ferramentas para solução de problemas e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="71ef8-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="71ef8-111">Verifique periodicamente a documentação para ver se há atualizações.</span><span class="sxs-lookup"><span data-stu-id="71ef8-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="71ef8-112">Monitorar a disponibilidade dos Controladores de Borda de Sessão usando mensagens de opções do PROTOCOLO</span><span class="sxs-lookup"><span data-stu-id="71ef8-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="71ef8-113">O Roteamento Direto usa as opções SIP enviadas pelos Controladores de Borda de Sessão para monitorar a saúde do SBC.</span><span class="sxs-lookup"><span data-stu-id="71ef8-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="71ef8-114">Não são necessárias ações do administrador do locatário para habilitar o monitoramento de opções SIP.</span><span class="sxs-lookup"><span data-stu-id="71ef8-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="71ef8-115">As informações coletadas são consideradas quando as decisões de roteamento são tomadas.</span><span class="sxs-lookup"><span data-stu-id="71ef8-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="71ef8-116">Por exemplo, se, para um usuário específico, houver vários SBCs disponíveis para rotear uma chamada, o Roteamento Direto considerará as informações de opções SIP recebidas de cada SBC para determinar o roteamento.</span><span class="sxs-lookup"><span data-stu-id="71ef8-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="71ef8-117">O diagrama a seguir mostra um exemplo da configuração:</span><span class="sxs-lookup"><span data-stu-id="71ef8-117">The following diagram shows an example of the configuration:</span></span> 

![Exemplo de configuração de opções SIP](media/sip-options-config-example.png)

<span data-ttu-id="71ef8-119">Quando um usuário faz uma chamada para o número +1 425 a qualquer>, o Roteamento \< Direto avalia a rota.</span><span class="sxs-lookup"><span data-stu-id="71ef8-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="71ef8-120">Há dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="71ef8-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="71ef8-121">Ambos os SBCs têm prioridade igual na rota.</span><span class="sxs-lookup"><span data-stu-id="71ef8-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="71ef8-122">Antes de escolher um SBC, o mecanismo de roteamento avalia a saúde dos SBCs com base em quando o SBC enviou as opções SIP da última vez.</span><span class="sxs-lookup"><span data-stu-id="71ef8-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="71ef8-123">Um SBC será considerado saudável se as estatísticas no momento do envio da chamada mostrarem que o SBC envia opções a cada minuto.</span><span class="sxs-lookup"><span data-stu-id="71ef8-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="71ef8-124">Quando uma chamada é feita, aplica-se a seguinte lógica:</span><span class="sxs-lookup"><span data-stu-id="71ef8-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="71ef8-125">O SBC foi emparelhado às 11:00.</span><span class="sxs-lookup"><span data-stu-id="71ef8-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="71ef8-126">O SBC envia opções às 11:01, 11:02 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="71ef8-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="71ef8-127">Às 11:15, um usuário faz uma chamada e o mecanismo de roteamento seleciona esse SBC.</span><span class="sxs-lookup"><span data-stu-id="71ef8-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="71ef8-128">O Roteamento Direto assume as opções de intervalo regular três vezes (o intervalo regular é de um minuto).</span><span class="sxs-lookup"><span data-stu-id="71ef8-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="71ef8-129">Se as opções foram enviar durante os últimos três minutos, o SBC será considerado saudável.</span><span class="sxs-lookup"><span data-stu-id="71ef8-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="71ef8-130">Se o SBC nas opções de exemplo enviadas em qualquer período entre 11:12 e 11:15 (hora em que a chamada foi feita), ela será considerada saudável.</span><span class="sxs-lookup"><span data-stu-id="71ef8-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="71ef8-131">Caso não, o SBC será rebaixado da rota.</span><span class="sxs-lookup"><span data-stu-id="71ef8-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="71ef8-132">Desmoção significa que o SBC não será tentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="71ef8-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="71ef8-133">Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com igual prioridade.</span><span class="sxs-lookup"><span data-stu-id="71ef8-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="71ef8-134">Se sbc1.contoso.com não enviar opções SIP em um intervalo regular conforme descrito anteriormente, ele será rebaixado.</span><span class="sxs-lookup"><span data-stu-id="71ef8-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="71ef8-135">Em seguida, sbc2.contoso.com tenta a chamada.</span><span class="sxs-lookup"><span data-stu-id="71ef8-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="71ef8-136">Se sbc2.contoso.con não conseguir entregar a chamada, a sbc1.contoso.com (rebaixada) será tentada novamente antes que uma falha seja gerada.</span><span class="sxs-lookup"><span data-stu-id="71ef8-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="71ef8-137">Se dois (ou mais) SBCs em uma rota são considerados saudáveis e iguais, a Fisher-Yates aleatória é aplicada para distribuir as chamadas entre os SBCs.</span><span class="sxs-lookup"><span data-stu-id="71ef8-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="71ef8-138">Monitorar o painel análise de qualidade de chamada e logs SBC</span><span class="sxs-lookup"><span data-stu-id="71ef8-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="71ef8-139">Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados a erros de configuração dos SBCs ou do serviço de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="71ef8-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="71ef8-140">Você pode usar as seguintes ferramentas para monitorar sua configuração:</span><span class="sxs-lookup"><span data-stu-id="71ef8-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="71ef8-141">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="71ef8-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="71ef8-142">Logs SBC</span><span class="sxs-lookup"><span data-stu-id="71ef8-142">SBC logs</span></span> 

<span data-ttu-id="71ef8-143">O serviço roteamento direto tem códigos de erro muito descritivos relatados à Análise de Chamadas ou aos logs SBC.</span><span class="sxs-lookup"><span data-stu-id="71ef8-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="71ef8-144">O Painel de Qualidade da Chamada fornece informações sobre qualidade e confiabilidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="71ef8-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="71ef8-145">Para saber mais sobre como solucionar problemas usando o Recurso de Análise de Chamadas, consulte Como ligar e usar o Painel de Qualidade de Chamada do Microsoft Teams e do [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e usar a Análise de Chamadas para solucionar problemas de baixa qualidade de [chamadas.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="71ef8-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="71ef8-146">Em caso de falhas de chamada, a Análise de Chamada fornece códigos SIP padrão para ajudá-lo na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="71ef8-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Exemplo de código SIP para falha de chamada](media/failed-response-code.png)

<span data-ttu-id="71ef8-148">No entanto, a Análise de Chamadas só pode ajudar quando as chamadas atingem os componentes internos do Roteamento Direto e falham.</span><span class="sxs-lookup"><span data-stu-id="71ef8-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="71ef8-149">Em caso de problemas com o emparelhamento SBC ou problemas em que o "Convite" SIP foi rejeitado (por exemplo, o nome do FQDN do tronco está configurado indefigurado), a Análise de Chamada não ajudará.</span><span class="sxs-lookup"><span data-stu-id="71ef8-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="71ef8-150">Nesse caso, consulte os logs SBC.</span><span class="sxs-lookup"><span data-stu-id="71ef8-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="71ef8-151">O Roteamento Direto envia uma descrição detalhada dos problemas para os SBCs; esses problemas podem ser lidos nos logs SBC.</span><span class="sxs-lookup"><span data-stu-id="71ef8-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
