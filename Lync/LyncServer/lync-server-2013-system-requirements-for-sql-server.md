---
title: 'Lync Server 2013: requisitos de sistema para o SQL Server'
description: 'Lync Server 2013: requisitos de sistema para o SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524136174be8798aed1dc7d5d236dbb45ab18330
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562627"
---
# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="d7885-103">Requisitos do sistema para o SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7885-103">System requirements for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7885-104">_**Última modificação do tópico:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="d7885-104">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="d7885-105">Antes de implantar o servidor Enterprise Edition, instale o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 em um computador dedicado que atenda aos requisitos de hardware.</span><span class="sxs-lookup"><span data-stu-id="d7885-105">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="d7885-106">Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="d7885-106">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="d7885-107">Para obter detalhes sobre os requisitos de software, consulte [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="d7885-107">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="d7885-108">Para obter informações sobre as permissões necessárias para a implantação, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7885-108">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="d7885-109">Antes de criar o pool de front-ends, você também deve configurar o Firewall do Windows para permitir o acesso do Lync Server 2013 ao SQL Server em portas específicas definindo portas para o servidor usando o Gerenciador de configuração do SQL Server e abrindo portas no firewall do Windows com segurança avançada.</span><span class="sxs-lookup"><span data-stu-id="d7885-109">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

