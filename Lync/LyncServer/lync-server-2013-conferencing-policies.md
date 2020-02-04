---
title: 'Lync Server 2013: políticas de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d1d9ed6fc0ad75e316a41ef7939f36ecaba354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="b22f6-102">Políticas de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b22f6-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b22f6-103">_**Tópico da última modificação:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="b22f6-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="b22f6-104">A política de conferência define os recursos e as funcionalidades que os usuários disponibilizam durante uma conferência (também conhecida como reunião).</span><span class="sxs-lookup"><span data-stu-id="b22f6-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="b22f6-105">As definições de política de conferência englobam uma grande variedade de opções de agendamento e participação, desde se uma reunião pode incluir vídeo e áudio IP até o número máximo de pessoas que podem participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="b22f6-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="b22f6-106">Os administradores podem usar a política de conferência para gerenciar a segurança, a largura de banda e os aspectos legais das reuniões.</span><span class="sxs-lookup"><span data-stu-id="b22f6-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="b22f6-107">Você pode definir a política de conferência em três níveis: escopo global, escopo de site e escopo de usuário.</span><span class="sxs-lookup"><span data-stu-id="b22f6-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="b22f6-108">As configurações se aplicam a um usuário específico desde o menor escopo até o maior.</span><span class="sxs-lookup"><span data-stu-id="b22f6-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="b22f6-109">Se você atribuir uma política de usuário a um usuário, essas configurações terão precedência.</span><span class="sxs-lookup"><span data-stu-id="b22f6-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="b22f6-110">Caso você não atribua uma política de usuário, aplicam-se as definições de site.</span><span class="sxs-lookup"><span data-stu-id="b22f6-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="b22f6-111">Caso políticas de usuários ou de site não sejam aplicáveis, a política global fornece as definições padrão.</span><span class="sxs-lookup"><span data-stu-id="b22f6-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="b22f6-112">Há uma política global por padrão, portanto você não pode criar uma nova política global.</span><span class="sxs-lookup"><span data-stu-id="b22f6-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="b22f6-113">Você também não pode excluir a política global existente, mas pode alterar a política global existente para personalizar suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="b22f6-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b22f6-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b22f6-114">In This Section</span></span>

  - [<span data-ttu-id="b22f6-115">Exibir informações de política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b22f6-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="b22f6-116">Criar ou modificar uma política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b22f6-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="b22f6-117">Excluir uma política de conferência existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b22f6-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="b22f6-118">Referência de configurações de política de conferência para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b22f6-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

