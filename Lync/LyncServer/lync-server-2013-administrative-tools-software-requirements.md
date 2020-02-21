---
title: 'Lync Server 2013: requisitos de software de ferramentas administrativas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d1532acc21bc788adc8e52bfd1d562509e105ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="8b5a6-102">Requisitos de software de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b5a6-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b5a6-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8b5a6-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8b5a6-104">Este tópico descreve o software necessário para instalar e usar as ferramentas administrativas do Lync Server 2013, além dos requisitos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="8b5a6-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8b5a6-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="8b5a6-106">A edição de 64 bits do Microsoft .NET Framework 4,5 é necessária para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="8b5a6-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="8b5a6-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="8b5a6-108">O Windows PowerShell 3,0 é necessário para executar qualquer componente do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8b5a6-109">Para obter mais informações, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="8b5a6-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="8b5a6-110">Windows Installer versão 4.5</span><span class="sxs-lookup"><span data-stu-id="8b5a6-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="8b5a6-111">O Lync Server 2013 usa a tecnologia do Windows Installer para instalar, desinstalar e manter várias funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="8b5a6-112">O Windows Installer versão 4.5 está disponível como um componente redistribuível para o sistema operacional Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="8b5a6-113">O Windows Installer 4,5 acompanha o Windows Server 2012 R2, o Windows Server 2012 e o Windows Server 2008 R2, o que significa que você não precisa baixar o utilitário para qualquer computador que esteja executando o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="8b5a6-114">(O Lync Server 2013 só pode ser instalado em computadores que executam o Windows Server 2012 R2, o Windows Server 2012 ou o Windows Server 2008 R2.)</span><span class="sxs-lookup"><span data-stu-id="8b5a6-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="8b5a6-115">No entanto, se você quiser instalar o Shell de gerenciamento do Lync Server ou o construtor de topologias do Lync Server em uma estação de trabalho do administrador, talvez seja necessário baixar o Windows Installer 4,5.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="8b5a6-116">Esse utilitário é fornecido com o Windows 7 e o Windows 2008 R2, mas não com nenhuma versão anterior do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="8b5a6-117">Você pode baixar o Windows Installer 4,5 do centro de download da <https://go.microsoft.com/fwlink/p/?linkid=197395>Microsoft em.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="8b5a6-118">Plug-in do navegador do Microsoft Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="8b5a6-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="8b5a6-119">O painel de controle do Lync Server 2013 é uma ferramenta baseada na Web e exige que você instale a versão mais recente do plug-in do navegador do Microsoft Silverlight 5.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="8b5a6-120">Quando você iniciar o painel de controle do Lync Server 2013, se esse software não estiver instalado ou se uma versão anterior estiver instalada, o painel de controle do Lync Server 2013 solicitará a instalação da versão necessária.</span><span class="sxs-lookup"><span data-stu-id="8b5a6-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b5a6-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="8b5a6-121">See Also</span></span>


[<span data-ttu-id="8b5a6-122">Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b5a6-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="8b5a6-123">Requisitos de infraestrutura de ferramentas administrativas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b5a6-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="8b5a6-124">Direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b5a6-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

