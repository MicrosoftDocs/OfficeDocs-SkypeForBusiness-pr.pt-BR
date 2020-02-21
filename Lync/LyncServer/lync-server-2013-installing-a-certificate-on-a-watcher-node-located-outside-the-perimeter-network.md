---
title: 'Lync Server 2013: instalando um certificado em um nó do Inspetor localizado fora da rede de perímetro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b82dcdfd5cc5f7ec00b92c333acbe107a8ec519
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="10fe4-102">Instalar um certificado em um nó do Inspetor localizado fora da rede de perímetro do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10fe4-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10fe4-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="10fe4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="10fe4-104">Agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Lync Server), fora da empresa (como um nó do Inspetor de transação sintética externa) ou em um limite de confiança dos serviços de domínio do Active Directory, pode requer a configuração de um servidor gateway do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="10fe4-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="10fe4-105">Essa função do servidor permite que os agentes não tenham uma relação confiável com o Servidor de Gerenciamento Raiz para gerar alertas.</span><span class="sxs-lookup"><span data-stu-id="10fe4-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="10fe4-106">Para obter detalhes, consulte "Managing gateway Servers in Operations Manager 2007" na Biblioteca TechNet do System Center [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703)Operations Manager em.</span><span class="sxs-lookup"><span data-stu-id="10fe4-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="10fe4-107">Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="10fe4-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="10fe4-108">Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher.</span><span class="sxs-lookup"><span data-stu-id="10fe4-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="10fe4-109">Para obter detalhes e baixar esses utilitários, consulte o artigo de blog "obtendo certificados para agentes que ingressaram em nenhum domínio com o assistente de geração de [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421)certificados" em.</span><span class="sxs-lookup"><span data-stu-id="10fe4-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

