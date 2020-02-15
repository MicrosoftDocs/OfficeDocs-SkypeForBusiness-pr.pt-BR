---
title: 'Lync Server 2013: ferramentas de gerenciamento do Windows PowerShell e do Lync Server'
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
ms.openlocfilehash: 0e475cd9249030ec09ad3261e84e068d9db0e8c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="44e0c-102">Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e0c-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e0c-103">_**Última modificação do tópico:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="44e0c-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="44e0c-104">No Microsoft Lync Server 2013, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44e0c-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="44e0c-105">O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa.</span><span class="sxs-lookup"><span data-stu-id="44e0c-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="44e0c-106">As ferramentas do Lync Server 2013 que são implementadas usando o Windows PowerShell incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="44e0c-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="44e0c-107">**Construtor de topologias**.</span><span class="sxs-lookup"><span data-stu-id="44e0c-107">**Topology Builder**.</span></span> <span data-ttu-id="44e0c-108">Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada e valida sua topologia antes de iniciar instalações de servidor.</span><span class="sxs-lookup"><span data-stu-id="44e0c-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="44e0c-109">Quando você instala o Lync Server 2013 em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor conforme indicado na topologia.</span><span class="sxs-lookup"><span data-stu-id="44e0c-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="44e0c-110">Após a configuração, as informações de configuração são automaticamente replicadas para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="44e0c-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="44e0c-111">Os componentes podem ser adicionados à sua implantação apenas usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="44e0c-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="44e0c-112">**Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="44e0c-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="44e0c-113">Você pode usar o Shell de gerenciamento do Lync Server para o gerenciamento completo de linha de comando de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="44e0c-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="44e0c-114">**Painel de controle do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="44e0c-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="44e0c-115">Você pode usar a interface do usuário do painel de controle do Microsoft Lync Server 2013 para gerenciar as tarefas mais comuns em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="44e0c-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="44e0c-116">Essas ferramentas usam os cmdlets do Windows PowerShell para gerenciamento de sua implantação, incluindo aproximadamente 550 cmdlets específicos ao produto.</span><span class="sxs-lookup"><span data-stu-id="44e0c-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="44e0c-117">Os cmdlets de segurança incluídos no Lync Server 2013 são usados principalmente para gerenciar a autenticação e os direitos e permissões do usuário.</span><span class="sxs-lookup"><span data-stu-id="44e0c-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="44e0c-118">Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="44e0c-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="44e0c-119">Além disso, vários cmdlets permitem que você use o novo recurso RBAC (controle de acesso baseado em função) para delegar o controle administrativo do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44e0c-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="44e0c-120">Para obter detalhes sobre os cmdlets do Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="44e0c-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="44e0c-121">Os recursos de segurança de script para Windows PowerShell são projetados especificamente para ajudar a impedir alguns dos problemas de segurança relacionados a script de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="44e0c-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="44e0c-122">Os recursos de segurança do Windows PowerShell têm como objetivo a criação de um ambiente no qual os usuários não podem executar facilmente ou sem intenção.</span><span class="sxs-lookup"><span data-stu-id="44e0c-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="44e0c-123">Por padrão, os recursos de segurança do Windows PowerShell estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="44e0c-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="44e0c-124">É possível modificar o estado desses recursos a fim de acomodar suas necessidades de script e diversas metas de segurança.</span><span class="sxs-lookup"><span data-stu-id="44e0c-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="44e0c-125">Isso sem mencionar que o shell impossibilita a execução de scripts pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="44e0c-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="44e0c-126">Em vez disso, o dificulta—por padrão—a execução sem intenção de scripts pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="44e0c-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="44e0c-127">Para obter detalhes, consulte segurança de scripts do [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)Windows PowerShell em.</span><span class="sxs-lookup"><span data-stu-id="44e0c-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

