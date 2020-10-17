---
title: 'Lync Server 2013: concedendo permissões de unidade organizacional'
description: 'Lync Server 2013: concedendo permissões de unidade organizacional.'
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
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554507"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="aefe8-103">Concedendo permissões de unidade organizacional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aefe8-103">Granting organizational unit permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aefe8-104">_**Última modificação do tópico:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="aefe8-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="aefe8-105">Você pode usar o cmdlet **Grant-CsOuPermission** para conceder permissões a objetos em unidades organizacionais especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessá-los sem serem membros do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="aefe8-105">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="aefe8-106">As permissões adicionadas à unidade organizacional especificada são as mesmas permissões que o cmdlet **Enable-CsAdDomain** adiciona aos contêineres de computadores e usuários durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="aefe8-106">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="aefe8-107">Use o cmdlet **Test-CsOuPermission** para verificar as permissões configuradas usando o cmdlet **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="aefe8-107">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="aefe8-108">Você pode usar o cmdlet **Revoke-CsOuPermission** para remover permissões concedidas usando o cmdlet **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="aefe8-108">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="aefe8-109">Para conceder permissões de UO</span><span class="sxs-lookup"><span data-stu-id="aefe8-109">To grant OU permissions</span></span>

1.  <span data-ttu-id="aefe8-110">Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja conceder permissões de OU.</span><span class="sxs-lookup"><span data-stu-id="aefe8-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="aefe8-111">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="aefe8-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="aefe8-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aefe8-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aefe8-113">Sejam</span><span class="sxs-lookup"><span data-stu-id="aefe8-113">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="aefe8-114">Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="aefe8-114">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="aefe8-115">Para verificar permissões de UO</span><span class="sxs-lookup"><span data-stu-id="aefe8-115">To verify OU permissions</span></span>

1.  <span data-ttu-id="aefe8-116">Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja verificar as permissões de OU concedidas usando o cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="aefe8-116">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="aefe8-117">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="aefe8-117">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="aefe8-118">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aefe8-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aefe8-119">Sejam</span><span class="sxs-lookup"><span data-stu-id="aefe8-119">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="aefe8-120">Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="aefe8-120">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="aefe8-121">Para revogar permissões de OU</span><span class="sxs-lookup"><span data-stu-id="aefe8-121">To revoke OU permissions</span></span>

1.  <span data-ttu-id="aefe8-122">Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja revogar as permissões de OU que foram concedidas pelo cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="aefe8-122">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="aefe8-123">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="aefe8-123">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="aefe8-124">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aefe8-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aefe8-125">Sejam</span><span class="sxs-lookup"><span data-stu-id="aefe8-125">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="aefe8-126">Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="aefe8-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

