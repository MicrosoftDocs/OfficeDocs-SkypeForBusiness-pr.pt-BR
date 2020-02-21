---
title: Configurar regras de PIN (número de identificação pessoal) de conferência discada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16b56e1809f9ffefa37065a208340e1143e38487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="b1bd4-102">Configurar regras de PIN (número de identificação pessoal) de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1bd4-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1bd4-103">_**Última modificação do tópico:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="b1bd4-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="b1bd4-104">Lync Server 2013 os usuários que têm credenciais do AD DS (serviços de domínio Active Directory) em sua organização podem participar de conferências discadas como usuários autenticados usando um PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="b1bd4-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="b1bd4-105">A política de PIN define as regras de funcionamento dos PINs de conferências de discagem.</span><span class="sxs-lookup"><span data-stu-id="b1bd4-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="b1bd4-p102">É possível criar uma nova política de PIN se você quiser que uma política específica seja aplicada a um site ou a determinado grupo de usuários. Se você quiser usar a mesma política de PIN para toda sua organização, poderá usar a política de PIN global e modificá-la conforme o necessário. As políticas de PIN se aplicam aos usuários a partir do escopo mais estreito para o mais amplo. Se você atribuir uma política de PIN no nível de usuário a um usuário, essas configurações terão precedência. Se você não atribuir uma política de usuário, a política de PIN no nível de site será aplicada, se existir. Se nenhuma política de usuário ou site se aplicar, a política de PIN global fornecerá as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="b1bd4-p102">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users. If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b1bd4-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b1bd4-112">In This Section</span></span>

  - [<span data-ttu-id="b1bd4-113">Modificar as configurações de PIN de conferência discada padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1bd4-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="b1bd4-114">Criar ou modificar as configurações de PIN de conferência discada no Lync Server 2013 para um site ou grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="b1bd4-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="b1bd4-115">Excluir as configurações de PIN de conferência discada para um site ou grupo de usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1bd4-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

