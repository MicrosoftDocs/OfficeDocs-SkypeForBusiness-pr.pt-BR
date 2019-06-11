---
title: 'Lync Server 2013: Gerenciando chamadas para números não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50a6c7fe05729f705bd7ea752658f7c890188159
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="1898b-102">Gerenciando chamadas para números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1898b-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1898b-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1898b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1898b-104">O Lync Server permite que você configure a manipulação de chamadas telefônicas de entrada quando o número discado é válido para a sua organização, mas não é atribuído a um usuário ou telefone.</span><span class="sxs-lookup"><span data-stu-id="1898b-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="1898b-105">Você pode usar o aplicativo de anúncio para transferir essas chamadas para um destino predeterminado (número de telefone, URI de SIP ou caixa postal) ou executar um anúncio de áudio ou ambos.</span><span class="sxs-lookup"><span data-stu-id="1898b-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="1898b-106">Você também pode transferir essas chamadas para um número de telefone de atendedor automático do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="1898b-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="1898b-107">A manipulação de chamadas para números não atribuídos de uma dessas maneiras ajuda você a evitar as situações em que um chamador disca sem erros e ouve um tom ocupado, ou o cliente SIP recebe uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1898b-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="1898b-108">Esta seção descreve como gerenciar intervalos de números não atribuídos para manipular chamadas para números de telefone não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="1898b-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="1898b-109">A seção também descreve como gerenciar anúncios durante a recuperação de desastres se desejar essa funcionalidade durante uma interrupção.</span><span class="sxs-lookup"><span data-stu-id="1898b-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1898b-110">Usar a manipulação de número não atribuído durante uma interrupção é opcional.</span><span class="sxs-lookup"><span data-stu-id="1898b-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1898b-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1898b-111">In This Section</span></span>

  - [<span data-ttu-id="1898b-112">Criar um anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1898b-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="1898b-113">Configurar números de telefone não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1898b-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="1898b-114">Gerenciar comunicados durante recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1898b-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

