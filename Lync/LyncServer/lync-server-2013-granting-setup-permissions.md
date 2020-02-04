---
title: 'Lync Server 2013: Concedendo permissões de configuração'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="981e3-102">Concedendo permissões de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="981e3-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="981e3-103">_**Tópico da última modificação:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="981e3-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="981e3-104">Você pode usar o cmdlet **Grant-CsSetupPermission** para adicionar permissões de leitura, gravação, ReadSPN e WriteSPN ao grupo RTCUniversalServerAdmins para uma unidade organizacional (ou) especificada do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="981e3-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="981e3-105">Em seguida, os membros do grupo RTCUniversalServerAdmins nessa UO podem instalar servidores que executam o Lync Server 2013 no domínio especificado sem serem membros do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="981e3-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="981e3-106">Use o cmdlet **Test-CsSetupPermission** para verificar as permissões configuradas usando o cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="981e3-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="981e3-107">Você pode usar o cmdlet **REVOKE-CsSetupPermission** para remover permissões concedidas usando o cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="981e3-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="981e3-108">Para conceder permissões de configuração</span><span class="sxs-lookup"><span data-stu-id="981e3-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="981e3-109">Faça logon em um computador que esteja executando o Lync Server 2013 no domínio onde você deseja conceder permissões de configuração.</span><span class="sxs-lookup"><span data-stu-id="981e3-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="981e3-110">Use uma conta que seja membro do grupo Domain admins ou do grupo Administradores de empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="981e3-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="981e3-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="981e3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="981e3-112">Execute:</span><span class="sxs-lookup"><span data-stu-id="981e3-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="981e3-113">Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio especificado (por exemplo, CN = computadores).</span><span class="sxs-lookup"><span data-stu-id="981e3-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="981e3-114">Você também pode especificar esse parâmetro como o nome diferenciado (DN) completo da OU (por exemplo, "CN = computadores, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="981e3-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="981e3-115">Nesse caso, você deve especificar um DN de OU consistente com o domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="981e3-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="981e3-116">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="981e3-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="981e3-117">Para verificar as permissões de configuração</span><span class="sxs-lookup"><span data-stu-id="981e3-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="981e3-118">Faça logon em um computador que esteja executando o Lync Server 2013 no domínio em que você deseja verificar as permissões de configuração concedidas usando o cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="981e3-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="981e3-119">Use uma conta que seja membro do grupo Domain admins ou do grupo Administradores de empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="981e3-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="981e3-120">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="981e3-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="981e3-121">Execute:</span><span class="sxs-lookup"><span data-stu-id="981e3-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="981e3-122">Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio especificado (por exemplo, CN = computadores).</span><span class="sxs-lookup"><span data-stu-id="981e3-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="981e3-123">Você também pode especificar esse parâmetro como o nome diferenciado (DN) completo da OU (por exemplo, "CN = computadores, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="981e3-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="981e3-124">Nesse caso, você deve especificar um DN de OU consistente com o domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="981e3-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="981e3-125">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="981e3-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="981e3-126">Para revogar permissões de configuração</span><span class="sxs-lookup"><span data-stu-id="981e3-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="981e3-127">Faça logon em um computador que esteja executando o Lync Server 2013 no domínio onde você deseja revogar as permissões de configuração que foram concedidas pelo cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="981e3-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="981e3-128">Use uma conta que seja membro do grupo Domain admins ou do grupo Administradores de empresa se a UO estiver em um domínio filho diferente.</span><span class="sxs-lookup"><span data-stu-id="981e3-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="981e3-129">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="981e3-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="981e3-130">Execute:</span><span class="sxs-lookup"><span data-stu-id="981e3-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="981e3-131">Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio especificado (por exemplo, CN = computadores).</span><span class="sxs-lookup"><span data-stu-id="981e3-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="981e3-132">Você também pode especificar esse parâmetro como o nome diferenciado (DN) completo da OU (por exemplo, "CN = computadores, DC = contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="981e3-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="981e3-133">Nesse caso, você deve especificar um DN de OU consistente com o domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="981e3-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="981e3-134">Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="981e3-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

