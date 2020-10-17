---
title: 'Lync Server 2013: habilitar usuários para repositório unificado de contatos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b4c060cfce4e45f4736abcbc0d4c9d02b1abc1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528548"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="fb754-102">Habilitar usuários para repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb754-102">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb754-103">_**Última modificação do tópico:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="fb754-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="fb754-104">Quando você implanta o Lync Server 2013 e publica a topologia, o repositório unificado de contatos é habilitado para todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="fb754-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="fb754-105">Você não precisa realizar qualquer ação adicional para habilitar o repositório unificado de contatos após implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb754-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="fb754-106">Contudo, você pode usar o **Set-CsUserServicesPolicy** cmdlet para definir quais usuários têm o armazenamento unificado de contatos disponível.</span><span class="sxs-lookup"><span data-stu-id="fb754-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="fb754-107">Você pode habilitar esse recurso globalmente, por local, por tenant ou por indivíduos ou grupos de indivíduos.</span><span class="sxs-lookup"><span data-stu-id="fb754-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="fb754-108">Para permitir o armazenamento unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="fb754-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="fb754-109">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fb754-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fb754-110">Faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="fb754-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="fb754-111">Para habilitar o repositório unificado de contatos globalmente para todos os usuários do Lync Server, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="fb754-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="fb754-112">Para permitir o armazenamento unificado de contatos para os usuários em um local específico, digite na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="fb754-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="fb754-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fb754-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="fb754-114">Para permitir o armazenamento unificado de contatos por tenant, digite na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="fb754-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="fb754-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fb754-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="fb754-116">Para permitir o armazenamento unificado de contatos para usuários específicos, digite na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="fb754-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb754-117">Você também pode alterar o URI do SIP ou o usuário remoto em vez do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="fb754-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="fb754-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fb754-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb754-p102">No exemplo anterior, o primeiro comando criar uma nova política de acordo com o usuário chamada <EM>Usuários do UCS Permitidos</EM>, com o sinalizador AcsAllowed definido para True. O segundo comando define a política ao usuário com nome de Ken Myer, o que significa que Ken Myer está autorizado a ter armazenamento unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="fb754-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

