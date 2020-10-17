---
title: 'Lync Server 2013: requisitos para publicar uma topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f4186a351876b874a8b84963f9923369511f65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511818"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="dad5e-102">Requisitos para publicar uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad5e-102">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dad5e-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dad5e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dad5e-104">Este tópico descreve os requisitos de infraestrutura e software específicos à publicação de uma topologia, seja usando o construtor de topologias ou a interface de linha de comando do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dad5e-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="dad5e-105">Esses requisitos são além dos requisitos gerais de sistema operacional, software e permissões aplicáveis a todas as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dad5e-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="dad5e-106">Certifique-se de atender a todos os requisitos de ferramentas administrativas antes de publicar uma topologia.</span><span class="sxs-lookup"><span data-stu-id="dad5e-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="dad5e-107">Você deve executar o construtor de topologias em um computador que ingressou no mesmo domínio ou floresta da implantação do Lync Server 2013 que você está criando para que as etapas de preparação dos serviços de domínio Active Directory já tenham sido concluídas, permitindo que você use as ferramentas administrativas desse computador para publicar com êxito sua topologia.</span><span class="sxs-lookup"><span data-stu-id="dad5e-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="dad5e-p102">Os computadores definidos na topologia devem ingressar no domínio e no AD DS, exceto os Servidores de Borda. No entanto, os computadores não precisam estar online quando você publica a topologia.</span><span class="sxs-lookup"><span data-stu-id="dad5e-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="dad5e-110">O compartilhamento de arquivo para o pool deve ser criado e está disponível para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="dad5e-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="dad5e-111">Para publicar um pool de front-ends Enterprise Edition, o servidor back-end baseado em SQL Server deve ser associado ao domínio no qual você está implantando os servidores, online e configurado com as regras de firewall apropriadas para torná-lo disponível aos usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="dad5e-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="dad5e-112">Para obter detalhes sobre como especificar exceções de firewall, consulte [Understanding firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dad5e-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="dad5e-113">Para obter outros detalhes sobre a configuração do SQL Server, consulte [Configurar o SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="dad5e-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dad5e-114">O servidor Standard Edition tem um banco de dados colocado que aceitará a configuração publicada.</span><span class="sxs-lookup"><span data-stu-id="dad5e-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="dad5e-115">Você deve primeiro executar a tarefa de configuração <STRONG>preparar primeiro servidor Standard Edition</STRONG> no assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dad5e-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="dad5e-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="dad5e-116">See Also</span></span>


[<span data-ttu-id="dad5e-117">Publicar a topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad5e-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="dad5e-118">Delegar permissões de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad5e-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="dad5e-119">Requisitos de software de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad5e-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="dad5e-120">Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad5e-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="dad5e-121">Direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad5e-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

