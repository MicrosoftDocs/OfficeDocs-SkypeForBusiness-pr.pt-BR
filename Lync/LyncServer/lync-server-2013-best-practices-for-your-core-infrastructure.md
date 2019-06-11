---
title: 'Lync Server 2013: práticas recomendadas para a sua infraestrutura principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="33876-102">Práticas recomendadas para a sua infraestrutura principal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33876-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33876-103">_**Tópico da última modificação:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="33876-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="33876-104">Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="33876-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="33876-105">Essas práticas se beneficiam não só na infra-estrutura do Microsoft Lync Server 2013, mas também em toda a sua rede.</span><span class="sxs-lookup"><span data-stu-id="33876-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="33876-106">Se você não implementou essas práticas, recomendamos que faça isso antes de implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33876-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="33876-107">Para ajudar a proteger os servidores em sua implantação do Lync Server 2013 contra danos acidentais ou intencionais que podem resultar em tempo de inatividade, tome as seguintes precauções:</span><span class="sxs-lookup"><span data-stu-id="33876-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="33876-108">Mantenha os servidores atualizados com atualizações de segurança.</span><span class="sxs-lookup"><span data-stu-id="33876-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="33876-109">A assinatura do Microsoft Security Notification Service ajuda a garantir que você receba notificações imediatas de versões de boletim de segurança de qualquer produto da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33876-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="33876-110">Para se inscrever, acesse o site de notificações técnicas [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)de segurança da Microsoft em.</span><span class="sxs-lookup"><span data-stu-id="33876-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="33876-111">Verifique se os direitos de acesso estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="33876-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="33876-p103">Mantenha os servidores em um ambiente físico que impeça o acesso não autorizado. Verifique se o software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do seu aplicativo antivírus para manter as assinaturas de vírus atuais.</span><span class="sxs-lookup"><span data-stu-id="33876-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="33876-116">Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instalou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33876-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="33876-117">Criptografe os sistemas operacionais e as unidades de disco em que os dados estiverem armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir o controle constante e completo dos servidores, o isolamento típico total e o descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.</span><span class="sxs-lookup"><span data-stu-id="33876-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="33876-118">Desabilite todas as portas de DMA (Acesso Remoto Direto à Memória) externas do servido, a menos que você possa garantir o controle muito rigoroso sobre o acesso físico aos servidores.</span><span class="sxs-lookup"><span data-stu-id="33876-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="33876-119">Ataques baseados em DMA, que podem ser iniciados de modo razoavelmente fácil, podem expor informações confidenciais, como chaves de criptografia privada.</span><span class="sxs-lookup"><span data-stu-id="33876-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

