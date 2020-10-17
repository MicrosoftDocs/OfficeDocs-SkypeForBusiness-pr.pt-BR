---
title: 'Lync Server 2013: Gerenciando chamadas para números não atribuídos'
description: 'Lync Server 2013: Gerenciando chamadas para números não atribuídos.'
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
ms.openlocfilehash: a91c1ec30ea1e942fa3ea27fbcd369572884a52a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569147"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="fd445-103">Gerenciando chamadas para números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd445-103">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd445-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fd445-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fd445-105">O Lync Server permite que você configure o tratamento de chamadas telefônicas de entrada quando o número discado é válido para sua organização, mas não é atribuído a um usuário ou telefone.</span><span class="sxs-lookup"><span data-stu-id="fd445-105">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="fd445-106">Você pode usar o aplicativo de comunicado para transferir essas chamadas para um destino predeterminado (número de telefone, URI de SIP ou caixa postal) ou reproduzir um anúncio de áudio ou ambos.</span><span class="sxs-lookup"><span data-stu-id="fd445-106">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="fd445-107">Também é possível transferir essas chamadas para um número telefônico do Atendedor Automático do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="fd445-107">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="fd445-108">Tratar das chamadas a números não atribuídos é uma das maneiras de evitar a situação em que um chamador liga para o número incorreto e ouve um tom de ocupado, ou o cliente SIP recebe uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="fd445-108">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="fd445-p102">Esta seção descreve como gerenciar intervalos de números não atribuídos para tratar as chamadas a números não atribuídos. A seção também descreve como gerenciar Comunicados durante recuperação de desastres, se você desejar essa funcionalidade durante uma interrupção de energia.</span><span class="sxs-lookup"><span data-stu-id="fd445-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd445-111">O uso do tratamento de chamadas a números não atribuídos durante uma interrupção de energia é opcional.</span><span class="sxs-lookup"><span data-stu-id="fd445-111">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd445-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fd445-112">In This Section</span></span>

  - [<span data-ttu-id="fd445-113">Criar um comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd445-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="fd445-114">Configurar números de telefone não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd445-114">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="fd445-115">Gerenciar comunicados durante recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd445-115">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

