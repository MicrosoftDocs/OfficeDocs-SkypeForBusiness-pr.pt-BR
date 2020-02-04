---
title: 'Lync Server 2013: visão geral do monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="9a8aa-102">Visão geral do monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a8aa-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a8aa-103">_**Tópico da última modificação:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="9a8aa-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="9a8aa-104">No Microsoft Lync Server 2013, o monitoramento é usado para coletar dados de uso e dados de qualidade da experiência (QoE) sobre as sessões de comunicação nas quais seus usuários participam.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="9a8aa-105">Uma sessão é um termo genérico que abrange a conexão de um usuário a:</span><span class="sxs-lookup"><span data-stu-id="9a8aa-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="9a8aa-106">Conferência</span><span class="sxs-lookup"><span data-stu-id="9a8aa-106">Conference</span></span>

  - <span data-ttu-id="9a8aa-107">Modalidade de conferência (como áudio/vídeo ou compartilhamento de aplicativos)</span><span class="sxs-lookup"><span data-stu-id="9a8aa-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="9a8aa-108">um outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio</span><span class="sxs-lookup"><span data-stu-id="9a8aa-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a8aa-109">O Lync Server 2013 controla as informações sobre cada sessão: quem chamou quem; quais pontos de extremidade foram usados na sessão; Qual foi a duração da sessão por último; Qual foi a qualidade percebida da sessão; e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="9a8aa-110">No entanto, o Lync Server não grava e armazena a chamada propriamente dita.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="9a8aa-111">Isso também inclui sessões de mensagens instantâneas: embora o Lync Server Registre informações sobre sessões de mensagens instantâneas, ele não mantém um registro de cada mensagem instantânea enviada durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="9a8aa-112">As informações de detalhes de chamadas coletadas pelo Lync Server podem ser empregadas para qualquer número de usos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="9a8aa-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="9a8aa-113">**Retorno sobre o investimento (ROI)**.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="9a8aa-114">Os administradores podem comparar os dados de uso coletados pelo Monitoring Server com dados similares coletados para o sistema de telefonia anterior a fim de mostrar a redução de custos e ajudar a justificar a implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="9a8aa-115">**Gerenciamento de estoque de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-115">**Device Inventory Management**.</span></span> <span data-ttu-id="9a8aa-116">As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos que ainda estão em uso que precisam ser substituídos, além de identificar dispositivos caros que não parecem estar sendo usados.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="9a8aa-117">Suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-117">Help Desk.</span></span> <span data-ttu-id="9a8aa-118">A solução de problemas de dados permite aos engenheiros de suporte determinar por que a chamada de um usuário falhou e fazer isso sem precisar coletar os logs do lado do servidor ou do cliente.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="9a8aa-119">Essas informações podem ser acessadas de forma imediata e compreendidas pela equipe de suporte que não tenha conhecimento técnico profundo do Microsoft Lync 2013 e do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="9a8aa-p106">**Solução de problemas de sistemas**. Habilita os administradores a detectar problemas graves que podem impedir os usuários de executar tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="9a8aa-122">Além dessas informações básicas de chamadas, o Monitoring Server também fornece um mecanismo que permite que pontos de extremidade SIP (como o Lync 2013) forneçam informações de solução de problemas que o servidor não teria, de outra forma, ter acesso a:</span><span class="sxs-lookup"><span data-stu-id="9a8aa-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="9a8aa-123">**Métricas de mídia que influenciam a qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="9a8aa-124">Essas métricas lidam com a transmissão real da chamada em si; ou seja, eles fornecem um tipo de registro de viagens como viagem de chamadas pela rede.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="9a8aa-125">Essas métricas (que incluem itens como perda de pacotes, tremulação e tempos de viagem de ida e volta) fornecem informações sobre o que aconteceu com a chamada no momento em que ele saiu do ponto de extremidade até o momento em que chegou ao ponto de extremidade da outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="9a8aa-126">**Problemas comunicados ao usuário final**.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="9a8aa-127">Essas métricas incluem notificações de baixa qualidade que o Lync 2013 apresenta aos usuários finais em casos onde eles estão longe de um microfone, falando muito sem problemas, com uma conexão de rede ruim ou com baixa qualidade porque outro programa no computador é consumindo os recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="9a8aa-p109">**Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="9a8aa-130">No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações automaticamente para o servidor front-end que facilitou a chamada.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="9a8aa-131">Não é necessária nenhuma ação para que os pontos de extremidade transmitam essas informações, pois esse comportamento já está incorporado ao protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="9a8aa-132">No entanto, se desejar coletar e armazenar essas informações, você precisará instalar e habilitar o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="9a8aa-133">Se fizer isso, as informações das chamadas serão coletadas pelos agentes em execução no Servidor Front-End e transmitidas para um par de bancos de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="9a8aa-134">Observe que o processo de instalação e configuração do monitoramento foi simplificado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="9a8aa-135">Em versões anteriores do software, o monitoramento exigia uma função de servidor de monitoramento separada, que normalmente significa que um computador separado reservava para uso como o servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="9a8aa-136">No Lync Server 2013, no entanto, a função de servidor de monitoramento foi eliminada.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="9a8aa-137">Em vez disso, o serviço de monitoramento (na forma de "agentes da coleta de dados unificados") foi posicionado em todos os servidores de front-end.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="9a8aa-138">Isso tem pelo menos dois benefícios importantes.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-138">This has at least two major benefits.</span></span> <span data-ttu-id="9a8aa-139">Colocação do serviço de monitoramento:</span><span class="sxs-lookup"><span data-stu-id="9a8aa-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="9a8aa-140">Diminui o número de funções de servidor necessárias ao implementar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="9a8aa-141">Decrementar a função de servidor de monitoramento também ajuda a reduzir os custos, eliminando a necessidade de manter servidores dedicados para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="9a8aa-142">Reduz a complexidade da configuração e administração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="9a8aa-143">Posicionando os serviços de monitoramento em cada servidor front-end que você não precisa mais instalar, configurar e gerenciar a função do servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="9a8aa-144">Para obter mais informações, consulte o tópico [implantando o monitoramento no Lync server 2013](lync-server-2013-deploying-monitoring.md) no guia de implantação do lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="9a8aa-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

