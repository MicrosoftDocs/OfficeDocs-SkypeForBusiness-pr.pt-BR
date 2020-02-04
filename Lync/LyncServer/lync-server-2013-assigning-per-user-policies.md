---
title: 'Lync Server 2013: atribuir políticas por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b80446d9117a37b86c386132aa80439cb568a98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="4f565-102">Como atribuir políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f565-103">_**Tópico da última modificação:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="4f565-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="4f565-104">Você pode atribuir determinadas políticas a um usuário ou a um grupo de usuários para especificar configurações específicas que se desviam das configurações definidas em políticas atribuídas a outros usuários, como políticas globais.</span><span class="sxs-lookup"><span data-stu-id="4f565-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="4f565-105">Essas políticas são chamadas políticas por usuário.</span><span class="sxs-lookup"><span data-stu-id="4f565-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f565-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4f565-106">In This Section</span></span>

  - [<span data-ttu-id="4f565-107">Atribuir uma política de conferência por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="4f565-108">Atribuir uma política de versão de cliente por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="4f565-109">Atribuir uma política de PIN por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="4f565-110">Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="4f565-111">Atribuir uma política de arquivamento por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="4f565-112">Atribuir uma política de localização por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="4f565-113">Atribuir uma política de mobilidade por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="4f565-114">Atribuir uma política de chat persistente por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="4f565-115">Atribuir uma política de plano de discagem por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="4f565-116">Atribuir uma política de voz por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f565-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="4f565-117">See Also</span></span>


[<span data-ttu-id="4f565-118">Gerenciando usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f565-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

