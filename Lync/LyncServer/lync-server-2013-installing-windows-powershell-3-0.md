---
title: 'Lync Server 2013: Instalando o Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a799ba54fe7677ed2ccfa8051f295b2b775cdc0e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="473a7-102">Instalando o Windows PowerShell 3,0 para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="473a7-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="473a7-103">_**Última modificação do tópico:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="473a7-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="473a7-104">Para implantar o Lync Server 2013 com êxito, você precisará do Windows PowerShell 3,0 em cada computador que faz parte da sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="473a7-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="473a7-105">Agora, para sistemas que executam o Windows Server 2012 ou o Windows Server 2012 R2, você não precisa fazer nada aqui e pode prosseguir para o próximo estágio de implantação, porque o PowerShell 3,0 está incluído nesses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="473a7-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="473a7-106">Mas para sistemas executando o Windows Server 2008 R2 SP1, você precisará instalar o PowerShell 3,0 como pré-requisito antes de instalar o Lync Server 2013 ou as coisas não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="473a7-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="473a7-107">Para instalar o PowerShell 3,0, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="473a7-107">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="473a7-108">Este é um link direto para a página de download do PowerShell 3,0, juntamente com informações relacionadas à instalação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="473a7-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="473a7-109">Depois de fazer a instalação, ou se você só quiser verificar e ter certeza antes de continuar com a implantação do Lync Server, confirmar se o PowerShell 3,0 está em um servidor é bem simples se você fizer isso:</span><span class="sxs-lookup"><span data-stu-id="473a7-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="473a7-110">No servidor que você deseja verificar, escolha **Iniciar**, clique em **todos os programas**, em **acessórios**, clique em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="473a7-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="473a7-111">No console do Windows PowerShell, digite o seguinte comando no prompt de comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="473a7-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="473a7-112">Se o Windows PowerShell 3,0 estiver instalado, você verá a saída parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="473a7-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

