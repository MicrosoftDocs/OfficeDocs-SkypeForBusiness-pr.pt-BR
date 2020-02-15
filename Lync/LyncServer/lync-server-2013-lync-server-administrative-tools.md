---
title: 'Lync Server 2013: ferramentas administrativas do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6de54e91129351a153c9cf4e08925d62eeb342c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="f1935-102">Ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1935-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f1935-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f1935-104">Este tópico descreve as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1935-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="f1935-105">As ferramentas administrativas são instaladas por padrão em cada servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="f1935-106">Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados.</span><span class="sxs-lookup"><span data-stu-id="f1935-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="f1935-107">Para obter os procedimentos para instalar as ferramentas administrativas, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="f1935-108">Para obter os procedimentos para abrir as ferramentas para executar tarefas de gerenciamento, consulte [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="f1935-109">Certifique-se de revisar os requisitos de direitos de infra-estrutura, sistema operacional, software e administrador antes de instalar ou usar as ferramentas administrativas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="f1935-110">Para obter detalhes sobre os requisitos de infraestrutura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="f1935-111">Para obter detalhes sobre os requisitos de sistema operacional e software para instalar as ferramentas administrativas do Lync Server, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [suporte e requisitos adicionais do servidor no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="f1935-112">As permissões e os direitos de usuário necessários para instalar e usar as ferramentas são descritos em [direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="f1935-113">As ferramentas administrativas consistem no seguinte:</span><span class="sxs-lookup"><span data-stu-id="f1935-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="f1935-114">**Assistente de implantação do Lync Server**   use para implantar o Lync Server e instalar todas as ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="f1935-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="f1935-115">**O Construtor**   de topologias do Lync Server usa para definir componentes em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f1935-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="f1935-116">**Painel de controle do Lync Server**   use para o gerenciamento contínuo da sua implantação usando uma interface baseada na Web.</span><span class="sxs-lookup"><span data-stu-id="f1935-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="f1935-117">**Shell de gerenciamento do Lync Server**   use para o gerenciamento contínuo da sua implantação usando a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f1935-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="f1935-118">**A ferramenta**   de registro em log do Lync Server é usada para solucionar problemas em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f1935-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="f1935-119">**O serviço**   de registro em log centralizado coleta logs e rastreamento de arquivos de um computador, pool, site ou global.</span><span class="sxs-lookup"><span data-stu-id="f1935-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="f1935-120">Selecione e defina cenários que contenham provedores, sinalizadores e níveis de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="f1935-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="f1935-121">O registro em log é coletado, agregado e exibido com ferramentas como qualquer ferramenta baseada em texto ou Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="f1935-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="f1935-122">Você pode gerenciar sua implantação usando principalmente o construtor de topologias e o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="f1935-123">Assistente de Implantação</span><span class="sxs-lookup"><span data-stu-id="f1935-123">Deployment Wizard</span></span>

<span data-ttu-id="f1935-124">Você deve usar o assistente de implantação do Lync Server incluído na mídia de instalação para instalar todas as ferramentas administrativas em um computador em que você ainda não tenha instalado o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="f1935-125">Durante o processo de instalação das ferramentas administrativas, o assistente de implantação do Lync Server é instalado localmente junto com outras ferramentas para que você possa usá-lo posteriormente para instalar arquivos para componentes adicionais ou remover arquivos de componentes que não deseja no computador.</span><span class="sxs-lookup"><span data-stu-id="f1935-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="f1935-126">Para obter detalhes sobre como executar o assistente de implantação do Lync Server pela primeira vez na mídia de instalação do Lync Server, consulte [install Lync server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="f1935-127">Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="f1935-127">Topology Builder</span></span>

<span data-ttu-id="f1935-128">Para obter detalhes sobre as tarefas de implantação que você pode executar usando o construtor de topologias, consulte a documentação de implantação de cada função de servidor.</span><span class="sxs-lookup"><span data-stu-id="f1935-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="f1935-129">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="f1935-129">Lync Server Control Panel</span></span>

<span data-ttu-id="f1935-130">Você pode usar o painel de controle do Lync Server 2013 para executar a maioria das tarefas administrativas necessárias para gerenciar e manter o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1935-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="f1935-131">O painel de controle do Lync Server oferece uma interface gráfica do usuário (GUI) para gerenciar a configuração dos servidores que executam o Lync Server, além dos usuários, clientes e dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1935-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="f1935-132">O Shell de gerenciamento do Lync Server usa o painel de controle do Lync Server como o mecanismo subjacente para executar a configuração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="f1935-133">O painel de controle do Lync Server é instalado automaticamente em todos os servidores front-end do Lync Server ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f1935-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="f1935-134">Nesta versão, os Servidores de Borda são administrados remotamente.</span><span class="sxs-lookup"><span data-stu-id="f1935-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="f1935-135">Você também pode instalar o painel de controle do Lync Server em outro computador, como um console de gerenciamento do qual você deseja gerenciar centralmente o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="f1935-136">Para obter detalhes, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1935-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f1935-137">Para definir as configurações usando o painel de controle do Lync Server, você deve estar conectado usando uma conta atribuída à função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f1935-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="f1935-138">Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Lync Server 2013, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1935-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f1935-139">Para definir as configurações usando o painel de controle do Lync Server, você também deve usar um computador com uma resolução de tela mínima de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="f1935-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="f1935-140">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="f1935-140">Lync Server Management Shell</span></span>

<span data-ttu-id="f1935-141">No Lync Server, o Shell de gerenciamento do Lync Server fornece um novo método de administração e gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1935-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="f1935-142">O Shell de gerenciamento do Lync Server é uma interface de gerenciamento poderosa, criada na interface de linha de comando do Windows PowerShell, que inclui um conjunto abrangente de cmdlets específicos para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="f1935-143">Com o Shell de gerenciamento do Lync Server, você obtém um conjunto avançado de controles de configuração e automação.</span><span class="sxs-lookup"><span data-stu-id="f1935-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="f1935-144">O construtor de topologias e o painel de controle do Lync Server implementam subconjuntos desses cmdlets para dar suporte ao gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="f1935-145">O Shell de gerenciamento do Lync Server inclui cmdlets para todas as tarefas de administração do Lync Server e você pode usar os cmdlets individualmente para gerenciar sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f1935-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="f1935-146">Para obter detalhes, consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) ou a ajuda de linha de comando para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1935-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="f1935-147">Ferramenta de Log</span><span class="sxs-lookup"><span data-stu-id="f1935-147">Logging Tool</span></span>

<span data-ttu-id="f1935-148">A ferramenta de registro em log do Lync Server facilita a solução de problemas ao capturar informações de log e rastreamento do produto enquanto o produto está em execução.</span><span class="sxs-lookup"><span data-stu-id="f1935-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="f1935-149">Você pode usar a ferramenta para executar sessões de depuração em qualquer função de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1935-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="f1935-150">Para obter detalhes sobre a ferramenta de registro em log, consulte a documentação da ferramenta de registro em log [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)do Lync Server 2010 na biblioteca do TechNet em.</span><span class="sxs-lookup"><span data-stu-id="f1935-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f1935-151">O serviço de registro em log centralizado é recomendado para todas as coletas de log sobre a ferramenta de log do Lync Server em todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="f1935-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="f1935-152">A ferramenta de log do Lync Server ainda funcionará, mas interferirá ou será renderizada principalmente se o serviço de registro em log centralizado já estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="f1935-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="f1935-153">Você deve usar somente o serviço de registro em log centralizado ou a ferramenta de log do Lync Server, mas nunca simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f1935-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="f1935-154">Para obter mais informações sobre o serviço de registro em log centralizado e por que você deve usá-lo exclusivamente, consulte <A href="lync-server-2013-using-the-centralized-logging-service.md">usando o serviço de registro em log centralizado no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1935-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1935-155">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f1935-155">In This Section</span></span>

  - [<span data-ttu-id="f1935-156">Requisitos de infraestrutura de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="f1935-157">Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="f1935-158">Requisitos de software de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="f1935-159">Direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="f1935-160">Requisitos para publicar uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="f1935-161">Instalar ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="f1935-162">Abrir as ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="f1935-163">Resolver problemas do painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="f1935-164">Usando o serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1935-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="f1935-165">See Also</span></span>


[<span data-ttu-id="f1935-166">Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1935-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

