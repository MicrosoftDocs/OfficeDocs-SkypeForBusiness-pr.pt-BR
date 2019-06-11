---
title: 'Lync Server 2013: Validando a configuração do servidor do Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="17f11-102">Validando a configuração do servidor do Office Web Apps no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17f11-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17f11-103">_**Tópico da última modificação:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="17f11-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="17f11-104">Após a publicação do Office Web Apps Server na topologia e após a publicação da topologia, você verá dois novos eventos do log de eventos no log de eventos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17f11-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="17f11-105">Primeiro, um evento LS Data MCU (ID 41034) deve ser adicionado; esse evento relatará que o Servidor do Office Web Apps foi descoberto:</span><span class="sxs-lookup"><span data-stu-id="17f11-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="17f11-106">**O Servidor do Office Web Apps do servidor de webconferência foi descoberto, o conteúdo do PowerPoint está habilitado.**</span><span class="sxs-lookup"><span data-stu-id="17f11-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="17f11-p102">Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:</span><span class="sxs-lookup"><span data-stu-id="17f11-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="17f11-109">**Descoberta bem-sucedida do Servidor do Office Web Apps dp Servidor de Conferência da Web.**</span><span class="sxs-lookup"><span data-stu-id="17f11-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="17f11-110">**Página do apresentador interno do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="17f11-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="17f11-111">**Página de participantes do servidor do Office Web Apps Server Internal:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="17f11-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="17f11-112">**Página do apresentador externo do Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="17f11-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="17f11-113">**Página de participantes do servidor do Office Web Apps Server Internal:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="17f11-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="17f11-114">Se você vir um evento de MCU de dados LS com a ID do evento 41033, isso significa que o descobrimento do servidor do Office Web Apps falhou.</span><span class="sxs-lookup"><span data-stu-id="17f11-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="17f11-115">Nesse caso, o Microsoft Lync Server 2013 experimentará quantas vezes forem necessárias para descobrir o servidor Office Web Apps recém configurado.</span><span class="sxs-lookup"><span data-stu-id="17f11-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="17f11-116">Se o processo de descoberta falhar repetidamente, remova o servidor do Office Web Apps do documento de topologia, publique a topologia atualizada e tente adicionar o servidor do Office Web Apps novamente à topologia após a resolução dos problemas de conectividade.</span><span class="sxs-lookup"><span data-stu-id="17f11-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="17f11-117">Se o Office Web Apps Server parece estar configurado corretamente e foi reconhecido pelo processo de descoberta, você pode verificar se o servidor do Office Web Apps está funcionando como esperado compartilhando uma apresentação do PowerPoint entre um par de clientes do Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="17f11-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="17f11-118">Se o usuário A conseguir carregar e exibir a apresentação do PowerPoint e se o usuário B puder entrar na reunião e ver essa apresentação, o Office Web Apps Server está funcionando.</span><span class="sxs-lookup"><span data-stu-id="17f11-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="17f11-119">Mesmo que o Office Web Apps Server pareça estar configurado corretamente, você pode possivelmente receber a mensagem de erro "alguns recursos de compartilhamento estão indisponíveis devido a problemas de conectividade do servidor" quando você tenta compartilhar uma apresentação do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="17f11-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="17f11-120">Se você receber a mensagem de erro, reinicie o servidor front-end (ou servidores) associado ao novo servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="17f11-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

