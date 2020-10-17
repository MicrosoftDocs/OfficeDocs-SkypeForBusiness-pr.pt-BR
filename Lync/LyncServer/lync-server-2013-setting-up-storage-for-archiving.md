---
title: 'Lync Server 2013: configurar armazenamento para arquivamento'
description: 'Lync Server 2013: configurar armazenamento para arquivamento.'
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
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554237"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="84973-103">Configurando o armazenamento para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84973-103">Setting up storage for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84973-104">_**Última modificação do tópico:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="84973-104">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="84973-105">O armazenamento de arquivamento do Lync Server 2013 inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="84973-105">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="84973-106">**Armazenamento**     de dados O armazenamento de dados é necessário para armazenar o conteúdo de IM.</span><span class="sxs-lookup"><span data-stu-id="84973-106">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="84973-107">**Armazenamento**     de arquivos O armazenamento de arquivos é necessário para armazenar a conferência (reunião) armazenamento de dados de conteúdo e armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="84973-107">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="84973-108">Configurando o armazenamento de dados</span><span class="sxs-lookup"><span data-stu-id="84973-108">Setting Up Data Storage</span></span>

<span data-ttu-id="84973-109">Os requisitos para a configuração do armazenamento de dados para arquivamento no Lync Server 2013 dependem de como você deseja armazenar dados de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="84973-109">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="84973-110">Integre o arquivamento do Lync Server 2013 com sua implantação do Exchange para armazenar dados de arquivamento usando o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="84973-110">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="84973-111">Configurar servidores de banco de dados do SQL Server separados para armazenar dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="84973-111">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="84973-112">Configurando o repositório do Exchange para arquivamento de dados</span><span class="sxs-lookup"><span data-stu-id="84973-112">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="84973-113">A configuração do Exchange para armazenamento de dados de arquivamento exige que sua implantação do Exchange esteja executando o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="84973-113">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="84973-114">Além disso, as caixas de correio do usuário devem estar hospedadas no servidor Exchange 2013 e suas caixas de correio devem ser colocadas em In-Place.</span><span class="sxs-lookup"><span data-stu-id="84973-114">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="84973-115">Para obter detalhes sobre como configurar o Exchange 2013, consulte a documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="84973-115">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="84973-116">Configurando o repositório dos Servidores de banco de dados do SQL Server para arquivamento de dados</span><span class="sxs-lookup"><span data-stu-id="84973-116">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="84973-117">O arquivamento no Lync Server 2013 requer o software de banco de dados do SQL Server para armazenar os dados arquivados, a menos que você integre sua implantação com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="84973-117">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="84973-118">Para bancos de dados de arquivamento do SQL Server, você deve instalar o SQL Server no computador que hospedará o banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="84973-118">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="84973-119">É possível usar a mesma instância do SQL utilizada para o banco de dados de back-end de um pool de Front Ends.</span><span class="sxs-lookup"><span data-stu-id="84973-119">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="84973-120">Para obter um melhor desempenho, você deve implantar o banco de dados de arquivamento em um computador separado do armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="84973-120">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="84973-121">Para obter detalhes sobre a colocação de componentes do Lync Server 2013, consulte [suporte à colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="84973-121">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="84973-122">Cada servidor de banco de dados deve estar executando uma versão com suporte do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="84973-122">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="84973-123">Para obter detalhes sobre as versões com suporte, consulte [Technical Requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="84973-123">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="84973-124">Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="84973-124">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="84973-125">Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="84973-125">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="84973-126">Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="84973-126">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="84973-127">Para obter detalhes sobre o SQL Server, consulte o TechCenter do SQL Server em [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .</span><span class="sxs-lookup"><span data-stu-id="84973-127">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84973-128">Verifique se o tipo de inicialização do serviço do SQL Server Agent é automático e se o serviço SQL Server Agent está em execução para a instância SQL que está segurando o banco de dados de arquivamento, para que o trabalho de manutenção padrão de arquivamento do SQL Server possa ser executado com base no controle do serviço do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="84973-128">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="84973-129">Configurando o armazenamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="84973-129">Setting Up File Storage</span></span>

<span data-ttu-id="84973-130">O arquivamento usa o compartilhamento de arquivo do Lync Server 2013 que você especificou ao configurar seu pool de front-ends ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="84973-130">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="84973-131">Não é possível alterar o compartilhamento de arquivos usado para o Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="84973-131">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="84973-132">Para obter detalhes sobre os sistemas de armazenamento de arquivos com suporte, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="84973-132">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

