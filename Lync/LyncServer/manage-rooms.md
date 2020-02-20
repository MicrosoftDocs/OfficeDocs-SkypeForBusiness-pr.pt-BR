---
title: Gerenciar salas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc3f9e2c680d2812c11c41a551132d580de17f46
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="ea4cd-102">Gerenciar salas</span><span class="sxs-lookup"><span data-stu-id="ea4cd-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea4cd-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ea4cd-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ea4cd-104">Para criar uma nova sala de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ea4cd-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea4cd-105">-PersistentChatPoolFqdn não é necessário se um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="ea4cd-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ea4cd-106">Há apenas um pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="ea4cd-107">Você oferece um FQDN do pool para a categoria.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="ea4cd-108">Você oferece um FQDN do pool para adicionar a sala.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ea4cd-109">Para fazer alterações em uma sala de servidor de chat persistente existente</span><span class="sxs-lookup"><span data-stu-id="ea4cd-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="ea4cd-110">Windows PowerShell: Membros, gerentes e apresentadores podem ser definidos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="ea4cd-111">Todos eles devem ser um subconjunto de AllowedMembers menos DeniedMembers da Categoria de host.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="ea4cd-112">Uma sala que é type=normal não pode incluir Apresentadores.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="ea4cd-113">Criar, Obter, Definir, Limpar ou Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="ea4cd-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="ea4cd-114">Para criar uma nova sala</span><span class="sxs-lookup"><span data-stu-id="ea4cd-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="ea4cd-115">Para definir ma sala</span><span class="sxs-lookup"><span data-stu-id="ea4cd-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="ea4cd-116">Para obter uma sala</span><span class="sxs-lookup"><span data-stu-id="ea4cd-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="ea4cd-117">ou</span><span class="sxs-lookup"><span data-stu-id="ea4cd-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="ea4cd-118">onde –filter suporta apenas Nome e Descrição e ajuda a encontrar salas cujo Nome/Descrição corresponde a cadeia de caracteres de palavra chave.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="ea4cd-119">O PoolFqdn pesquisa em um determinado pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="ea4cd-120">Para limpar uma sala e mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="ea4cd-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="ea4cd-121">ou</span><span class="sxs-lookup"><span data-stu-id="ea4cd-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="ea4cd-122">Para remover uma sala</span><span class="sxs-lookup"><span data-stu-id="ea4cd-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="ea4cd-123">ou</span><span class="sxs-lookup"><span data-stu-id="ea4cd-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

