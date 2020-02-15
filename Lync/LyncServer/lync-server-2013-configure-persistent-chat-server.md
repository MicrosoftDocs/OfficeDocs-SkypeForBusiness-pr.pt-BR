---
title: 'Lync Server 2013: configurar servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c43bfaf3b40a746f09a000cb089509b589e39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="147b9-102">Configurar o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="147b9-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="147b9-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="147b9-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="147b9-104">Para criar uma nova configuração de chat persistente</span><span class="sxs-lookup"><span data-stu-id="147b9-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="147b9-105">Para obter configuração de chat persistente</span><span class="sxs-lookup"><span data-stu-id="147b9-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="147b9-106">Para remover a configuração de chat persistente</span><span class="sxs-lookup"><span data-stu-id="147b9-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="147b9-107">Para definir a configuração de chat persistente</span><span class="sxs-lookup"><span data-stu-id="147b9-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="147b9-108">Para o Lync Server 2013, todo o tráfego do serviço Web é suportado no Lync Server 2013, servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="147b9-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="147b9-109">Portanto, o endereço gcweb01 no servidor de chat persistente não é necessário.</span><span class="sxs-lookup"><span data-stu-id="147b9-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="147b9-110">Ainda oferecemos suporte ao acesso de serviço web interno porque fornecemos serviços de upload/download de arquivos na web somente para o site *interno* (e não para o site *externo* para usuários remotos).</span><span class="sxs-lookup"><span data-stu-id="147b9-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

