---
title: 'Lync Server 2013: Implantando o portal da Web administrativo do sistema de salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945532f4f0514263ed0d72e00ac5224aa6d7120b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="06297-102">Implantando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06297-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06297-103">_**Última modificação do tópico:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="06297-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="06297-104">O portal da Web administrativo do Microsoft Lync Server 2013 Lync Room System (LRS) é um portal da Web que as organizações podem usar para manter suas salas de conferência do sistema de salas do Lync.</span><span class="sxs-lookup"><span data-stu-id="06297-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="06297-105">Os administradores podem usar o portal da Web administrativo do LRS para monitorar a integridade do LRS, por exemplo, monitorando dispositivos de áudio/vídeo conectados.</span><span class="sxs-lookup"><span data-stu-id="06297-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="06297-106">Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="06297-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="06297-107">O portal da Web administrativo do LRS é implantado em todos os servidores front-end do Lync.</span><span class="sxs-lookup"><span data-stu-id="06297-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="06297-108">Este guia fornece instruções para os administradores sobre como instalar e configurar o portal da Web administrativo do LRS.</span><span class="sxs-lookup"><span data-stu-id="06297-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="06297-109">Destina-se a administradores que têm conhecimento da administração do Lync Server e que têm direitos de usuário de administrador para modificar a topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06297-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="06297-110">Depois que o portal da Web administrativo do LRS é implantado no servidor, os administradores podem verificar o status de todas as salas do LRS fazendo logon no site de seus próprios computadores ou laptops.</span><span class="sxs-lookup"><span data-stu-id="06297-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="06297-111">Ao instalar o portal da Web administrativo do LRS em uma implantação do Microsoft Lync Server 2013, você deve usar o <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">portal da Web administrativo do sistema de salas do Microsoft Lync para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="06297-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="06297-112">Uma nova versão do portal da Web administrativo do LRS está disponível para o Skype for Business Server 2015, mas você não deve instalar essa versão, a menos que tenha implantado o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="06297-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="06297-113">Baixe o <A href="http://go.microsoft.com/fwlink/?linkid=544807">portal da Web administrativo do sistema de salas do Microsoft Lync para o Skype for Business Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="06297-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="06297-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="06297-114">In This Section</span></span>

[<span data-ttu-id="06297-115">Configurando seu ambiente do Lync Server 2013 para o portal da Web administrativo do sistema de salas do Lync</span><span class="sxs-lookup"><span data-stu-id="06297-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="06297-116">Instalando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06297-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="06297-117">Usando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06297-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06297-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="06297-118">See Also</span></span>


[<span data-ttu-id="06297-119">Implantando a conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06297-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

