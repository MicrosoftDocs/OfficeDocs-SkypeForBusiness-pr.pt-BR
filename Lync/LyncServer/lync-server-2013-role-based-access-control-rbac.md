---
title: 'Lync Server 2013: controle de acesso baseado em função (RBAC)'
description: 'Lync Server 2013: controle de acesso baseado em função (RBAC).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576577"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="09299-103">Controle de acesso baseado em função (RBAC) para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09299-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09299-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="09299-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="09299-105">O Microsoft Lync Server 2013 inclui grupos de controle de acesso de Role-Based (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="09299-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="09299-106">Esses grupos são criados durante a preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="09299-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="09299-107">Para obter detalhes sobre a preparação da floresta, consulte [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="09299-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="09299-108">Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="09299-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="09299-109">Com o RBAC, o privilégio administrativo é concedido atribuindo usuários a funções administrativas predefinidas, incluindo as 11 funções predefinidas que abrangem várias tarefas administrativas comuns.</span><span class="sxs-lookup"><span data-stu-id="09299-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="09299-110">Cada função é associada a uma lista específica de cmdlets do Shell de gerenciamento do Lync Server que os usuários dessa função têm permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="09299-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="09299-111">Você pode usar o RBAC para seguir o princípio do "privilégio mínimo", onde os usuários recebem apenas as habilidades administrativas necessárias para seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="09299-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="09299-112">Para obter detalhes, consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="09299-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

