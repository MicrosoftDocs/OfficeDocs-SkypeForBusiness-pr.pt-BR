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
ms.openlocfilehash: 47d53d740af9cb0407b0309d858d4a1a85b3b976
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="bda66-102">Visão geral do monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bda66-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bda66-103">_**Última modificação do tópico:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="bda66-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="bda66-104">No Microsoft Lync Server 2013, o monitoramento é usado para coletar informações de uso e dados de qualidade da experiência (QoE) sobre as sessões de comunicação nas quais seus usuários estão envolvidos.</span><span class="sxs-lookup"><span data-stu-id="bda66-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="bda66-105">Sessão é um termo genérico que abrange uma conexão do usuário com:</span><span class="sxs-lookup"><span data-stu-id="bda66-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="bda66-106">Conferência</span><span class="sxs-lookup"><span data-stu-id="bda66-106">Conference</span></span>

  - <span data-ttu-id="bda66-107">Uma modalidade de conferência (como áudio/vídeo ou compartilhamento de aplicativos)</span><span class="sxs-lookup"><span data-stu-id="bda66-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="bda66-108">Outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio</span><span class="sxs-lookup"><span data-stu-id="bda66-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bda66-109">O Lync Server 2013 mantém controle das informações sobre cada sessão: quem chamou quem; quais pontos de extremidade foram usados na sessão; Quanto tempo foi a sessão por último; Qual era a qualidade percebida da sessão; e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="bda66-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="bda66-110">No entanto, o Lync Server não grava e armazena a chamada propriamente dita.</span><span class="sxs-lookup"><span data-stu-id="bda66-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="bda66-111">Isso também inclui sessões de mensagens instantâneas: embora o Lync Server Registre informações sobre sessões de mensagens instantâneas, ele não mantém um registro de cada mensagem instantânea enviada durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="bda66-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="bda66-112">As informações de detalhes da chamada coletadas pelo Lync Server podem ser empregadas para qualquer número de usos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="bda66-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="bda66-113">**ROI (retorno do investimento)**.</span><span class="sxs-lookup"><span data-stu-id="bda66-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="bda66-114">Os administradores podem comparar os dados de uso coletados pelo Monitoring Server com dados similares coletados pelo sistema de telefonia anterior para mostrar a economia de custos e ajudar a justificar a implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bda66-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="bda66-p104">**Gerenciamento de inventário de dispositivos**. As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos ainda em uso que precisam ser substituídos, bem como dispositivos caros que podem simplesmente não estar sendo usados.</span><span class="sxs-lookup"><span data-stu-id="bda66-p104">**Device Inventory Management**. Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="bda66-117">Assistência técnica.</span><span class="sxs-lookup"><span data-stu-id="bda66-117">Help Desk.</span></span> <span data-ttu-id="bda66-118">Dados sobre solução de problemas permitem que os engenheiros de suporte determinem o motivo da falha de uma chamada do usuário sem a necessidade de coletar logs do cliente ou do servidor.</span><span class="sxs-lookup"><span data-stu-id="bda66-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="bda66-119">Essas informações podem ser prontamente acessadas e compreendidas pela equipe de suporte que não têm um conhecimento técnico profundo do Microsoft Lync 2013 e do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bda66-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="bda66-p106">**Solução de problemas de sistemas**. Permite que os administradores detectem problemas graves que podem impedir que os usuários executem tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="bda66-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="bda66-122">Além dessas informações básicas de chamada, o Monitoring Server também fornece um mecanismo que permite que os pontos de extremidade SIP (como o Lync 2013) forneçam informações de solução de problemas às quais o servidor não teria acesso:</span><span class="sxs-lookup"><span data-stu-id="bda66-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="bda66-p107">**Métricas de mídia que influenciam a qualidade**. Essas métricas lidam com a transmissão da chamada propriamente dita, ou seja, elas fornecem um log de trajeto à medida que a chamada passa pela rede. Essas métricas, que incluem itens como perda de pacotes, tremulação e tempo entre saída e chegada, fornecem informações sobre o que aconteceu com a chamada do momento em que ela saiu do seu ponto de extremidade até o momento em que chegou ao ponto de extremidade do outro usuário.</span><span class="sxs-lookup"><span data-stu-id="bda66-p107">**Media Metrics that Impact Quality**. These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network. These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="bda66-126">**Problemas comunicados ao usuário final**.</span><span class="sxs-lookup"><span data-stu-id="bda66-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="bda66-127">Essas métricas incluem notificações de baixa qualidade que o Lync 2013 apresenta aos usuários finais em casos em que eles estão muito distantes de um microfone, falando muito simples, têm uma conexão de rede ruim ou estão tendo uma qualidade ruim porque outro programa no computador é consumo dos recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bda66-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="bda66-p109">**Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.</span><span class="sxs-lookup"><span data-stu-id="bda66-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="bda66-p110">No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações automaticamente para o servidor front-end que intermediou a chamada. Não é necessária nenhuma ação manual para que os pontos de extremidade transmitam essas informações, pois essa função já é incorporada ao protocolo SIP. No entanto, se você desejar coletar e armazenar essas informações, precisará instalar e habilitar o monitoramento. Se fizer isso, as informações sobre as chamadas serão coletadas pelos agentes em execução no servidor front-end e transmitidas para um par de bancos de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bda66-p110">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call. You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol. However, if you want to collect and store that information, then you need to install and enable monitoring. If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="bda66-134">Observe que o processo de instalação e configuração do monitoramento foi simplificado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bda66-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="bda66-135">Em versões anteriores do software, o monitoramento exigia uma função de Servidor de Monitoramento separada, ou seja, era necessário reservar um computador separado para ser usado como o Servidor de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bda66-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="bda66-136">No Lync Server 2013, no entanto, a função de servidor de monitoramento foi eliminada.</span><span class="sxs-lookup"><span data-stu-id="bda66-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="bda66-137">Em vez disso, o serviço de monitoramento (no formato de "agentes de coleta de dados unificados") foi incorporado a todos os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="bda66-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="bda66-138">Isso traz pelo menos dois benefícios importantes.</span><span class="sxs-lookup"><span data-stu-id="bda66-138">This has at least two major benefits.</span></span> <span data-ttu-id="bda66-139">A incorporação do serviço de monitoramento:</span><span class="sxs-lookup"><span data-stu-id="bda66-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="bda66-140">Diminui o número de funções de servidor necessárias ao implementar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bda66-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="bda66-141">A redução de função de Servidor de Monitoramento também ajuda a reduzir os custos, pois elimina a necessidade de manter servidores dedicados para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bda66-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="bda66-142">Reduz a complexidade da instalação e administração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bda66-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="bda66-143">Ao integrar os serviços de monitoramento a cada servidor front-end, não é mais necessário instalar, configurar e gerenciar a função do Servidor de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bda66-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="bda66-144">Para obter mais informações, consulte o tópico [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) no lync Server 2013 2013 Deployment Guide.</span><span class="sxs-lookup"><span data-stu-id="bda66-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

