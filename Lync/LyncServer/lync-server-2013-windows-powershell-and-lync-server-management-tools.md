---
title: 'Lync Server 2013: ferramentas de gerenciamento do Windows PowerShell e do Lync Server'
description: 'Lync Server 2013: ferramentas de gerenciamento do Windows PowerShell e do Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546037"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="bf205-103">Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf205-103">Windows PowerShell and Lync Server 2013 management tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf205-104">_**Última modificação do tópico:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="bf205-104">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="bf205-105">No Microsoft Lync Server 2013, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf205-105">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="bf205-106">O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa.</span><span class="sxs-lookup"><span data-stu-id="bf205-106">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="bf205-107">As ferramentas do Lync Server 2013 que são implementadas usando o Windows PowerShell incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bf205-107">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="bf205-108">**Construtor de topologias**.</span><span class="sxs-lookup"><span data-stu-id="bf205-108">**Topology Builder**.</span></span> <span data-ttu-id="bf205-109">Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada e valida sua topologia antes de iniciar instalações de servidor.</span><span class="sxs-lookup"><span data-stu-id="bf205-109">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="bf205-110">Quando você instala o Lync Server 2013 em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor conforme indicado na topologia.</span><span class="sxs-lookup"><span data-stu-id="bf205-110">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="bf205-111">Após a configuração, as informações de configuração são automaticamente replicadas para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="bf205-111">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="bf205-112">Os componentes podem ser adicionados à sua implantação apenas usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="bf205-112">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="bf205-113">**Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf205-113">**Lync Server Management Shell**.</span></span> <span data-ttu-id="bf205-114">Você pode usar o Shell de gerenciamento do Lync Server para o gerenciamento completo de linha de comando de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="bf205-114">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="bf205-115">**Painel de controle do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf205-115">**Lync Server Control Panel**.</span></span> <span data-ttu-id="bf205-116">Você pode usar a interface do usuário do painel de controle do Microsoft Lync Server 2013 para gerenciar as tarefas mais comuns em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="bf205-116">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="bf205-117">Essas ferramentas usam os cmdlets do Windows PowerShell para gerenciamento de sua implantação, incluindo aproximadamente 550 cmdlets específicos ao produto.</span><span class="sxs-lookup"><span data-stu-id="bf205-117">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="bf205-118">Os cmdlets de segurança incluídos no Lync Server 2013 são usados principalmente para gerenciar a autenticação e os direitos e permissões do usuário.</span><span class="sxs-lookup"><span data-stu-id="bf205-118">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="bf205-119">Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="bf205-119">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="bf205-120">Além disso, vários cmdlets permitem que você use o novo recurso de controle de acesso de Role-Based (RBAC) para delegar o controle administrativo do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf205-120">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="bf205-121">Para obter detalhes sobre os cmdlets do Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="bf205-121">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="bf205-122">Os recursos de segurança de script para Windows PowerShell são projetados especificamente para ajudar a impedir alguns dos problemas de segurança relacionados a script de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="bf205-122">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="bf205-123">Os recursos de segurança do Windows PowerShell têm como objetivo a criação de um ambiente no qual os usuários não podem executar facilmente ou sem intenção.</span><span class="sxs-lookup"><span data-stu-id="bf205-123">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="bf205-124">Por padrão, os recursos de segurança do Windows PowerShell estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="bf205-124">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="bf205-125">É possível modificar o estado desses recursos a fim de acomodar suas necessidades de script e diversas metas de segurança.</span><span class="sxs-lookup"><span data-stu-id="bf205-125">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="bf205-126">Isso sem mencionar que o shell impossibilita a execução de scripts pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="bf205-126">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="bf205-127">Em vez disso, o dificulta—por padrão—a execução sem intenção de scripts pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="bf205-127">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="bf205-128">Para obter detalhes, consulte segurança de scripts do Windows PowerShell em [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .</span><span class="sxs-lookup"><span data-stu-id="bf205-128">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

