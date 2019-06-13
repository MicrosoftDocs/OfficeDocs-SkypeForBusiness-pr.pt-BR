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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Este artigo descreve como monitorar e solucionar problemas de configuração de roteamento direto.
ms.openlocfilehash: eeae12aafba87d9af210138f546ed82b12acbbd7
ms.sourcegitcommit: 1a768e470a9509139eeb24034def12630acb7914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "34915152"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="11a18-103">Monitorar e solucionar problemas do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="11a18-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="11a18-104">Este artigo descreve como monitorar e solucionar problemas de configuração de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="11a18-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="11a18-105">A capacidade de fazer e receber chamadas usando o roteamento direto envolve os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="11a18-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="11a18-106">Controladores de borda de sessão (SBCs)</span><span class="sxs-lookup"><span data-stu-id="11a18-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="11a18-107">Componentes de roteamento direto no Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="11a18-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="11a18-108">Troncos de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="11a18-108">Telecom trunks</span></span> 

<span data-ttu-id="11a18-109">Se você tiver dificuldades para solucionar problemas, abra um caso de suporte com o fornecedor do SBC ou a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11a18-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="11a18-110">A Microsoft está trabalhando para fornecer mais ferramentas para solução de problemas e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="11a18-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="11a18-111">Verifique a documentação em busca de atualizações periodicamente.</span><span class="sxs-lookup"><span data-stu-id="11a18-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="11a18-112">Monitorando a disponibilidade de controladores de borda de sessão usando mensagens de opções do protocolo de início de sessão (SIP)</span><span class="sxs-lookup"><span data-stu-id="11a18-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="11a18-113">O roteamento direto usa as opções de SIP enviadas pelos controladores de borda da sessão para monitorar a integridade do SBC.</span><span class="sxs-lookup"><span data-stu-id="11a18-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="11a18-114">Não há nenhuma ação necessária do administrador do locatário para habilitar o monitoramento de opções SIP.</span><span class="sxs-lookup"><span data-stu-id="11a18-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="11a18-115">As informações coletadas são levadas em consideração quando são feitas decisões de roteamento.</span><span class="sxs-lookup"><span data-stu-id="11a18-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="11a18-116">Por exemplo, se, para um usuário específico, há vários SBCs disponíveis para direcionar uma chamada, o roteamento direto considera as informações de opções SIP recebidas de cada SBC para determinar o roteamento.</span><span class="sxs-lookup"><span data-stu-id="11a18-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="11a18-117">O diagrama a seguir mostra um exemplo da configuração:</span><span class="sxs-lookup"><span data-stu-id="11a18-117">The following diagram shows an example of the configuration:</span></span> 

![Exemplo de configuração de opções SIP](media/sip-options-config-example.png)

<span data-ttu-id="11a18-119">Quando um usuário faz uma chamada para número + 1 425 \<quaisquer sete dígitos>, o roteamento direto avalia a rota.</span><span class="sxs-lookup"><span data-stu-id="11a18-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="11a18-120">Há dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="11a18-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="11a18-121">O SBCs tem prioridade igual na rota.</span><span class="sxs-lookup"><span data-stu-id="11a18-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="11a18-122">Antes de escolher um SBC, o mecanismo de roteamento avalia a integridade do SBCs com base em quando o SBC enviou as opções de SIP pela última vez.</span><span class="sxs-lookup"><span data-stu-id="11a18-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="11a18-123">Um SBC é considerado Íntegro se as estatísticas no momento de enviar a chamada mostrarem que o SBC envia opções em um intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="11a18-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="11a18-124">O roteamento direto calcula intervalos regulares levando duas vezes a média quando o SBC envia opções antes de fazer a chamada e adicionar cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="11a18-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="11a18-125">Por exemplo, assuma o seguinte:</span><span class="sxs-lookup"><span data-stu-id="11a18-125">For example, assume the following:</span></span> 

- <span data-ttu-id="11a18-126">Um SBC está configurado para enviar as opções a cada minuto.</span><span class="sxs-lookup"><span data-stu-id="11a18-126">An SBC is configured to send options every minute.</span></span> 
- <span data-ttu-id="11a18-127">O SBC foi emparelhado em 11, 0 AM.</span><span class="sxs-lookup"><span data-stu-id="11a18-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="11a18-128">O SBC envia opções em 11, 1 AM, 11, 2 AM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="11a18-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="11a18-129">Em 11,15, um usuário faz uma chamada e o mecanismo de roteamento seleciona esse SBC.</span><span class="sxs-lookup"><span data-stu-id="11a18-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="11a18-130">A seguinte lógica é aplicada: duas vezes o intervalo médio quando o SBC envia opções (um minuto mais um minuto = dois minutos) mais cinco minutos = sete minutos.</span><span class="sxs-lookup"><span data-stu-id="11a18-130">The following logic is applied: Two times the average interval when the SBC sends options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="11a18-131">Esse é o valor do intervalo regular para o SBC.</span><span class="sxs-lookup"><span data-stu-id="11a18-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="11a18-132">Se o SBC em nosso exemplo enviou opções em qualquer período entre 11, 8 AM e 11,15 AM (o tempo em que a chamada foi feita), ele é considerado íntegro.</span><span class="sxs-lookup"><span data-stu-id="11a18-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="11a18-133">Caso contrário, o SBC será rebaixado da rota.</span><span class="sxs-lookup"><span data-stu-id="11a18-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="11a18-134">O rebaixamento significa que o SBC não será tentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="11a18-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="11a18-135">Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com prioridade igual.</span><span class="sxs-lookup"><span data-stu-id="11a18-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="11a18-136">Se o sbc1.contoso.com não enviar opções de SIP em um intervalo regular, conforme descrito acima, ele será rebaixado.</span><span class="sxs-lookup"><span data-stu-id="11a18-136">If sbc1.contoso.com does not send SIP options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="11a18-137">Em seguida, sbc2.contoso.com tenta fazer a chamada.</span><span class="sxs-lookup"><span data-stu-id="11a18-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="11a18-138">Se sbc2. contoso. con não puder enviar a chamada, o sbc1.contoso.com (rebaixado) será tentado novamente antes de uma falha ser gerada.</span><span class="sxs-lookup"><span data-stu-id="11a18-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="11a18-139">Monitorar o painel de análise de qualidade de chamada e os logs SBC</span><span class="sxs-lookup"><span data-stu-id="11a18-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="11a18-140">Em alguns casos, especialmente durante o emparelhamento inicial, podem haver problemas relacionados à configuração incorreta do SBCs e/ou do serviço de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="11a18-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="11a18-141">Você pode usar as seguintes ferramentas para monitorar a configuração:</span><span class="sxs-lookup"><span data-stu-id="11a18-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="11a18-142">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="11a18-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="11a18-143">Logs SBC</span><span class="sxs-lookup"><span data-stu-id="11a18-143">SBC logs</span></span> 

<span data-ttu-id="11a18-144">O serviço de roteamento direto tem códigos de erro muito descritivos relatados para os logs de análise de chamada ou de SBC.</span><span class="sxs-lookup"><span data-stu-id="11a18-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="11a18-145">O painel de qualidade de chamada fornece informações sobre a qualidade da chamada e a confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="11a18-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="11a18-146">Para saber mais sobre como solucionar problemas usando a análise de chamadas, consulte [ativar e usar o painel de qualidade de chamada para Microsoft Teams e Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e [usar a análise de chamadas para solucionar problemas de qualidade de chamada deficiente](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="11a18-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="11a18-147">Em caso de falhas de chamadas, o recurso de análise de chamadas fornece códigos SIP padrão para ajudá-lo a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="11a18-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Exemplo de código SIP para falha na chamada](media/failed-response-code.png)

<span data-ttu-id="11a18-149">No entanto, a análise de chamadas só pode ajudar quando chamadas chegam aos componentes internos de roteamento direto e falham.</span><span class="sxs-lookup"><span data-stu-id="11a18-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="11a18-150">Em caso de problemas com emparelhamento de SBC ou problemas nos quais o SIP "INVITE" foi recusado (por exemplo, o nome do FQDN do tronco está configurado incorretamente), a análise de chamadas não ajuda.</span><span class="sxs-lookup"><span data-stu-id="11a18-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="11a18-151">Nesse caso, confira os logs SBC.</span><span class="sxs-lookup"><span data-stu-id="11a18-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="11a18-152">O roteamento direto envia uma descrição detalhada de problemas para o SBCs; esses problemas podem ser lidos nos logs SBC.</span><span class="sxs-lookup"><span data-stu-id="11a18-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
