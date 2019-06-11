---
title: 'Lync Server 2013: Implantando o portal da Web administrativo do sistema de salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fc5e7d0f136481ddce5d34de41268cb224822e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="fc1f5-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc1f5-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc1f5-103">_**Tópico da última modificação:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="fc1f5-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="fc1f5-104">O portal da Web administrativo do Microsoft Lync Server 2013 Lync (Microsoft Lync Server) é um portal da Web que as organizações podem usar para manter suas salas de conferência do sistema de sala do Lync.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="fc1f5-105">Os administradores podem usar o portal da Web administrativo do LRS para monitorar a integridade do LRS, por exemplo, monitorando dispositivos de áudio/vídeo conectados.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="fc1f5-106">Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="fc1f5-107">O portal da Web administrativo do LRS é implantado em cada servidor front-end do Lync.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="fc1f5-108">Este guia fornece instruções para administradores sobre como instalar e configurar o portal da Web administrativo do LRS.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="fc1f5-109">Destina-se a administradores que têm conhecimento da administração do Lync Server e que têm direitos de usuário de administrador para modificar a topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="fc1f5-110">Depois que o portal da Web administrativo do LRS for implantado no servidor, os administradores poderão verificar o status de todas as salas do LRS fazendo logon no site de seus próprios computadores ou laptops.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fc1f5-111">Ao instalar o portal da Web administrativo do LRS em uma implantação do Microsoft Lync Server 2013, você deve usar o <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">portal da Web administrativo do sistema de sala do Microsoft Lync para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="fc1f5-112">Uma nova versão do portal da Web administrativo do LRS está disponível para o Skype for Business Server 2015, mas você não deve instalar essa versão, a menos que tenha implantado o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="fc1f5-113">Baixe o <A href="http://go.microsoft.com/fwlink/?linkid=544807">portal da Web administrativo do sistema de sala do Microsoft Lync para o Skype for Business Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fc1f5-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fc1f5-114">In This Section</span></span>

[<span data-ttu-id="fc1f5-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="fc1f5-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="fc1f5-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc1f5-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="fc1f5-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc1f5-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc1f5-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="fc1f5-118">See Also</span></span>


[<span data-ttu-id="fc1f5-119">Implantando conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc1f5-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

