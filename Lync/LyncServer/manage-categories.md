---
title: Gerenciar categorias
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bac2433702a90624e3ee4fb865bfb70b6d07d16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="27dd5-102">Manage categories</span><span class="sxs-lookup"><span data-stu-id="27dd5-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27dd5-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="27dd5-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="27dd5-104">Para criar uma nova categoria de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="27dd5-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="27dd5-105">PersistentChatPoolFqdn é necessário apenas se houver mais de um pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="27dd5-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="27dd5-106">Para fazer alterações na categoria de servidor de chat persistente existente</span><span class="sxs-lookup"><span data-stu-id="27dd5-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="27dd5-107">Windows PowerShell: AllowedMembers, DeniedMembers e Creator podem ser definidos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="27dd5-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="27dd5-108">Os criadores devem ser o subconjunto de AllowedMembers menos DeniedMembers.</span><span class="sxs-lookup"><span data-stu-id="27dd5-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="27dd5-109">Você também pode definir as propriedades de uma categoria ao mesmo tempo que os membros e os criadores.</span><span class="sxs-lookup"><span data-stu-id="27dd5-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="27dd5-110">Criar, obter, definir ou remover uma categoria</span><span class="sxs-lookup"><span data-stu-id="27dd5-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="27dd5-111">Para criar uma nova categoria</span><span class="sxs-lookup"><span data-stu-id="27dd5-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="27dd5-112">Para obter uma categoria</span><span class="sxs-lookup"><span data-stu-id="27dd5-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="27dd5-113">ou</span><span class="sxs-lookup"><span data-stu-id="27dd5-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="27dd5-114">Para definir uma categoria</span><span class="sxs-lookup"><span data-stu-id="27dd5-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="27dd5-115">ou</span><span class="sxs-lookup"><span data-stu-id="27dd5-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="27dd5-116">Para remover uma categoria</span><span class="sxs-lookup"><span data-stu-id="27dd5-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="27dd5-117">ou</span><span class="sxs-lookup"><span data-stu-id="27dd5-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

