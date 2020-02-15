---
title: 'Lync Server 2013: concedendo permissões de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61fb0f5eac11016cf21dd8691ed9fa5f97bc804f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="a608e-102">Concedendo permissões de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a608e-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a608e-103">_**Última modificação do tópico:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="a608e-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="a608e-104">Você pode usar o cmdlet **Grant-CsSetupPermission** para adicionar permissões de leitura, gravação, ReadSPN e WriteSPN ao grupo RTCUniversalServerAdmins para uma unidade organizacional (ou) especificada do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a608e-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="a608e-105">Em seguida, os membros do grupo RTCUniversalServerAdmins no OU podem instalar servidores que executam o Lync Server 2013 no domínio especificado sem ser membros do grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="a608e-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="a608e-106">Use o cmdlet do **Test-CsSetupPermission** para verificar as permissões que você configurou usando o cmdlet **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="a608e-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="a608e-107">Você pode usar o cmdlet **Revoke-CsSetupPermission** para remover as permissões que você concedeu usando o cmdlet **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="a608e-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="a608e-108">Para conceder permissões de configuração</span><span class="sxs-lookup"><span data-stu-id="a608e-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="a608e-109">Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja conceder permissões de configuração.</span><span class="sxs-lookup"><span data-stu-id="a608e-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="a608e-110">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="a608e-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="a608e-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a608e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a608e-112">Sejam</span><span class="sxs-lookup"><span data-stu-id="a608e-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="a608e-p103">Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio específico (por exemplo, CN=computers). De outro modo, você pode especificar esse parâmetro como o nome diferenciado (DN) de UO completo (por exemplo, "CN=computers,DC=Contoso,DC=com"). No último caso, você de especificar um DN de OU que seja consistente com o domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="a608e-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="a608e-116">Se você não especificar o parâmetro de Domínio, o valor padrão é o domínio local.</span><span class="sxs-lookup"><span data-stu-id="a608e-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="a608e-117">Para verificar as permissões de configuração</span><span class="sxs-lookup"><span data-stu-id="a608e-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="a608e-118">Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja verificar as permissões de configuração concedidas usando o cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="a608e-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="a608e-119">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="a608e-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="a608e-120">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a608e-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a608e-121">Sejam</span><span class="sxs-lookup"><span data-stu-id="a608e-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="a608e-p105">Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio específico (por exemplo, CN=computers). De outro modo, você pode especificar esse parâmetro como o nome diferenciado (DN) de UO completo (por exemplo, "CN=computers,DC=Contoso,DC=com"). No último caso, você de especificar um DN de OU que seja consistente com o domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="a608e-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="a608e-125">Se você não especificar o parâmetro de Domínio, o valor padrão é o domínio local.</span><span class="sxs-lookup"><span data-stu-id="a608e-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="a608e-126">Para revogar as permissões de configuração</span><span class="sxs-lookup"><span data-stu-id="a608e-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="a608e-127">Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja revogar as permissões de instalação concedidas pelo cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="a608e-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="a608e-128">Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="a608e-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="a608e-129">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a608e-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a608e-130">Sejam</span><span class="sxs-lookup"><span data-stu-id="a608e-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="a608e-p107">Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio específico (por exemplo, CN=computers). De outro modo, você pode especificar esse parâmetro como o nome diferenciado (DN) de UO completo (por exemplo, "CN=computers,DC=Contoso,DC=com"). No último caso, você de especificar um DN de OU que seja consistente com o domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="a608e-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="a608e-134">Se você não especificar o parâmetro de Domínio, o valor padrão é o domínio local.</span><span class="sxs-lookup"><span data-stu-id="a608e-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

