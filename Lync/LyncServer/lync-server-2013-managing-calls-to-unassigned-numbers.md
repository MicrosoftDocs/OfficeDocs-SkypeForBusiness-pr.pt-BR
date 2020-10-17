---
title: 'Lync Server 2013: Gerenciando chamadas para números não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b09be36c372473fc6700669f069646ca3f6054d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505888"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="6731a-102">Gerenciando chamadas para números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6731a-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6731a-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6731a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6731a-104">O Lync Server permite que você configure o tratamento de chamadas telefônicas de entrada quando o número discado é válido para sua organização, mas não é atribuído a um usuário ou telefone.</span><span class="sxs-lookup"><span data-stu-id="6731a-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="6731a-105">Você pode usar o aplicativo de comunicado para transferir essas chamadas para um destino predeterminado (número de telefone, URI de SIP ou caixa postal) ou reproduzir um anúncio de áudio ou ambos.</span><span class="sxs-lookup"><span data-stu-id="6731a-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="6731a-106">Também é possível transferir essas chamadas para um número telefônico do Atendedor Automático do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6731a-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="6731a-107">Tratar das chamadas a números não atribuídos é uma das maneiras de evitar a situação em que um chamador liga para o número incorreto e ouve um tom de ocupado, ou o cliente SIP recebe uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="6731a-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="6731a-p102">Esta seção descreve como gerenciar intervalos de números não atribuídos para tratar as chamadas a números não atribuídos. A seção também descreve como gerenciar Comunicados durante recuperação de desastres, se você desejar essa funcionalidade durante uma interrupção de energia.</span><span class="sxs-lookup"><span data-stu-id="6731a-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6731a-110">O uso do tratamento de chamadas a números não atribuídos durante uma interrupção de energia é opcional.</span><span class="sxs-lookup"><span data-stu-id="6731a-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6731a-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6731a-111">In This Section</span></span>

  - [<span data-ttu-id="6731a-112">Criar um comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6731a-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="6731a-113">Configurar números de telefone não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6731a-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="6731a-114">Gerenciar comunicados durante recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6731a-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

