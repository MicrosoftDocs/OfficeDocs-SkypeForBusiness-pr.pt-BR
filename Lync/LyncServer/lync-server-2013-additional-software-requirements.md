---
title: 'Lync Server 2013: Requisitos adicionais de software'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="0907c-102">Requisitos adicionais de software para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0907c-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0907c-103">_**Tópico da última modificação:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="0907c-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="0907c-104">Além dos requisitos de hardware e sistema operacional das plataformas do servidor, o Lync Server 2013 requer a instalação de software adicional nos servidores que você implantar.</span><span class="sxs-lookup"><span data-stu-id="0907c-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0907c-105">Para obter detalhes sobre os requisitos da plataforma para servidores que executam o Lync Server, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor para o Lync server 2013</A> e <A href="lync-server-2013-server-and-tools-operating-system-support.md">servidor e ferramentas, suporte ao sistema operacional do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0907c-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="0907c-106">Para obter detalhes sobre os requisitos do sistema para computadores e dispositivos cliente, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">planejando para clientes e dispositivos no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0907c-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="0907c-107">Para obter detalhes sobre os requisitos de software para ferramentas administrativas, consulte <A href="lync-server-2013-administrative-tools-software-requirements.md">requisitos de software para ferramentas administrativas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0907c-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="0907c-108">Software adicional necessário para todas as funções de servidor interno</span><span class="sxs-lookup"><span data-stu-id="0907c-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="0907c-109">Esta seção lista o software necessário em todas as funções de servidor interno, que são todas as funções de servidor do Lync Server, exceto para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="0907c-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="0907c-110">Os requisitos para os servidores de borda e os pools de bordas são listados mais adiante neste tópico em **software adicional para servidores de borda**.</span><span class="sxs-lookup"><span data-stu-id="0907c-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="0907c-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="0907c-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="0907c-112">Cada servidor executando o Lync Server 2013 deve ter a versão correta do Windows PowerShell 3,0 instalada.</span><span class="sxs-lookup"><span data-stu-id="0907c-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="0907c-113">Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="0907c-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="0907c-114">Microsoft.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0907c-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="0907c-115">O Lync Server requer o Microsoft .NET Framework 4,5 em todas as funções de servidor interno e em qualquer computador no qual você executará as ferramentas administrativas do Lync Server ou o Microsoft Lync Server 2013, ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0907c-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="0907c-116">Para o Lync Server 2013, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0907c-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="0907c-117">Para instalá-lo manualmente, baixe a estrutura do Microsoft .NET 4,5 a partir do centro de download da Microsoft em[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="0907c-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="0907c-118">Instalando o Microsoft .NET Framework 4,5 em servidores que executam o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0907c-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="0907c-119">Ao instalar o Microsoft .NET Framework 4,5 em servidores que executarão o Lync Server 2013 e o Windows Server 2012, você deve executar uma etapa adicional.</span><span class="sxs-lookup"><span data-stu-id="0907c-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="0907c-120">Após instalar o .NET Framework 4,5, use o Gerenciador de servidores para instalar a ativação HTTP.</span><span class="sxs-lookup"><span data-stu-id="0907c-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="0907c-121">**Para instalar a ativação HTTP do .NET 4,5 no Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="0907c-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="0907c-122">No menu **Iniciar** , clique em **programas**e, em seguida, clique em **Ferramentas administrativas**e, em seguida, clique em **Gerenciador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="0907c-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="0907c-123">No Gerenciador de servidores, em **Resumo de recursos**, escolha **Adicionar recursos**.</span><span class="sxs-lookup"><span data-stu-id="0907c-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="0907c-124">Expanda o **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="0907c-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="0907c-125">Selecione **ativação do WCF** , se ainda não estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="0907c-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="0907c-126">Em seguida, selecione **ativação http**.</span><span class="sxs-lookup"><span data-stu-id="0907c-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="0907c-127">Clique em **Avançar** e siga as instruções para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="0907c-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="0907c-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="0907c-128">Windows Identity Foundation</span></span>

<span data-ttu-id="0907c-129">A **base de identidade do Windows** no Lync Server 2013 requer a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação do servidor para o servidor.</span><span class="sxs-lookup"><span data-stu-id="0907c-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="0907c-130">O Windows Server 2008 R2 e o Windows Server 2012 exigem procedimentos diferentes para instalar a base de identidades do Windows.</span><span class="sxs-lookup"><span data-stu-id="0907c-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="0907c-131">Selecione o sistema operacional do seu servidor na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="0907c-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="0907c-132">Windows Server 2008 R2 para Windows Server 2008 R2, você verifica se ele já foi instalado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="0907c-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="0907c-133">Para fazer isso, vá para **Adicionar/remover programas**, **Exibir atualizações instaladas**e procurar em **Windows** para a entrada do **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="0907c-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="0907c-134">Para obter detalhes sobre como instalar o Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="0907c-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="0907c-135">Windows Server 2012 para Windows Server 2012, você usa o **Gerenciador de servidores** para instalar o Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="0907c-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="0907c-136">No **Assistente Adicionar funções e recursos**do Gerenciador de servidores, selecione **recursos**.</span><span class="sxs-lookup"><span data-stu-id="0907c-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="0907c-137">Selecione **Windows Identity Foundation 3,5** na lista.</span><span class="sxs-lookup"><span data-stu-id="0907c-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="0907c-138">Clique em **Avançar**e, em seguida, clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="0907c-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="0907c-139">Software adicional para todos os servidores front-end e servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0907c-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="0907c-140">Todos os servidores de front-end e servidores Standard Edition também devem executar o IIS (serviços de informações da Internet) com determinados módulos.</span><span class="sxs-lookup"><span data-stu-id="0907c-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="0907c-141">Além disso, todos os servidores de front-end e servidores da edição padrão em que a conferência, chamadas de aplicativo, anúncio ou grupos de resposta são implementadas devem executar o tempo de execução do Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="0907c-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="0907c-142">IIS (Serviços de Informações da Internet)</span><span class="sxs-lookup"><span data-stu-id="0907c-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="0907c-143">Os servidores front-end e servidores Standard Edition devem executar o IIS (serviços de informações da Internet), com os seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="0907c-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="0907c-144">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="0907c-144">Static Content</span></span>

  - <span data-ttu-id="0907c-145">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="0907c-145">Default Document</span></span>

  - <span data-ttu-id="0907c-146">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="0907c-146">HTTP Errors</span></span>

  - <span data-ttu-id="0907c-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0907c-147">ASP.NET</span></span>

  - <span data-ttu-id="0907c-148">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="0907c-148">.NET Extensibility</span></span>

  - <span data-ttu-id="0907c-149">Extensões da API de servidor da Internet (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="0907c-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="0907c-150">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="0907c-150">ISAPI Filters</span></span>

  - <span data-ttu-id="0907c-151">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="0907c-151">HTTP Logging</span></span>

  - <span data-ttu-id="0907c-152">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="0907c-152">Logging Tools</span></span>

  - <span data-ttu-id="0907c-153">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="0907c-153">Tracing</span></span>

  - <span data-ttu-id="0907c-154">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="0907c-154">Windows Authentication</span></span>

  - <span data-ttu-id="0907c-155">Requisição de filtro</span><span class="sxs-lookup"><span data-stu-id="0907c-155">Request Filtering</span></span>

  - <span data-ttu-id="0907c-156">Compressão de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="0907c-156">Static Content Compression</span></span>

  - <span data-ttu-id="0907c-157">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="0907c-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="0907c-158">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="0907c-158">IIS Management Console</span></span>

  - <span data-ttu-id="0907c-159">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="0907c-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="0907c-160">Autenticação anônima (instalada por padrão quando o IIS é instalado)</span><span class="sxs-lookup"><span data-stu-id="0907c-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="0907c-161">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="0907c-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="0907c-162">Experiência em tempo de execução do Windows Media Format e área de trabalho do Windows</span><span class="sxs-lookup"><span data-stu-id="0907c-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="0907c-163">**Experiência da área de trabalho do Windows** Todos os servidores front-end e servidores Standard Edition em que a conferência será implantada devem ter o tempo de execução do Windows Media Format instalado, o que, com exceção do Windows Server 2012, é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="0907c-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="0907c-164">O Windows Server 2012 requer o Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="0907c-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="0907c-165">O tempo de execução do Windows Media Format é necessário para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos de estacionamento de chamada, anúncio e resposta são reproduzidos para anúncios e músicas.</span><span class="sxs-lookup"><span data-stu-id="0907c-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="0907c-166">Recomendamos que você instale a experiência da área de trabalho do Windows antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0907c-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="0907c-167">Se o Lync Server 2013 não encontrar esse software no servidor, ele solicitará que você o instale e, em seguida, deverá reiniciar o servidor para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="0907c-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="0907c-168">Software adicional para servidores front-end e servidores Standard Edition em execução no Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0907c-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="0907c-169">Os servidores front-end exigem o .NET 3,5, que não é instalado por padrão no Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="0907c-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="0907c-170">Para instalá-lo, coloque a mídia de instalação do Windows Server 2012 na unidade D e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0907c-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="0907c-171">Para obter detalhes sobre como instalar o .NET 3,5 em servidores que executam o Windows Server 2012, consulte "Microsoft .NET <https://go.microsoft.com/fwlink/p/?linkid=275032>Framework 3,5 considerações de implantação" em.</span><span class="sxs-lookup"><span data-stu-id="0907c-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="0907c-172">Software adicional para directors</span><span class="sxs-lookup"><span data-stu-id="0907c-172">Additional Software for Directors</span></span>

<span data-ttu-id="0907c-173">Os diretores devem executar o IIS (serviços de informações da Internet), com os seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="0907c-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="0907c-174">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="0907c-174">Static Content</span></span>

  - <span data-ttu-id="0907c-175">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="0907c-175">Default Document</span></span>

  - <span data-ttu-id="0907c-176">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="0907c-176">HTTP Errors</span></span>

  - <span data-ttu-id="0907c-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0907c-177">ASP.NET</span></span>

  - <span data-ttu-id="0907c-178">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="0907c-178">.NET Extensibility</span></span>

  - <span data-ttu-id="0907c-179">Extensões da API de servidor da Internet (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="0907c-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="0907c-180">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="0907c-180">ISAPI Filters</span></span>

  - <span data-ttu-id="0907c-181">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="0907c-181">HTTP Logging</span></span>

  - <span data-ttu-id="0907c-182">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="0907c-182">Logging Tools</span></span>

  - <span data-ttu-id="0907c-183">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="0907c-183">Tracing</span></span>

  - <span data-ttu-id="0907c-184">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="0907c-184">Windows Authentication</span></span>

  - <span data-ttu-id="0907c-185">Requisição de filtro</span><span class="sxs-lookup"><span data-stu-id="0907c-185">Request Filtering</span></span>

  - <span data-ttu-id="0907c-186">Compressão de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="0907c-186">Static Content Compression</span></span>

  - <span data-ttu-id="0907c-187">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="0907c-187">IIS Management Console</span></span>

  - <span data-ttu-id="0907c-188">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="0907c-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="0907c-189">Autenticação anônima (instalada por padrão quando o IIS é instalado)</span><span class="sxs-lookup"><span data-stu-id="0907c-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="0907c-190">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="0907c-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="0907c-191">Software adicional para servidores de front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="0907c-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="0907c-192">Os servidores de front-end de chat persistente devem executar o enfileiramento de mensagens (também conhecido como MSMQ), que é um componente do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="0907c-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="0907c-193">Para obter informações sobre como habilitar o MSMQ, [clique aqui.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="0907c-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="0907c-194">Software adicional para servidores Edge</span><span class="sxs-lookup"><span data-stu-id="0907c-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="0907c-195">Os servidores de borda exigem o seguinte software:</span><span class="sxs-lookup"><span data-stu-id="0907c-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="0907c-196">Cada servidor executando o Lync Server 2013 deve ter a versão correta do Windows PowerShell 3,0 instalada.</span><span class="sxs-lookup"><span data-stu-id="0907c-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="0907c-197">Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="0907c-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="0907c-198">O Lync Server requer o Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="0907c-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="0907c-199">Para o Lync Server 2013 instalado no Windows Server 2008 R2, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0907c-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="0907c-200">Para instalá-lo manualmente, baixe a estrutura do Microsoft .NET 4,5 a partir do centro de download da Microsoft em[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="0907c-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="0907c-201">A **base de identidade do Windows** no Lync Server 2013 requer a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação do servidor para o servidor.</span><span class="sxs-lookup"><span data-stu-id="0907c-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="0907c-202">O Windows Server 2008 R2 e o Windows Server 2012 exigem procedimentos diferentes para instalar a base de identidades do Windows.</span><span class="sxs-lookup"><span data-stu-id="0907c-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="0907c-203">Selecione o sistema operacional do seu servidor na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="0907c-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="0907c-204">Windows Server 2008 R2 para Windows Server 2008 R2, você verifica se ele já foi instalado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="0907c-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="0907c-205">Para fazer isso, vá para **Adicionar/remover programas**, **Exibir atualizações instaladas**e procurar em **Windows** para a entrada do **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="0907c-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="0907c-206">Para obter detalhes sobre como instalar o Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="0907c-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="0907c-207">Windows Server 2012 para Windows Server 2012, você usa o **Gerenciador de servidores** para instalar o Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="0907c-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="0907c-208">No **Assistente Adicionar funções e recursos**do Gerenciador de servidores, selecione **recursos**.</span><span class="sxs-lookup"><span data-stu-id="0907c-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="0907c-209">Selecione **Windows Identity Foundation 3,5** na lista.</span><span class="sxs-lookup"><span data-stu-id="0907c-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="0907c-210">Clique em **Avançar**e, em seguida, clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="0907c-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="0907c-211">Não instalar provedores de soquete em camadas em servidores de mídia</span><span class="sxs-lookup"><span data-stu-id="0907c-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="0907c-212">Não instale qualquer software cliente do Microsoft Internet Security and Acceleration (ISA) Server ou qualquer outro software de provedores de serviços em camadas (LSP) Winsock em qualquer servidor front-end ou servidores autônomos de mediação.</span><span class="sxs-lookup"><span data-stu-id="0907c-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="0907c-213">A instalação deste software pode causar um desempenho de tráfego de mídia ruim.</span><span class="sxs-lookup"><span data-stu-id="0907c-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0907c-214">Confira também</span><span class="sxs-lookup"><span data-stu-id="0907c-214">See Also</span></span>


[<span data-ttu-id="0907c-215">Requisitos de software de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0907c-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

