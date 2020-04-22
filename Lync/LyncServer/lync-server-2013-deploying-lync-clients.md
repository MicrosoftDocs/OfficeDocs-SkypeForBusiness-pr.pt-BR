---
title: 'Lync Server 2013: Implantando clientes Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad8735834ab004753444849c529cb4ceec18c16
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="17cf7-102">Implantando clientes Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17cf7-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="17cf7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="17cf7-104">O Lync 2013 introduz uma abordagem diferente para a implantação do cliente.</span><span class="sxs-lookup"><span data-stu-id="17cf7-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="17cf7-105">Em uma partida de versões anteriores, o Lync 2013 não tem mais seu próprio instalador.</span><span class="sxs-lookup"><span data-stu-id="17cf7-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="17cf7-106">Em vez disso, o Lync está incluído no programa de instalação do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="17cf7-107">Para implantar o Lync 2013 em seus usuários, você pode usar os métodos de instalação e as ferramentas de personalização do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="17cf7-108">O **Office 2013 Windows Installer** é um pacote de instalação baseado no Windows Installer que consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="17cf7-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="17cf7-109">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="17cf7-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="17cf7-110">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="17cf7-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="17cf7-111">Os tópicos desta seção descrevem como usar e personalizar o Office 2013 Windows Installer para implantar o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="17cf7-112">O **Office 2013 clique para executar** é um programa de instalação que transmite arquivos de instalação do Office para o usuário a partir do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17cf7-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft 365 admin center.</span></span> <span data-ttu-id="17cf7-113">Os administradores podem personalizar a instalação utilizando a Ferramenta de Implantação do Office para Clique para Executar.</span><span class="sxs-lookup"><span data-stu-id="17cf7-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="17cf7-114">Como o Office 2013 clique para executar é usado principalmente no ambiente do Microsoft Office 365, este método de instalação não é descrito em detalhes nesta seção.</span><span class="sxs-lookup"><span data-stu-id="17cf7-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="17cf7-115">Informações detalhadas sobre como usar e personalizar a instalação clique para executar estão disponíveis na documentação do kit de recursos do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="17cf7-116">Os administradores também podem baixar os arquivos de programa e de origem do Office 2013 clique para executar em um local local, o que é útil quando você deseja minimizar a demanda na rede ou impedir que os usuários instalem software da Internet por causa dos requisitos de segurança corporativos.</span><span class="sxs-lookup"><span data-stu-id="17cf7-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="17cf7-117">Os tópicos desta seção concentram-se em como implantar clientes usando o instalador baseado em MSI do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="17cf7-118">Sua referência principal deve ser a documentação do kit de recursos do Office 2013, que descreve detalhadamente como preparar sua infraestrutura, personalizar a instalação e implantar o Office 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="17cf7-119">No entanto, você deve usar a documentação do Office em conjunto com os tópicos nesta seção, que apontam as considerações de implantação específicas para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="17cf7-120">O suplemento de reunião online do Lync 2013, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="17cf7-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="17cf7-121">O programa de instalação do Office 2013 não desinstala versões anteriores do Lync ou Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="17cf7-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="17cf7-122">O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator</span><span class="sxs-lookup"><span data-stu-id="17cf7-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="17cf7-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="17cf7-123">In This Section</span></span>

  - [<span data-ttu-id="17cf7-124">Personalizando a instalação do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="17cf7-125">Personalizando o comportamento do Lync e a interface do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="17cf7-126">Personalizando o suplemento reunião online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="17cf7-127">Configurando a página de ingresso na reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="17cf7-128">Configurando as versões de cliente suportadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="17cf7-129">Configurando o modo de privacidade de presença avançada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cf7-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

