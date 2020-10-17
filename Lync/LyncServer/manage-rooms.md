---
title: Gerenciar salas
description: Gerenciar salas.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be093e14a68639fdde73b58936e1b2f5cf4424cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544587"
---
# <a name="manage-rooms"></a><span data-ttu-id="7442b-103">Gerenciar salas</span><span class="sxs-lookup"><span data-stu-id="7442b-103">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7442b-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7442b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7442b-105">Para criar uma nova sala de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="7442b-105">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7442b-106">-PersistentChatPoolFqdn não é necessário se um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="7442b-106">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7442b-107">Há apenas um pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7442b-107">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="7442b-108">Você oferece um FQDN do pool para a categoria.</span><span class="sxs-lookup"><span data-stu-id="7442b-108">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="7442b-109">Você oferece um FQDN do pool para adicionar a sala.</span><span class="sxs-lookup"><span data-stu-id="7442b-109">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="7442b-110">Para fazer alterações em uma sala de servidor de chat persistente existente</span><span class="sxs-lookup"><span data-stu-id="7442b-110">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="7442b-111">Windows PowerShell: Membros, gerentes e apresentadores podem ser definidos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="7442b-111">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="7442b-112">Todos eles devem ser um subconjunto de AllowedMembers menos DeniedMembers da Categoria de host.</span><span class="sxs-lookup"><span data-stu-id="7442b-112">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="7442b-113">Uma sala que é type=normal não pode incluir Apresentadores.</span><span class="sxs-lookup"><span data-stu-id="7442b-113">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="7442b-114">Criar, Obter, Definir, Limpar ou Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="7442b-114">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="7442b-115">Para criar uma nova sala</span><span class="sxs-lookup"><span data-stu-id="7442b-115">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="7442b-116">Para definir ma sala</span><span class="sxs-lookup"><span data-stu-id="7442b-116">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="7442b-117">Para obter uma sala</span><span class="sxs-lookup"><span data-stu-id="7442b-117">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="7442b-118">ou</span><span class="sxs-lookup"><span data-stu-id="7442b-118">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="7442b-119">onde –filter suporta apenas Nome e Descrição e ajuda a encontrar salas cujo Nome/Descrição corresponde a cadeia de caracteres de palavra chave.</span><span class="sxs-lookup"><span data-stu-id="7442b-119">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="7442b-120">O PoolFqdn pesquisa em um determinado pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7442b-120">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="7442b-121">Para limpar uma sala e mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="7442b-121">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="7442b-122">ou</span><span class="sxs-lookup"><span data-stu-id="7442b-122">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="7442b-123">Para remover uma sala</span><span class="sxs-lookup"><span data-stu-id="7442b-123">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="7442b-124">ou</span><span class="sxs-lookup"><span data-stu-id="7442b-124">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

