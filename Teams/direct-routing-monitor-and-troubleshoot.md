---
title: Monitorar e solucionar problemas de roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Este artigo descreve como monitorar e solucionar problemas de configuração de roteamento direto.
ms.openlocfilehash: 75f116004c0385aa7d13b0173380221304590814
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30350982"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="aad14-103">Monitorar e solucionar problemas de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="aad14-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="aad14-104">Este artigo descreve como monitorar e solucionar problemas de configuração de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="aad14-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="aad14-105">A capacidade de fazer e receber chamadas usando o roteamento direto envolve os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="aad14-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="aad14-106">Controladores de borda de sessão (SBCs)</span><span class="sxs-lookup"><span data-stu-id="aad14-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="aad14-107">Componentes de roteamento diretos no Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="aad14-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="aad14-108">Troncos de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="aad14-108">Telecom trunks</span></span> 

<span data-ttu-id="aad14-109">Se você tiver dificuldades para solução de problemas, abra um caso de suporte com seu fornecedor SBC ou o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aad14-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="aad14-110">Microsoft está trabalhando em fornecer mais ferramentas para o monitoramento e solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="aad14-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="aad14-111">Verifique a documentação periodicamente para atualizações.</span><span class="sxs-lookup"><span data-stu-id="aad14-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="aad14-112">Monitorar a disponibilidade dos controladores de borda de sessão usando mensagens de opções de protocolo de iniciação de sessão (SIP)</span><span class="sxs-lookup"><span data-stu-id="aad14-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="aad14-113">Roteamento direto usa opções SIP enviadas pelos controladores de borda de sessão para monitorar a integridade SBC.</span><span class="sxs-lookup"><span data-stu-id="aad14-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="aad14-114">Não há nenhuma ação necessária do administrador do locatário para habilitar o monitoramento de SIP Options.</span><span class="sxs-lookup"><span data-stu-id="aad14-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="aad14-115">As informações coletadas sejam levadas em consideração quando as decisões de roteamento são feitas.</span><span class="sxs-lookup"><span data-stu-id="aad14-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="aad14-116">Por exemplo, se, para um usuário específico, existem várias SBCs disponíveis para encaminhar uma chamada, roteamento direto considera que as informações de SIP Options recebidas de cada SBC para determinar o roteamento.</span><span class="sxs-lookup"><span data-stu-id="aad14-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="aad14-117">O diagrama a seguir mostra um exemplo da configuração:</span><span class="sxs-lookup"><span data-stu-id="aad14-117">The following diagram shows an example of the configuration:</span></span> 

![Exemplo de configuração de opções de SIP](media/sip-options-config-example.png)

<span data-ttu-id="aad14-119">Quando um usuário faz uma chamada para o número +1 425 \<qualquer digits> sete, roteamento direto avalia a rota.</span><span class="sxs-lookup"><span data-stu-id="aad14-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="aad14-120">Existem dois SBCs na rota: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="aad14-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="aad14-121">Ambos os SBCs possuem prioridade iguais na rota.</span><span class="sxs-lookup"><span data-stu-id="aad14-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="aad14-122">Antes de separação um SBC, o mecanismo de circulação avalia a integridade dos SBCs com base em quando o SBC enviadas as opções de SIP última vez.</span><span class="sxs-lookup"><span data-stu-id="aad14-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="aad14-123">Um SBC é considerado Íntegro se estatísticas no momento do envio de chamada mostra que o SBC envia opções em um intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="aad14-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="aad14-124">Roteamento direto calcula a intervalos regulares de acordo com a média de duas vezes quando o SBC envia opções antes de fazer a chamada e adicionar cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="aad14-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="aad14-125">Por exemplo, suponha que o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aad14-125">For example, assume the following:</span></span> 

- <span data-ttu-id="aad14-126">Um SBC está configurado para enviar opções cada minuto.</span><span class="sxs-lookup"><span data-stu-id="aad14-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="aad14-127">O SBC foi emparelhado às 11.00 AM.</span><span class="sxs-lookup"><span data-stu-id="aad14-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="aad14-128">O SBC envia opções nos 11.01 AM, 11.02 AM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="aad14-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="aad14-129">No 11.15, um usuário faz uma chamada e o mecanismo de circulação seleciona esta SBC.</span><span class="sxs-lookup"><span data-stu-id="aad14-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="aad14-130">A lógica a seguir é aplicada: duas vezes o intervalo de médio quando o SBC envia opções (um minuto mais um minuto = dois minutos) e mais de cinco minutos = sete minutos.</span><span class="sxs-lookup"><span data-stu-id="aad14-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="aad14-131">Esse é o valor do intervalo para o SBC regular.</span><span class="sxs-lookup"><span data-stu-id="aad14-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="aad14-132">Se o SBC em nosso exemplo enviada opções em qualquer período entre 11.08 AM e 11.15 AM (o tempo que a chamada foi feita), ele é considerado íntegro.</span><span class="sxs-lookup"><span data-stu-id="aad14-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="aad14-133">Caso contrário, o SBC vai ser rebaixado da rota.</span><span class="sxs-lookup"><span data-stu-id="aad14-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="aad14-134">Rebaixamento significa que o SBC não será testado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="aad14-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="aad14-135">Por exemplo, temos sbc1.contoso.com e sbc2.contoso.com com prioridade igual.</span><span class="sxs-lookup"><span data-stu-id="aad14-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="aad14-136">Se sbc1.contoso.com não enviar SIP Options em intervalos regulares, conforme descrito acima, ele será rebaixado.</span><span class="sxs-lookup"><span data-stu-id="aad14-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="aad14-137">Em seguida, sbc2.contoso.com tentará para a chamada.</span><span class="sxs-lookup"><span data-stu-id="aad14-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="aad14-138">Se sbc2.contoso.con não é possível entregar a chamada, o sbc1.contoso.com (rebaixado) for testado novamente antes que uma falha seja gerada.</span><span class="sxs-lookup"><span data-stu-id="aad14-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="aad14-139">Monitore os logs SBC e painel de análise de qualidade de chamada</span><span class="sxs-lookup"><span data-stu-id="aad14-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="aad14-140">Em alguns casos, especialmente durante o emparelhamento inicial, pode haver problemas relacionados à configuração incorreta dos SBCs e/ou o serviço de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="aad14-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="aad14-141">Você pode usar as seguintes ferramentas para monitorar sua configuração:</span><span class="sxs-lookup"><span data-stu-id="aad14-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="aad14-142">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="aad14-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="aad14-143">Logs SBC</span><span class="sxs-lookup"><span data-stu-id="aad14-143">SBC logs</span></span> 

<span data-ttu-id="aad14-144">O serviço de roteamento direto tem os códigos de erro de muito descritivo reportados para análise de chamada ou os logs SBC.</span><span class="sxs-lookup"><span data-stu-id="aad14-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="aad14-145">O painel de controle de qualidade de chamada fornece informações sobre a qualidade da chamada e a confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="aad14-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="aad14-146">Para saber mais sobre como solucionar problemas usando a análise de chamada, consulte [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e [Análise de uso chamada solucionar problemas de qualidade de chamadas ruins](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="aad14-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="aad14-147">No caso de falhas de chamada, chamada Analytics fornece códigos SIP padrão para ajudar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="aad14-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Exemplos de código SIP de falha de ligação](media/failed-response-code.png)

<span data-ttu-id="aad14-149">No entanto, chamar Analytics só pode ajudar quando chamadas alcançar os componentes internos do roteamento direto e falharem.</span><span class="sxs-lookup"><span data-stu-id="aad14-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="aad14-150">No caso de problemas com pareamento de SBC ou onde SIP "Convidar" foi rejeitada (por exemplo, o nome do tronco que FQDN foi definida incorretamente), análise de chamada não ajudará.</span><span class="sxs-lookup"><span data-stu-id="aad14-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="aad14-151">Nesse caso, consulte os logs SBC.</span><span class="sxs-lookup"><span data-stu-id="aad14-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="aad14-152">Roteamento direto envia uma descrição detalhada de problemas para os SBCs; Esses problemas podem ser lidas dos logs SBC.</span><span class="sxs-lookup"><span data-stu-id="aad14-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
