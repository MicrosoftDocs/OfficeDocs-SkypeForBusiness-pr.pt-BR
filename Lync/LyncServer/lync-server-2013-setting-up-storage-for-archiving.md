---
title: 'Lync Server 2013: configurar armazenamento para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a87522269396a6ca9e362ded0454a55b3e105061
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="0a1ea-102">Configurando o armazenamento para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a1ea-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a1ea-103">_**Última modificação do tópico:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="0a1ea-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="0a1ea-104">O armazenamento de arquivamento do Lync Server 2013 inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0a1ea-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="0a1ea-105">\*\*\*\*   O armazenamento de dados de armazenamento de dados é necessário para armazenar o conteúdo de im.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="0a1ea-106">\*\*\*\*   O armazenamento de arquivos de armazenamento de arquivos é necessário para armazenar a conferência (reunião) armazenamento de dados de conteúdo e armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="0a1ea-107">Configurando o armazenamento de dados</span><span class="sxs-lookup"><span data-stu-id="0a1ea-107">Setting Up Data Storage</span></span>

<span data-ttu-id="0a1ea-108">Os requisitos para a configuração do armazenamento de dados para arquivamento no Lync Server 2013 dependem de como você deseja armazenar dados de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="0a1ea-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="0a1ea-109">Integre o arquivamento do Lync Server 2013 com sua implantação do Exchange para armazenar dados de arquivamento usando o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="0a1ea-110">Configurar servidores de banco de dados do SQL Server separados para armazenar dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="0a1ea-111">Configurando o repositório do Exchange para arquivamento de dados</span><span class="sxs-lookup"><span data-stu-id="0a1ea-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="0a1ea-112">A configuração do Exchange para armazenamento de dados de arquivamento exige que sua implantação do Exchange esteja executando o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="0a1ea-113">Além disso, as caixas de correio do usuário devem estar hospedadas no servidor Exchange 2013 e suas caixas de correio devem ser colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="0a1ea-114">Para obter detalhes sobre como configurar o Exchange 2013, consulte a documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="0a1ea-115">Configurando o repositório dos Servidores de banco de dados do SQL Server para arquivamento de dados</span><span class="sxs-lookup"><span data-stu-id="0a1ea-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="0a1ea-116">O arquivamento no Lync Server 2013 requer o software de banco de dados do SQL Server para armazenar os dados arquivados, a menos que você integre sua implantação com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="0a1ea-117">Para bancos de dados de arquivamento do SQL Server, você deve instalar o SQL Server no computador que hospedará o banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="0a1ea-118">É possível usar a mesma instância do SQL utilizada para o banco de dados de back-end de um pool de Front Ends.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="0a1ea-119">Para obter um melhor desempenho, você deve implantar o banco de dados de arquivamento em um computador separado do armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="0a1ea-120">Para obter detalhes sobre a colocação de componentes do Lync Server 2013, consulte [suporte à colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0a1ea-121">Cada servidor de banco de dados deve estar executando uma versão com suporte do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="0a1ea-122">Para obter detalhes sobre as versões com suporte, consulte [Technical Requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="0a1ea-123">Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="0a1ea-124">Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="0a1ea-125">Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="0a1ea-126">Para obter detalhes sobre o SQL Server, consulte o TechCenter do [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-126">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a1ea-127">Certifique-se de que o tipo de inicialização do serviço SQL Server Agent seja automático e que o serviço SQL Server Agent esteja em execução para a instância SQL que está segurando o banco de dados de arquivamento, para que o trabalho de manutenção padrão de arquivamento do SQL Server possa ser executado na base agendada sob o controle do serviço do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="0a1ea-128">Configurando o armazenamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="0a1ea-128">Setting Up File Storage</span></span>

<span data-ttu-id="0a1ea-129">O arquivamento usa o compartilhamento de arquivo do Lync Server 2013 que você especificou ao configurar seu pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="0a1ea-130">Não é possível alterar o compartilhamento de arquivos usado para o Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="0a1ea-131">Para obter detalhes sobre os sistemas de armazenamento de arquivos com suporte, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="0a1ea-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

