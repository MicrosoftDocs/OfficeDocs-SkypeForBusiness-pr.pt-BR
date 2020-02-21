---
title: 'Lync Server 2013: instalar ferramentas administrativas do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8805c82c26eb97da8537b33cda8346f5942de1c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="905f1-102">Instalar ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="905f1-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="905f1-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="905f1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="905f1-104">Este tópico descreve como instalar as ferramentas administrativas que você precisa usar para implantar e gerenciar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="905f1-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="905f1-105">As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="905f1-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="905f1-106">Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados.</span><span class="sxs-lookup"><span data-stu-id="905f1-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="905f1-107">É altamente recomendável que você instale as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que a implantação do Lync Server 2013 que você está criando porque fazendo isso, verifique se as etapas de preparação dos serviços de domínio do Active Directory já estão concluído, permitindo que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="905f1-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="905f1-108">Certifique-se de revisar os requisitos de direitos de infra-estrutura, sistema operacional, software e administrador antes de instalar ou usar as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="905f1-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="905f1-109">Para obter detalhes sobre os requisitos de infraestrutura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="905f1-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="905f1-110">Para obter detalhes sobre os requisitos de sistema operacional e software para instalar as ferramentas administrativas do Lync Server 2013, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [suporte e requisitos adicionais do servidor no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="905f1-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="905f1-111">Para obter detalhes sobre os direitos e permissões de usuário necessários para instalar e usar as ferramentas, consulte [direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="905f1-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="905f1-112">Se a sua organização requer a localização de Serviços de Informações da Internet (IIS) e de todos os serviços web em uma unidade diferente da unidade do sistema, você pode alterar o caminho do local de instalação para os arquivos do Lync Server na caixa de diálogo de instalação.</span><span class="sxs-lookup"><span data-stu-id="905f1-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="905f1-113">Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="905f1-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="905f1-114">Para instalar as ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="905f1-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="905f1-p104">Faça logon como um administrador local (requisito mínimo) no computador onde você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão no sistema operacional Windows Vista ou Windows 7 e o UAC (Controle da Conta de Usuário) estiver habilitado, será solicitado para informar o nome de usuário e a senha do administrador local ou de um domínio equivalente.</span><span class="sxs-lookup"><span data-stu-id="905f1-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="905f1-117">Localize a mídia de instalação no computador e clique duas vezes em \\Setup\\AMD64\\. exe.</span><span class="sxs-lookup"><span data-stu-id="905f1-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="905f1-118">Se você receber uma solicitação para instalar o Microsoft Visual C++ 2008 distribuível, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="905f1-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="905f1-119">Na página **local de instalação do Microsoft Lync Server 2013** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="905f1-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="905f1-120">Altere este caminho para outro local ou unidade se precisa dos arquivos instalados em outra localização.</span><span class="sxs-lookup"><span data-stu-id="905f1-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="905f1-121">Se sua organização exigir que você localize os serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo configuração.</span><span class="sxs-lookup"><span data-stu-id="905f1-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="905f1-122">Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 será implantado também nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="905f1-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="905f1-p107">Na página **Acordo de licença do usuário final**, revise os termos de licença, clique em **Eu aceito** e em **OK**. Esta etapa é obrigatória antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="905f1-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="905f1-125">Na página **Microsoft Lync Server 2013 – assistente de implantação** , clique em **instalar ferramentas do administrador**.</span><span class="sxs-lookup"><span data-stu-id="905f1-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="905f1-126">Quando a instalação for concluída com êxito, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="905f1-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="905f1-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="905f1-127">See Also</span></span>


[<span data-ttu-id="905f1-128">Abrir as ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="905f1-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="905f1-129">Ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="905f1-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

