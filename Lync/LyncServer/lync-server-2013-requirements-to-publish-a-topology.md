---
title: 'Lync Server 2013: Requisitos para publicar uma topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e90604315732d9e9bfe4c45968ff0bcf5fbd2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="e045a-102">Requisitos para publicar uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e045a-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e045a-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e045a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e045a-104">Este tópico descreve os requisitos de infraestrutura e software que são específicos para a publicação de uma topologia, seja usando o construtor de topologias ou a interface de linha de comando do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e045a-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="e045a-105">Esses requisitos são além dos requisitos gerais do sistema operacional, do software e das permissões aplicáveis a todas as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e045a-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e045a-106">Certifique-se de satisfazer todos os requisitos de ferramentas administrativas antes de publicar uma topologia.</span><span class="sxs-lookup"><span data-stu-id="e045a-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="e045a-107">Você deve executar o construtor de topologias em um computador que esteja associado ao mesmo domínio ou floresta da implantação do Lync Server 2013 que você está criando para que as etapas de preparação dos serviços de domínio Active Directory sejam concluídas, permitindo que você use as ferramentas administrativas em esse computador para publicar sua topologia com êxito.</span><span class="sxs-lookup"><span data-stu-id="e045a-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="e045a-108">Os computadores definidos na topologia devem ser associados ao domínio, exceto para servidores de borda e no AD DS.</span><span class="sxs-lookup"><span data-stu-id="e045a-108">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="e045a-109">No entanto, os computadores não precisam estar online quando você publica a topologia.</span><span class="sxs-lookup"><span data-stu-id="e045a-109">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="e045a-110">O compartilhamento de arquivos do pool deve ser criado e disponibilizado para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="e045a-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="e045a-111">Para publicar um pool de front-end do Enterprise Edition, o servidor back-end baseado no SQL Server deve estar associado ao domínio no qual você está implantando os servidores, online e configurado com as regras de firewall adequadas para disponibilizá-lo para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="e045a-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="e045a-112">Para obter detalhes sobre como especificar exceções de firewall, consulte [noções básicas sobre requisitos de firewall do SQL Server com o Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e045a-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="e045a-113">Para obter mais detalhes sobre a configuração do SQL Server, consulte [Configurar o SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="e045a-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e045a-114">O servidor Standard Edition tem um banco de dados posicionado que aceitará a configuração publicada.</span><span class="sxs-lookup"><span data-stu-id="e045a-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="e045a-115">Você deve primeiro executar a tarefa de configuração <STRONG>preparar primeiro o servidor Standard Edition</STRONG> no assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e045a-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="e045a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e045a-116">See Also</span></span>


[<span data-ttu-id="e045a-117">Publicar a topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e045a-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="e045a-118">Delegar permissões de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e045a-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="e045a-119">Requisitos de software de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e045a-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="e045a-120">Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e045a-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="e045a-121">Direitos e permissões de administrador necessários para configuração e administração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e045a-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

