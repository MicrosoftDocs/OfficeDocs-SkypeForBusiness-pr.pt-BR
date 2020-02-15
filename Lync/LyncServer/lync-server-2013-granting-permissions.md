---
title: 'Lync Server 2013: concedendo permissões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 495b556254ab42270aa031861aea0c4390f17602
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="f8782-102">Concedendo permissões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8782-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8782-103">_**Última modificação do tópico:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="f8782-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f8782-104">Para a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma OU (unidade organizacional) do Active Directory específica, permitindo que os membros do grupo RTCUniversalServerAdmins nesse OU instalem o Lync Server 2013 no domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="f8782-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="f8782-105">Ao conceder permissões para um OU, as seguintes permissões são concedidas:</span><span class="sxs-lookup"><span data-stu-id="f8782-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="f8782-106">Ler</span><span class="sxs-lookup"><span data-stu-id="f8782-106">Read</span></span>

  - <span data-ttu-id="f8782-107">Gravar</span><span class="sxs-lookup"><span data-stu-id="f8782-107">Write</span></span>

  - <span data-ttu-id="f8782-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="f8782-108">ReadSPN</span></span>

  - <span data-ttu-id="f8782-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="f8782-109">WriteSPN</span></span>

<span data-ttu-id="f8782-110">Para administração, você pode adicionar permissões a UOs especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as UOs sem precisar ser membros do grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="f8782-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="f8782-111">As permissões adicionadas à UO especificada são as mesmas permissões que o cmdlet **Enable-CsAdDomain** adiciona aos contêineres de UO computadores e usuários.</span><span class="sxs-lookup"><span data-stu-id="f8782-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8782-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f8782-112">In This Section</span></span>

  - [<span data-ttu-id="f8782-113">Concedendo permissões de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8782-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="f8782-114">Concedendo permissões de unidade organizacional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8782-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

