---
title: 'Lync Server 2013: preparando e instalando o analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303df28b307a2d23bdc468d1c53977030d0cf8df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="40bc1-102">Preparando e instalando o Best Practices Analyzer no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40bc1-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40bc1-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="40bc1-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="40bc1-104">Você deve estar conectado como um membro do grupo Administradores para executar as tarefas que estão descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="40bc1-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="40bc1-105">Os requisitos de sistema para a instalação do Analisador de Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="40bc1-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="40bc1-106">Para executar o Lync Server 2013, o analisador de práticas recomendadas para verificar seu ambiente, o computador deve estar executando uma edição de 64 bits de um dos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="40bc1-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="40bc1-107">Sistema operacional Windows Server 2008 R2 com Service Pack 1 (SP1) Standard</span><span class="sxs-lookup"><span data-stu-id="40bc1-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="40bc1-108">Sistema operacional Windows Server 2008 R2 com SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="40bc1-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="40bc1-109">Sistema operacional Windows Server 2008 R2 com SP1 datacenter</span><span class="sxs-lookup"><span data-stu-id="40bc1-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="40bc1-110">Sistema operacional Windows Server 2012 datacenter</span><span class="sxs-lookup"><span data-stu-id="40bc1-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="40bc1-111">Sistema operacional Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="40bc1-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="40bc1-112">Sistema operacional Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="40bc1-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="40bc1-113">Sistema operacional Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40bc1-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="40bc1-114">Sistema operacional Windows Server 2012 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="40bc1-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="40bc1-115">Sistema operacional Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="40bc1-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="40bc1-116">Sistema operacional Windows 8</span><span class="sxs-lookup"><span data-stu-id="40bc1-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="40bc1-117">Sistema operacional Windows 7</span><span class="sxs-lookup"><span data-stu-id="40bc1-117">Windows 7 operating system</span></span>

<span data-ttu-id="40bc1-118">O computador também deve estar executando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="40bc1-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="40bc1-119">Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="40bc1-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="40bc1-120">Para o Lync Server 2013, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40bc1-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="40bc1-121">Lync Server 2013, componentes principais.</span><span class="sxs-lookup"><span data-stu-id="40bc1-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="40bc1-122">Pacote de compatibilidade com versões anteriores da WMI.</span><span class="sxs-lookup"><span data-stu-id="40bc1-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="40bc1-123">Para obter detalhes, consulte [instalar o pacote de compatibilidade com versões anteriores do WMI](install-wmi-backward-compatibility-package.md) na documentação de migração.</span><span class="sxs-lookup"><span data-stu-id="40bc1-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="40bc1-124">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40bc1-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="40bc1-125">Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="40bc1-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="40bc1-126">Você pode instalar o Best Practices Analyzer em computadores com um sistema operacional compatível que não esteja executando o Lync Server 2013, componentes principais ou o pacote de compatibilidade com versões anteriores do WMI, mas você pode usar o analisador de práticas recomendadas nesses computadores apenas para exibir relatórios, não para executar verificações.</span><span class="sxs-lookup"><span data-stu-id="40bc1-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="40bc1-127">Escolhendo um computador para instalação</span><span class="sxs-lookup"><span data-stu-id="40bc1-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="40bc1-128">É recomendável instalar o Lync Server 2013, o Best Practices Analyzer em um computador dedicado ao gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40bc1-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="40bc1-129">Você pode instalar a ferramenta em um servidor executando o Lync Server 2013 ou um computador administrativo executando as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40bc1-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="40bc1-130">Se você instalar a ferramenta em um servidor que está executando o Lync Server, recomendamos usar a ferramenta para verificar apenas esse servidor.</span><span class="sxs-lookup"><span data-stu-id="40bc1-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="40bc1-131">Instalando o Analisador de Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="40bc1-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="40bc1-132">Você pode baixar o Best Practices Analyzer for Lync Server 2013 [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)em.</span><span class="sxs-lookup"><span data-stu-id="40bc1-132">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="40bc1-133">Para instalar o Analisador de Práticas Recomendadas, inicie o arquivo RtcBPA.msi do Arquivo Microsoft Installer (.msi) no computador no qual você deseja instalar a ferramenta e, em seguida, siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="40bc1-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="40bc1-134">O local padrão para instalar os arquivos de programa \<é arquivos\>\\\\de programa da unidade de\\sistema do Lync Server 2013 BPA.</span><span class="sxs-lookup"><span data-stu-id="40bc1-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

