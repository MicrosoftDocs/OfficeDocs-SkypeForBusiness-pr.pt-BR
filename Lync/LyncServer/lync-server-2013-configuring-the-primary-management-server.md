---
title: 'Lync Server 2013: Configurando o servidor de gerenciamento principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6640e13209700d50aac04c43728175a4fcb4e6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="6af11-102">Configurando o servidor de gerenciamento primário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af11-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af11-103">_**Última modificação do tópico:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="6af11-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="6af11-104">Para aproveitar ao máximo os novos recursos de monitoramento de integridade incluídos no Microsoft Lync Server 2013 os administradores devem primeiro designar um computador para atuar como servidor de gerenciamento principal; nesse computador, você deve instalar o System Center Operations Manager 2007 R2 ou o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="6af11-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="6af11-105">Além disso, você deve instalar uma versão com suporte do SQL Server para funcionar como o banco de dados back-end do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6af11-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="6af11-106">Se você estiver usando o System Center Operations Manager 2012, poderá usar qualquer uma das seguintes versões do SQL Server como banco de dados back-end:</span><span class="sxs-lookup"><span data-stu-id="6af11-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="6af11-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6af11-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="6af11-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="6af11-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="6af11-109">Se você estiver usando o System Center Operations Manager 2007 R2, é recomendável instalar o SQL Server 2005 Service Pack 4 ou o SQL Server 2008 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="6af11-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="6af11-110">Você também pode usar o SQL Server 2008 R2 como banco de dados de backend para o System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6af11-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="6af11-111">Consulte o apêndice 1 desta documentação para saber mais sobre como configurar o SQL Server 2008 R2 para trabalhar com o System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6af11-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="6af11-112">Ao instalar o System Center Operations Manager 2012 ou o System Center Operations Manager 2007 R2, você precisa instalar todos os componentes desse produto, incluindo:</span><span class="sxs-lookup"><span data-stu-id="6af11-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="6af11-113">Banco de dados operacional</span><span class="sxs-lookup"><span data-stu-id="6af11-113">Operational database</span></span>

  - <span data-ttu-id="6af11-114">Servidor</span><span class="sxs-lookup"><span data-stu-id="6af11-114">Server</span></span>

  - <span data-ttu-id="6af11-115">Console</span><span class="sxs-lookup"><span data-stu-id="6af11-115">Console</span></span>

  - <span data-ttu-id="6af11-116">\s-1 \plain Windows PowerShellcmdlets</span><span class="sxs-lookup"><span data-stu-id="6af11-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="6af11-117">Console da Web</span><span class="sxs-lookup"><span data-stu-id="6af11-117">Web console</span></span>

  - <span data-ttu-id="6af11-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="6af11-118">Reporting</span></span>

  - <span data-ttu-id="6af11-119">Data warehouse</span><span class="sxs-lookup"><span data-stu-id="6af11-119">Data warehouse</span></span>

<span data-ttu-id="6af11-120">Esses componentes e respectivas instalações não serão debatidas em detalhes neste documento.</span><span class="sxs-lookup"><span data-stu-id="6af11-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="6af11-121">Para obter detalhes sobre o System Center Operations Manager 2007 R2, consulte a documentação do Operations Manager 2007 R2 em <http://go.microsoft.com/fwlink/p/?linkid=257526> e a documentação do <http://go.microsoft.com/fwlink/p/?linkid=257527>System Center Operations Manager 2012 em.</span><span class="sxs-lookup"><span data-stu-id="6af11-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="6af11-122">Siga estas instruções se você for usar o SQL Server 2005 ou o SQL Server 2008 Service Pack 1 como banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="6af11-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="6af11-123">Se você estiver usando o System Center Operations Manager 2012, poderá usar o SQL Server 2012 como banco de dados de back-end.</span><span class="sxs-lookup"><span data-stu-id="6af11-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="6af11-124">Para obter detalhes sobre o SQL Server 2012, consulte manuais online para o SQL [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)Server 2012 em.</span><span class="sxs-lookup"><span data-stu-id="6af11-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="6af11-125">Tenha em mente que você só pode ter um único servidor de gerenciamento principal por implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6af11-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="6af11-126">Além disso, embora você possa usar o System Center Operations Manager 2012 ou o System Center Operations Manager 2007 R2, não é possível executar os dois aplicativos simultaneamente, você deve escolher um ou outro.</span><span class="sxs-lookup"><span data-stu-id="6af11-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="6af11-127">Por exemplo, se você estiver executando o System Center Operations Manager 2012, todos os agentes do System Center também devem estar executando o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="6af11-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="6af11-128">Você não pode ter alguns agentes executando o System Center Operations Manager 2012 e outros agentes executando o System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6af11-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

