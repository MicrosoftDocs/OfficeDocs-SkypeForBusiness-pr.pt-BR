---
title: Instalar sistemas operacionais e software de pré-requisito nos servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69ad97d578073e2b0f9ed08d929007c33e59b8fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="d3844-102">Instalar sistemas operacionais e software de pré-requisito nos servidores do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3844-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3844-103">_**Última modificação do tópico:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="d3844-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="d3844-104">Depois de configurar o hardware e a infraestrutura do sistema, você precisa instalar os sistemas operacionais Windows e as atualizações apropriadas, além de todos os outros programas necessários em cada servidor que estiver implantando.</span><span class="sxs-lookup"><span data-stu-id="d3844-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="d3844-105">Isso inclui cada função de servidor do Lync Server 2013 e quaisquer servidores de infraestrutura adicionais ou servidores que executam o SQL Server necessários para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d3844-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d3844-106">Esta seção descreve a instalação dos sistemas operacionais e softwares de pré-requisito para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="d3844-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="d3844-107">Se você estiver implantando servidores de borda para dar suporte ao acesso de usuário externo, também precisará instalar sistemas operacionais e software de pré-requisito para esses servidores, incluindo servidores de borda e servidores de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="d3844-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="d3844-108">Para obter detalhes sobre como preparar servidores para dar suporte ao acesso de usuário externo, consulte <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">preparando para instalação de servidores na rede de perímetro do Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d3844-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="d3844-109">Instalação dos sistemas operacionais Windows nos Servidores</span><span class="sxs-lookup"><span data-stu-id="d3844-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="d3844-110">Em cada servidor que você está implantando, instale o sistema operacional Windows apropriado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d3844-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="d3844-111">**Servidores executando o Lync Server 2013**   para obter detalhes sobre os requisitos do sistema operacional para servidores que executam o Lync Server 2013, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="d3844-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="d3844-112">**Servidores de banco de dados**   para obter detalhes sobre os requisitos do sistema operacional para servidores de banco de dados, incluindo banco de dados back-end, banco de dados de arquivamento e banco de dados de monitoramento, consulte a documentação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3844-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="d3844-113">Para o SQL Server 2012, confira o SQL Server 2012 Books Online em [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span><span class="sxs-lookup"><span data-stu-id="d3844-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d3844-114">Se você estiver instalando o Lync Server 2013 no&nbsp;Windows&nbsp;Server 2008 R2 com SP1, deverá primeiro instalar a atualização descrita no artigo 2646886 de conhecimento da Microsoft, "correção: corrupção de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5", em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="d3844-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="d3844-115">Você também deve modificar o registro conforme descrito no artigo da base de conhecimento, as <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">identificações de evento 32402, 61045 são registradas nos servidores front-end do Lync Server 2013 instalados no Windows Server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="d3844-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="d3844-116">Como instalar o Windows Update em servidores</span><span class="sxs-lookup"><span data-stu-id="d3844-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="d3844-117">Instale as seguintes atualizações do Windows Update em cada servidor:</span><span class="sxs-lookup"><span data-stu-id="d3844-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="d3844-118">**Windows Update para servidores que executam o Lync Server 2013**   para obter detalhes sobre as atualizações do Windows Update necessárias para servidores que executam o Lync Server 2013, consulte [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d3844-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="d3844-119">**Servidores de banco de dados**   para obter detalhes sobre as atualizações do Windows Update necessárias para servidores de banco de dados, incluindo o banco de dados back-end, banco de dados de arquivamento e banco de dados de monitoramento, consulte a documentação do SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d3844-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="d3844-120">Para o SQL Server 2012, confira o SQL Server 2012 Books Online em [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span><span class="sxs-lookup"><span data-stu-id="d3844-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="d3844-121">Instalação de outros softwares de pré-requisito em servidores</span><span class="sxs-lookup"><span data-stu-id="d3844-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="d3844-122">O Lync Server 2013 requer a instalação do seguinte software adicional nos servidores:</span><span class="sxs-lookup"><span data-stu-id="d3844-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="d3844-123">**Software de pré-requisito para servidores que executam o Lync Server 2013**   os pré-requisitos de software adicionais para servidores que executam o Lync Server 2013 dependem da função de servidor que está sendo implantada.</span><span class="sxs-lookup"><span data-stu-id="d3844-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="d3844-124">Para obter detalhes sobre os requisitos de software específicos para cada servidor, consulte [Additional Software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d3844-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="d3844-125">**O Windows Identity Foundation**   Lync Server 2013 requer a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="d3844-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="d3844-126">Para verificar se ele já foi instalado no seu computador, vá para o painel de controle, clique em **programas e recursos**, **Veja atualizações instaladas**e procure em **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="d3844-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="d3844-127">Para obter detalhes sobre a instalação do Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="d3844-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="d3844-128">**Microsoft .NET Framework 4,5**   a edição de 64 bits do Microsoft .NET Framework 4,5 é necessária para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3844-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="d3844-129">**Software de pré-requisito para servidores**   de banco de dados para obter detalhes sobre a atualização do Windows necessária para servidores de banco de dados, incluindo banco de dados back-end, banco de dados de arquivamento e banco de dados de monitoramento, consulte a documentação do SQL Server 2012 em [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span><span class="sxs-lookup"><span data-stu-id="d3844-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3844-130">O Lync Server 2013 instala automaticamente o Microsoft SQL Server 2012 Express em cada servidor Standard Edition e cada servidor executando o Lync Server 2013 no qual o repositório de configuração local está localizado.</span><span class="sxs-lookup"><span data-stu-id="d3844-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="d3844-131">**Tempo de execução**   do Windows Media Format todos os servidores front-end e servidores Standard Edition onde a conferência será implantada deve ter o Windows Media Format Runtime instalado.</span><span class="sxs-lookup"><span data-stu-id="d3844-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="d3844-132">O Tempo de Execução do Windows Media Format é necessário para executar arquivos de Áudio do Windows Media (.wma), que aplicativos de Estacionamento de Chamadas, Comunicados e Grupos de Resposta reproduzem para comunicados e música.</span><span class="sxs-lookup"><span data-stu-id="d3844-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3844-133">Para o Windows Server 2012 e o Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="d3844-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3844-134">Para o Windows&nbsp;Server 2008 e o&nbsp;Windows&nbsp;Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="d3844-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="d3844-135">É recomendável instalar a experiência da área de trabalho do Windows antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3844-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="d3844-136">Se o Lync Server 2013 não localizar esse software no servidor, ele solicitará que você o instale e, em seguida, será necessário reiniciar o servidor para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="d3844-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

