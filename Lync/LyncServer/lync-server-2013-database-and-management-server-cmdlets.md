---
title: 'Lync Server 2013: cmdlets de banco de dados e servidor de gerenciamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database and Management Server cmdlets
ms:assetid: b323bd59-8f71-4f03-af94-f3afb8620f4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415671(v=OCS.15)
ms:contentKeyID: 48185174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25bf5b464b8bda91d2374811d3c727154d1ceccc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-and-management-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="68bbc-102">Cmdlets de banco de dados e servidor de gerenciamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bbc-102">Database and Management Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68bbc-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="68bbc-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="68bbc-104">Os cmdlets do banco de dados e do servidor de gerenciamento são usados para gerenciar os bancos de dados de back-end do Microsoft Lync Server 2013 e seus serviços de gerenciamento de front-end.</span><span class="sxs-lookup"><span data-stu-id="68bbc-104">The database and Management Server cmdlets are used to manage both your Microsoft Lync Server 2013 back-end databases and your front-end management services.</span></span> <span data-ttu-id="68bbc-105">Você pode usar esses cmdlets para instalar ou desinstalar qualquer um dos bancos de dados usados pelo Lync Server 2013, além de configurar o ponto de controle de serviço do Active Directory para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="68bbc-105">You can use these cmdlets to install or uninstall any of the databases used by Lync Server 2013, in addition to configuring the Active Directory service control point for the Central Management store.</span></span>

<div>

## <a name="database-and-management-server-cmdlets"></a><span data-ttu-id="68bbc-106">Cmdlets de banco de dados e do Servidor de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="68bbc-106">Database and Management Server Cmdlets</span></span>

<span data-ttu-id="68bbc-107">Veja a seguir uma lista de cmdlets que se relacionam diretamente com o gerenciamento de bancos de dados e do Servidor de Gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="68bbc-107">The following is a list of cmdlets that relate directly to managing databases and the Management Server:</span></span>

<span data-ttu-id="68bbc-108">**Bancos de dados e Servidor de Gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="68bbc-108">**Databases and Management Server**</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="68bbc-112">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-112">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-113">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-113">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68bbc-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68bbc-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68bbc-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="68bbc-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="68bbc-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="68bbc-121">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-121">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="68bbc-122">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-122">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68bbc-123">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-123">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68bbc-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68bbc-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68bbc-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="68bbc-125">See Also</span></span>


[<span data-ttu-id="68bbc-126">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="68bbc-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

