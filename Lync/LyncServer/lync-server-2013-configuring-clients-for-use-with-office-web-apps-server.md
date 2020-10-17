---
title: 'Lync Server 2013: Configurando clientes para uso com o servidor do Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf46a16d38e37dd8faac39a438053dcc7b8c103
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537058"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="224b3-102">Configurando clientes do Lync Server 2013 para uso com o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="224b3-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="224b3-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="224b3-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="224b3-104">Se você quiser que os usuários experimentem todos os recursos do servidor do Office Web App, atualize-os para o Microsoft Lync 2013; somente os usuários do Lync 2013 poderão fazer coisas como rolar por slides do PowerPoint independentemente da apresentação real do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="224b3-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="224b3-105">(Ou seja, esses usuários podem ver qualquer slide na apresentação a qualquer momento, sem interferir de qualquer forma com a apresentação real.) Os usuários que não estiverem usando o Lync 2013 ainda poderão participar de conferências online e exibir a apresentação do PowerPoint; no entanto, eles não poderão rolar de forma independente nos slides, nem poderão ver as transições de slide ou exibir vídeos incorporados.</span><span class="sxs-lookup"><span data-stu-id="224b3-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="224b3-106">Observe que esses recursos sempre estarão disponíveis para usuários do Lync 2013; Isso é verdadeiro mesmo se o apresentador do PowerPoint estiver executando o Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="224b3-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="224b3-107">Se uma apresentação do PowerPoint estiver sendo hospedada por um usuário que executa o Lync 2010, o Lync Server 2013 coordenará com o servidor do Office Web Apps para garantir que os usuários do Lync 2013 exibirão a versão do servidor do Office Web Apps dessa apresentação.</span><span class="sxs-lookup"><span data-stu-id="224b3-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="224b3-108">O servidor do Office Web Apps não fornece serviços do PowerPoint para usuários que executam clientes diferentes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="224b3-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="224b3-109">Em vez disso, os usuários se conectam ao serviço do servidor de conferência e exibem apresentações do PowerPoint da mesma forma que faziam no Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="224b3-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="224b3-110">Isso também significa que esses usuários terão acesso apenas aos recursos mais limitados oferecidos pelo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="224b3-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="224b3-111">Embora nenhuma configuração de cliente seja necessária para o servidor do Office Web Apps (diferente de atualizar usuários para o Lync 2013), é recomendável que os participantes da conferência sejam atualizados para o Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="224b3-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="224b3-112">Embora as conferências possam ser acessadas usando o Internet Explorer 8, existem algumas limitações ao usar esse navegador.</span><span class="sxs-lookup"><span data-stu-id="224b3-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="224b3-113">Por exemplo, usuários do Internet Explorer 8 não serão capazes de redimensionar a tela do PowerPoint a um tamanho personalizado; ao invés disso, eles estarão limitados a usar um dos três tamanhos de tela predefinidos.</span><span class="sxs-lookup"><span data-stu-id="224b3-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="224b3-114">Do mesmo modo, usuários do Internet Explorer 8 não serão capazes de reproduzir arquivos de mídia.</span><span class="sxs-lookup"><span data-stu-id="224b3-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

