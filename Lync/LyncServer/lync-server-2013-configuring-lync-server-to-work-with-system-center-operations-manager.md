---
title: Configurando o Lync Server para trabalhar com o System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff72248e691d3e5358fda79a98d318cfc3a382eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="1c81e-102">Configurando o Lync Server 2013 para trabalhar com o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1c81e-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c81e-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1c81e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1c81e-104">Para configurar sua infraestrutura do Microsoft Lync Server 2013 para trabalhar com o System Center Operations Manager, você deve fazer três coisas:</span><span class="sxs-lookup"><span data-stu-id="1c81e-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="1c81e-105">Identifique e configure seu servidor de gerenciamento do System Center Operations Manager principal.</span><span class="sxs-lookup"><span data-stu-id="1c81e-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="1c81e-106">A configuração do servidor de gerenciamento inclui a instalação do System Center Operations Manager 2012 ou do System Center Operations Manager 2007 R2, bem como a configuração de um banco de dados back-end usando o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c81e-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="1c81e-107">A versão real do SQL Server que você precisa usar depende da versão do System Center Operations Manager que você está usando.</span><span class="sxs-lookup"><span data-stu-id="1c81e-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="1c81e-108">Para obter detalhes, consulte [Configuring the Primary Management Server in Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="1c81e-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="1c81e-109">Identifique e configure os computadores do Lync Server que você deseja monitorar.</span><span class="sxs-lookup"><span data-stu-id="1c81e-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="1c81e-110">Para monitorar um computador do Lync Server usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para atuar como um proxy.</span><span class="sxs-lookup"><span data-stu-id="1c81e-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="1c81e-111">Identifique e configure os computadores que você deseja que atue como nós do *Inspetor*do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c81e-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="1c81e-112">Os nós do Inspetor são computadores que executam periodicamente as transações sintéticas do Lync Server, que são cmdlets do Windows PowerShell que verificam se os principais componentes do Lync Server, como a capacidade de fazer logon no sistema ou a capacidade de trocar mensagens instantâneas são funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="1c81e-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="1c81e-113">Os tópicos nesta seção contêm instruções para executar cada uma dessas tarefas.</span><span class="sxs-lookup"><span data-stu-id="1c81e-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1c81e-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1c81e-114">In This Section</span></span>

  - [<span data-ttu-id="1c81e-115">Configurando o servidor de gerenciamento primário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c81e-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="1c81e-116">Instalando os pacotes de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c81e-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="1c81e-117">Configurando os computadores do Lync Server que serão monitorados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c81e-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="1c81e-118">Instalando e configurando nós do Inspetor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c81e-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

