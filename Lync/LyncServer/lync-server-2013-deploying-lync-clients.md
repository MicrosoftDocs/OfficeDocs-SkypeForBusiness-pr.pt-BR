---
title: 'Lync Server 2013: Implantando clientes do Lync'
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
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="fd597-102">Implantando clientes do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd597-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fd597-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fd597-104">O Lync 2013 introduz uma abordagem diferente para a implantação do cliente.</span><span class="sxs-lookup"><span data-stu-id="fd597-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="fd597-105">Em uma partida de versões anteriores, o Lync 2013 não tem mais seu próprio instalador.</span><span class="sxs-lookup"><span data-stu-id="fd597-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="fd597-106">Em vez disso, o Lync está incluído no programa de instalação do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="fd597-107">Para implantar o Lync 2013 em seus usuários, você pode usar os métodos de instalação e ferramentas de personalização do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="fd597-108">**Office 2013 o Windows Installer** é um pacote de instalação baseado no Windows Installer que consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="fd597-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="fd597-109">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="fd597-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="fd597-110">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="fd597-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="fd597-111">Os tópicos desta seção descrevem como usar e personalizar o instalador do Windows do Office 2013 para implantar o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="fd597-112">O **Office 2013 clique para executar** é um programa de instalação que transmite os arquivos de instalação do Office para o usuário a partir do portal do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd597-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="fd597-113">Os administradores podem personalizar a instalação utilizando a Ferramenta de Implantação do Office para Clique para Executar.</span><span class="sxs-lookup"><span data-stu-id="fd597-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="fd597-114">Como o Office 2013 com Clique para executar é usado principalmente no ambiente do Microsoft Office 365, esse método de instalação não está descrito em detalhes nesta seção.</span><span class="sxs-lookup"><span data-stu-id="fd597-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="fd597-115">Informações detalhadas sobre como usar e personalizar a instalação do clique para executar estão disponíveis na documentação do Office 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="fd597-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="fd597-116">Os administradores também podem baixar os arquivos de código-fonte do Office 2013 e os arquivos de idioma do Office para um local local, o que é útil quando você deseja minimizar a demanda na rede ou impedir que os usuários instalem o software da Internet por causa de requisitos de segurança corporativa.</span><span class="sxs-lookup"><span data-stu-id="fd597-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="fd597-117">Os tópicos desta seção se concentram em como implantar clientes usando o instalador baseado em MSI do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="fd597-118">Sua referência principal deve ser a documentação do Office 2013 Resource Kit, que descreve em detalhes como preparar sua infraestrutura, personalizar a instalação e implantar o Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="fd597-119">No entanto, você deve usar a documentação do Office em conjunto com os tópicos desta seção, que apontam as considerações de implantação específicas do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="fd597-120">O suplemento de reunião online do Lync 2013, que dá suporte ao gerenciamento de reuniões dentro do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fd597-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="fd597-121">O programa de instalação do Office 2013 não desinstala versões anteriores do Lync ou do Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="fd597-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="fd597-122">O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator</span><span class="sxs-lookup"><span data-stu-id="fd597-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd597-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fd597-123">In This Section</span></span>

  - [<span data-ttu-id="fd597-124">Personalizando a instalação do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="fd597-125">Personalizando o comportamento do Lync e a interface do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="fd597-126">Personalizando o suplemento de reunião online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="fd597-127">Configurando a página de ingresso na reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="fd597-128">Configurando as versões de cliente com suporte no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="fd597-129">Configurando o modo de privacidade de presença avançada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd597-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

