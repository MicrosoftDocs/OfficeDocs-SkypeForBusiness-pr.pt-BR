---
title: 'Lync Server 2013: Validando a configuração do servidor do Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34c774411fd825dd01595ef1e51ffa9c65c6eb8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="615ae-102">Validando a configuração do servidor do Office Web Apps no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="615ae-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="615ae-103">_**Última modificação do tópico:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="615ae-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="615ae-104">Depois que o servidor do Office Web Apps tiver sido adicionado à topologia e depois que essa topologia tiver sido publicada, você verá dois eventos de log de eventos novos no log de eventos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="615ae-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="615ae-105">Primeiro, um evento MCU de dados de LS (ID de evento 41034) deve ser adicionado; Este evento relatará que o servidor do Office Web Apps foi descoberto:</span><span class="sxs-lookup"><span data-stu-id="615ae-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="615ae-106">**Servidor de conferência da Web o servidor do Office Web Apps é descoberto, o conteúdo do PowerPoint está habilitado.**</span><span class="sxs-lookup"><span data-stu-id="615ae-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="615ae-p102">Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:</span><span class="sxs-lookup"><span data-stu-id="615ae-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="615ae-109">**Descoberta bem-sucedida do servidor do Office Web Apps do servidor de Webconferência.**</span><span class="sxs-lookup"><span data-stu-id="615ae-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="615ae-110">**Página do apresentador interno do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="615ae-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="615ae-111">**Página de participantes internos do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="615ae-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="615ae-112">**Página do apresentador externo do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="615ae-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="615ae-113">**Página de participantes internos do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="615ae-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="615ae-114">Se você ver um evento LS Data MCU com o ID 41033, significa que a descoberta do Office Web Apps Server falhou.</span><span class="sxs-lookup"><span data-stu-id="615ae-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="615ae-115">Nesse caso, o Microsoft Lync Server 2013 tentará quantas vezes forem necessárias para descobrir o servidor do Office Web Apps recém configurado.</span><span class="sxs-lookup"><span data-stu-id="615ae-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="615ae-116">Se o processo de descoberta falhar repetidamente, você deve remover o Office Web Apps Server do seu documento de topologia, publicar a topologia atualizada e tentar adicionar o Office Web Apps Server novamente à topologia depois que os problemas de conectividade tiverem sido resolvidos.</span><span class="sxs-lookup"><span data-stu-id="615ae-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="615ae-117">Se o servidor do Office Web Apps parece estar configurado corretamente e foi reconhecido pelo processo de descoberta, é possível verificar se o servidor do Office Web Apps está funcionando conforme o esperado, compartilhando uma apresentação do PowerPoint entre um par de clientes do Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="615ae-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="615ae-118">Se o Usuário A puder carregar e exibir a apresentação do PowerPoint e se o Usuário B puder participar da reunião e ver a apresentação, então o Office Web Apps Server está funcionando.</span><span class="sxs-lookup"><span data-stu-id="615ae-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="615ae-p105">Mesmo que o Office Web Apps Server pareça estar configurado corretamente, é possível receber a mensagem de erro “Alguns recursos de compartilhamento não estão disponíveis devido a problemas de conectividade do servidor” ao tentar compartilhar uma apresentação do PowerPoint. Se você receber essa mensagem de erro, você deve reiniciar o servidor (ou servidores) de Front End associados ao novo Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="615ae-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

