---
title: 'Lync Server 2013: concedendo permissões de unidade organizacional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85c43cb727b83b06d6427e2bf3b6027d78dc025e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="942ca-102">Concedendo permissões de unidade organizacional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942ca-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942ca-103">_**Última modificação do tópico:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="942ca-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="942ca-104">Você pode usar o cmdlet **Grant-CsOuPermission** para conceder permissões a objetos em unidades organizacionais especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessá-los sem serem membros do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="942ca-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="942ca-105">As permissões adicionadas à unidade organizacional especificada são as mesmas permissões que o cmdlet **Enable-CsAdDomain** adiciona aos contêineres de computadores e usuários durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="942ca-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="942ca-106">Use o cmdlet **Test-CsOuPermission** para verificar as permissões configuradas usando o cmdlet **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="942ca-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="942ca-107">Você pode usar o cmdlet **Revoke-CsOuPermission** para remover permissões concedidas usando o cmdlet **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="942ca-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="942ca-108">Para conceder permissões de UO</span><span class="sxs-lookup"><span data-stu-id="942ca-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="942ca-109">Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja conceder permissões de OU.</span><span class="sxs-lookup"><span data-stu-id="942ca-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="942ca-110">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="942ca-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="942ca-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="942ca-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="942ca-112">Sejam</span><span class="sxs-lookup"><span data-stu-id="942ca-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="942ca-113">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="942ca-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="942ca-114">Para verificar permissões de UO</span><span class="sxs-lookup"><span data-stu-id="942ca-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="942ca-115">Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja verificar as permissões de OU concedidas usando o cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="942ca-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="942ca-116">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="942ca-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="942ca-117">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="942ca-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="942ca-118">Sejam</span><span class="sxs-lookup"><span data-stu-id="942ca-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="942ca-119">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="942ca-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="942ca-120">Para revogar permissões de OU</span><span class="sxs-lookup"><span data-stu-id="942ca-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="942ca-121">Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja revogar as permissões de OU que foram concedidas pelo cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="942ca-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="942ca-122">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="942ca-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="942ca-123">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="942ca-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="942ca-124">Sejam</span><span class="sxs-lookup"><span data-stu-id="942ca-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="942ca-125">Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="942ca-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

