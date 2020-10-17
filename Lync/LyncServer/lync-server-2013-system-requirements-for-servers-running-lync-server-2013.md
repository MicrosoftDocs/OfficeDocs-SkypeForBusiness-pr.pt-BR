---
title: 'Lync Server 2013: requisitos de sistema para servidores que executam o Lync Server 2013'
description: 'Lync Server 2013: requisitos de sistema para servidores que executam o Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562647"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="f4122-103">Requisitos do sistema para servidores que executam o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4122-103">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4122-104">_**Última modificação do tópico:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="f4122-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f4122-105">Para obter detalhes sobre os requisitos de hardware, consulte <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4122-105">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f4122-106">Os servidores Standard Edition e Enterprise Edition compartilham os mesmos requisitos de software.</span><span class="sxs-lookup"><span data-stu-id="f4122-106">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="f4122-107">Os servidores que executam o Lync Server 2013, Enterprise Edition são destinados a grandes organizações como a implantação organizacional principal.</span><span class="sxs-lookup"><span data-stu-id="f4122-107">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="f4122-108">O servidor Enterprise Edition foi projetado para acomodar aproximadamente 80.000 usuários por pool.</span><span class="sxs-lookup"><span data-stu-id="f4122-108">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="f4122-109">Os servidores que executam o Lync Server 2013, Standard Edition são destinados a organizações menores e locais remotos da implantação da organização principal.</span><span class="sxs-lookup"><span data-stu-id="f4122-109">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="f4122-110">Um par de servidores Standard Edition pode suportar até 5.000 usuários..</span><span class="sxs-lookup"><span data-stu-id="f4122-110">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="f4122-111">Para obter detalhes sobre as diferenças entre servidores Standard Edition e servidores Enterprise Edition, consulte [Deployment Overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4122-111">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="f4122-112">Instalação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f4122-112">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f4122-113">O Lync Server 2013 está disponível somente em uma edição de 64 bits, que requer hardware de 64 bits e uma edição de 64 bits do sistema operacional Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f4122-113">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="f4122-114">Uma edição de 32 bits do Lync Server 2013 não está disponível nesta versão.</span><span class="sxs-lookup"><span data-stu-id="f4122-114">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="f4122-115">O Standard Edition e o servidor Enterprise Edition podem usar qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="f4122-115">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="f4122-116">Windows Server 2008 R2 SP1 ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="f4122-116">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="f4122-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f4122-117">Windows Server 2012</span></span>

  - <span data-ttu-id="f4122-118">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f4122-118">Windows Server 2012 R2</span></span>

<span data-ttu-id="f4122-119">Instale o software do sistema operacional no servidor Standard Edition ou no servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f4122-119">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="f4122-120">Aplique todas as atualizações para deixar o sistema operacional com a atualização mais recente e a atualização necessária de nível consistente com os padrões da organização.</span><span class="sxs-lookup"><span data-stu-id="f4122-120">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="f4122-121">Para obter mais detalhes sobre os requisitos de operação, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f4122-121">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="f4122-122">A atualização in-loco do sistema operacional não é suportada pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4122-122">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="f4122-123">Você deve implantar um pool separado e migrar os usuários para o novo pool com um sistema operacional diferente.</span><span class="sxs-lookup"><span data-stu-id="f4122-123">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f4122-124">Para que o Lync Server 2013 funcione no Windows Server 2012 R2, talvez seja necessário alterar o valor de uma chave de registro no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f4122-124">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="f4122-125">Essa alteração pode ser necessária para que os certificados funcionem corretamente e para que os clientes possam se registrar em aparelhos de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="f4122-125">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="f4122-126">Para obter mais informações, consulte <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .</span><span class="sxs-lookup"><span data-stu-id="f4122-126">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="f4122-127">Software adicional para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4122-127">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="f4122-128">Além das atualizações necessárias para o sistema operacional, o Lync Server 2013 requer funções de sistema operacional, recursos e software a operar.</span><span class="sxs-lookup"><span data-stu-id="f4122-128">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="f4122-129">Para obter detalhes sobre o software adicional que deve ser instalado antes de publicar sua topologia e como instalar o Lync Server 2013, consulte [Additional Software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f4122-129">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="f4122-130">Software adicional necessário para todas as funções de servidor</span><span class="sxs-lookup"><span data-stu-id="f4122-130">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="f4122-131">Em todas as funções de servidor, você também deve verificar se a interface de linha de comando do Windows PowerShell 3,0 e o Microsoft .NET Framework 4,5 estão instalados.</span><span class="sxs-lookup"><span data-stu-id="f4122-131">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="f4122-132">Além disso, a interface de linha de comando 3,0 do Windows PowerShell e o Microsoft .NET Framework 4,5 são necessários em qualquer computador em que você executará as ferramentas administrativas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4122-132">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="f4122-133">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f4122-133">Windows PowerShell 3.0</span></span>

<span data-ttu-id="f4122-134">O Lync Server 2013 requer que você instale o Windows PowerShell 3,0 em cada computador que fará parte da sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4122-134">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="f4122-135">Para obter detalhes sobre como instalar o Windows PowerShell 3,0, consulte [instalando o Windows powershell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="f4122-135">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f4122-136">No Windows Server &nbsp; 2008 &nbsp; R2 com SP1, a interface de linha de comando do Windows PowerShell 3,0 não pode ser instalada antes da instalação do Microsoft .net Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="f4122-136">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="f4122-137">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f4122-137">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="f4122-138">Ao instalar o Microsoft .NET Framework 4,5 em servidores que executarão o Lync Server 2013 no Windows Server 2012 ou Windows Server 2012 R2, você deve executar uma etapa adicional.</span><span class="sxs-lookup"><span data-stu-id="f4122-138">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="f4122-139">Após a instalação do .NET Framework 4,5, use o Gerenciador do servidor para instalar a ativação HTTP.</span><span class="sxs-lookup"><span data-stu-id="f4122-139">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="f4122-140">**Para instalar a ativação HTTP do .NET 4,5 no Windows Server 2012 ou no Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="f4122-140">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="f4122-141">No menu **Iniciar** , clique em **programas**, em **Ferramentas administrativas**e, em seguida, clique em **Gerenciador do servidor**.</span><span class="sxs-lookup"><span data-stu-id="f4122-141">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="f4122-142">No Gerenciador de servidores, em **Resumo de recursos**, escolha **Adicionar recursos**.</span><span class="sxs-lookup"><span data-stu-id="f4122-142">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="f4122-143">Expanda o **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="f4122-143">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="f4122-144">Selecione **ativação do WCF** , se ainda não estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="f4122-144">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="f4122-145">Em seguida, selecione **ativação de http**.</span><span class="sxs-lookup"><span data-stu-id="f4122-145">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="f4122-146">Clique em **Avançar** e siga as instruções para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="f4122-146">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

