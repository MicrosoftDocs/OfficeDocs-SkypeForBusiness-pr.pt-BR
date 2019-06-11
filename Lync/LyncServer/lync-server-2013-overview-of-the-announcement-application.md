---
title: 'Lync Server 2013: visão geral do aplicativo Announcement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e9cedddf6dfdf714bb3d0eef0e0cd01063b89f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f6a64-102">Visão geral do aplicativo de anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6a64-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6a64-103">_**Tópico da última modificação:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="f6a64-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="f6a64-104">Ao implantar o aplicativo de anúncio, você precisa configurar uma tabela de número não atribuído que determine a ação a ser tomada quando alguém discar um número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="f6a64-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="f6a64-105">A tabela número não atribuído contém intervalos de números de telefone que são válidos para a organização e especifica qual aplicativo de anúncio manipula cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="f6a64-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="f6a64-106">Quando um chamador disca para um número de telefone válido para a sua organização, mas não está atribuído a ninguém, o Lync Server procura o número na tabela de roteamento de números não atribuídos, identifica o intervalo no qual o número cai e roteia a chamada para o anúncio aplicativo especificado para esse intervalo.</span><span class="sxs-lookup"><span data-stu-id="f6a64-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="f6a64-107">O aplicativo de anúncio atende a chamada e reproduz uma mensagem de áudio (se você a configurou para fazer isso) e, em seguida, desconectará a chamada ou a transferirá para um destino predeterminado, por exemplo, para um operador.</span><span class="sxs-lookup"><span data-stu-id="f6a64-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="f6a64-108">Você pode usar cmdlets do Shell de gerenciamento do Lync Server para configurar várias mensagens de áudio ou para transferir destinos.</span><span class="sxs-lookup"><span data-stu-id="f6a64-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="f6a64-p102">A forma como você configura a tabela de número não atribuído depende de como você deseja usá-la. Se você possui números específicos que não estão mais em uso e deseja reproduzir mensagens que são personalizadas para cada número, é possível inserir esses números específicos na tabela de número não atribuído. Por exemplo, se você alterou o número do seu atendimento ao cliente, é possível inserir o número do serviço antigo e associá-lo a um anúncio que oferece o novo número. Se você deseja reproduzir uma mensagem geral para qualquer pessoa que ligar para um número não atribuído, como funcionários que deixaram a organização, é possível inserir intervalos para todas as extensões válidas em sua organização. A tabela de número não atribuído é invocada sempre que um chamador liga para um número que não está atribuído atualmente.</span><span class="sxs-lookup"><span data-stu-id="f6a64-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="f6a64-114">No Lync Server 2013, o aplicativo de anúncio é instalado automaticamente com o aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="f6a64-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="f6a64-115">Os aplicativos de anúncio e de grupo de resposta são componentes padrão de uma implantação do Enterprise Voice: ao implantar o Enterprise Voice, esses dois aplicativos são implantados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6a64-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

