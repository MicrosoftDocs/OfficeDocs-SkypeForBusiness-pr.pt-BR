---
title: 'Lync Server 2013: práticas recomendadas para sua infraestrutura principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce25a61ef74c38b5455b7b8d437b43d24e12397e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="91c22-102">Práticas recomendadas para sua infraestrutura principal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c22-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91c22-103">_**Última modificação do tópico:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="91c22-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="91c22-104">Provavelmente, você já executou etapas para designar a tolerância a falha em seu sistema, usando práticas como a garantia da redundância de hardware, proteção contra perda de energia, instalação rotineira de atualizações de segurança e medidas antivírus, e atividade do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="91c22-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="91c22-105">Essas práticas se beneficiam não apenas da infraestrutura do Microsoft Lync Server 2013, mas também de toda a sua rede.</span><span class="sxs-lookup"><span data-stu-id="91c22-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="91c22-106">Se você não tiver implementado essas práticas, recomendamos fazê-lo antes de implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91c22-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="91c22-107">Para ajudar a proteger os servidores em sua implantação do Lync Server 2013 de danos acidentais ou intencionais que podem resultar em tempo de inatividade, tome as seguintes precauções:</span><span class="sxs-lookup"><span data-stu-id="91c22-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="91c22-108">Mantenha em dia as atualizações de segurança nos servidores.</span><span class="sxs-lookup"><span data-stu-id="91c22-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="91c22-109">Inscreva-se no serviço Microsoft Security Notification Service para receber uma notificação imediata do lançamento de boletins de segurança referentes a qualquer produto da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91c22-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="91c22-110">Para se inscrever, acesse o site Microsoft Technical Security [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202)Notifications em.</span><span class="sxs-lookup"><span data-stu-id="91c22-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="91c22-111">Certifique-se de que os direitos de acesso estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="91c22-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="91c22-p103">Mantenha os servidores em um ambiente físico que evite o acesso não autorizado. Verifique se um software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do aplicativo antivírus para deixar essas assinaturas sempre em dia.</span><span class="sxs-lookup"><span data-stu-id="91c22-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="91c22-116">Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instala o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91c22-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="91c22-117">Criptografe os sistemas operacionais e as unidades de disco nos quais os dados são armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir um controle constante e completo dos servidores, isolamento físico total e descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.</span><span class="sxs-lookup"><span data-stu-id="91c22-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="91c22-118">Desabilite todas as portas DMA (Acesso direto à memória) externas do servidor, a menos que você possa garantir um controle muito rígido sobre o acesso físico aos servidores.</span><span class="sxs-lookup"><span data-stu-id="91c22-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="91c22-119">Os ataques baseados em DMA, que podem ser iniciados com bastante facilidade, podem expor informações muito confidenciais, como chaves de criptografia privadas.</span><span class="sxs-lookup"><span data-stu-id="91c22-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

