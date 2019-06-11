---
title: Instalar sistemas operacionais e software de pré-requisito nos servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="7b358-102">Instalar sistemas operacionais e software de pré-requisito nos servidores para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b358-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b358-103">_**Tópico da última modificação:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="7b358-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="7b358-104">Depois de configurar a infraestrutura de hardware e do sistema, você precisa instalar os sistemas operacionais e atualizações apropriados do Windows, além de todos os outros softwares de pré-requisito em cada servidor que estiver implantando.</span><span class="sxs-lookup"><span data-stu-id="7b358-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="7b358-105">Isso inclui cada função de servidor do Lync Server 2013 e qualquer servidor de infraestrutura adicional ou servidores que executam o SQL Server necessários para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="7b358-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7b358-106">Esta seção descreve a instalação de sistemas operacionais e software de pré-requisito para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="7b358-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="7b358-107">Se você estiver implantando servidores de borda para dar suporte a acesso externo a usuários, também precisará instalar sistemas operacionais e software de pré-requisito para esses servidores, incluindo servidores de borda e servidores proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="7b358-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="7b358-108">Para obter detalhes sobre como preparar servidores para dar suporte a acesso externo a usuários, consulte Preparando-se <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">para a instalação de servidores na rede de perímetro do Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="7b358-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="7b358-109">Instalar sistemas operacionais Windows em servidores</span><span class="sxs-lookup"><span data-stu-id="7b358-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="7b358-110">Em cada servidor que você está implantando, instale o sistema operacional do Windows apropriado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7b358-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="7b358-111">**Servidores que executam o Lync Server 2013**   para obter detalhes sobre os requisitos do sistema operacional para servidores que executam o Lync Server 2013, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="7b358-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="7b358-112">**Servidores de banco de dados**   para obter detalhes sobre os requisitos de sistema operacional para servidores de banco de dados, incluindo o banco de dados back-end, o banco de dados de arquivamento e o banco de dados de monitoramento, consulte a documentação</span><span class="sxs-lookup"><span data-stu-id="7b358-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="7b358-113">Para o SQL Server 2012, consulte os manuais online do SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 em.</span><span class="sxs-lookup"><span data-stu-id="7b358-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7b358-114">Se você estiver instalando o Lync Server 2013 no&nbsp;Windows&nbsp;Server 2008 R2 com SP1, deve primeiro instalar a atualização descrita no artigo da base de dados de conhecimento Microsoft 2646886, "correcção: o corrompimento de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5 ", em <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="7b358-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="7b358-115">Você também deve modificar o registro conforme descrito no artigo da base de conhecimento, os <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">IDs de evento 32402, 61045 são registrados nos servidores front-end do Lync server 2013 instalados no Windows Server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="7b358-115">You must also modify the registry as described in the KB article, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="7b358-116">Instalar o Windows Update em servidores</span><span class="sxs-lookup"><span data-stu-id="7b358-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="7b358-117">Instale as seguintes atualizações do Windows Update em cada servidor:</span><span class="sxs-lookup"><span data-stu-id="7b358-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="7b358-118">**Windows Update para servidores que executam o Lync Server 2013**   para obter detalhes sobre as atualizações do Windows Update necessárias para servidores que executam o Lync Server 2013, consulte [requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md) no planejamento documentação.</span><span class="sxs-lookup"><span data-stu-id="7b358-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7b358-119">**Servidores de banco de dados**   para obter detalhes sobre as atualizações do Windows Update necessárias para servidores de banco de dados, incluindo o banco de dados back-end, o banco de dados de arquivamento e o banco de dados de monitoramento, consulte a documentação do SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="7b358-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="7b358-120">Para o SQL Server 2012, consulte os manuais online do SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 em.</span><span class="sxs-lookup"><span data-stu-id="7b358-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="7b358-121">Instalar outro software de pré-requisito em servidores</span><span class="sxs-lookup"><span data-stu-id="7b358-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="7b358-122">O Lync Server 2013 requer a instalação do seguinte software adicional nos servidores:</span><span class="sxs-lookup"><span data-stu-id="7b358-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="7b358-123">**Software de pré-requisito para servidores que executam o Lync Server 2013**   os pré-requisitos de software adicionais para servidores que executam o Lync Server 2013 dependem da função do servidor que está sendo implantado.</span><span class="sxs-lookup"><span data-stu-id="7b358-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="7b358-124">Para obter detalhes sobre os requisitos de software específicos para cada servidor, consulte [requisitos adicionais de software para o Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7b358-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7b358-125">\*\*\*\*   O Lync Server do Windows Identity Foundation 2013 exige a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="7b358-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="7b358-126">Para verificar se ele já foi instalado no computador, vá para o painel de controle, clique em **programas e recursos**, **Veja atualizações instaladas**e procure em **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="7b358-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="7b358-127">Para obter detalhes sobre como instalar o Windows Identity [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="7b358-127">For details about installing Windows Identity Foundation, see [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="7b358-128">**Microsoft .NET Framework 4,5**   a edição de 64 bits do Microsoft .NET Framework 4,5 é necessária para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b358-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="7b358-129">**Software de pré-requisito para servidores**   de banco de dados para obter detalhes sobre a atualização do Windows necessária para servidores de banco de dados, incluindo o banco de dados back-end, banco de dados de [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)arquivamento e banco de dados monitoramento, consulte a documentação do SQL Server 2012 em.</span><span class="sxs-lookup"><span data-stu-id="7b358-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7b358-130">O Lync Server 2013 instala automaticamente o Microsoft SQL Server 2012 Express em cada servidor Standard Edition e cada servidor que executa o Lync Server 2013 no qual o repositório de configuração local está localizado.</span><span class="sxs-lookup"><span data-stu-id="7b358-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="7b358-131">**Tempo de execução**   do formato do Windows Media todos os servidores front-end e servidores Standard Edition em que a conferência será implantada deve ter o tempo de execução do Windows Media Format instalado.</span><span class="sxs-lookup"><span data-stu-id="7b358-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="7b358-132">O tempo de execução do Windows Media Format é necessário para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos de estacionamento de chamada, anúncio e resposta são reproduzidos para anúncios e músicas.</span><span class="sxs-lookup"><span data-stu-id="7b358-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7b358-133">Para Windows Server 2012 e Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="7b358-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7b358-134">Para o Windows&nbsp;Server 2008 e o&nbsp;Windows&nbsp;Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="7b358-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="7b358-135">É recomendável instalar a experiência da área de trabalho do Windows antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b358-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="7b358-136">Se o Lync Server 2013 não encontrar esse software no servidor, ele solicitará que você o instale e, em seguida, deverá reiniciar o servidor para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="7b358-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

