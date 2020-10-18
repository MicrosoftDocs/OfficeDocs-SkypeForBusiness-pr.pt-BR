---
title: 'Lync Server 2013: instalando um certificado em um nó do Inspetor localizado fora da rede de perímetro'
description: 'Lync Server 2013: instalando um certificado em um nó do Inspetor localizado fora da rede de perímetro.'
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
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574027"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="b4a96-103">Instalar um certificado em um nó do Inspetor localizado fora da rede de perímetro do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a96-103">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a96-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b4a96-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b4a96-105">Os agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Lync Server), fora da empresa (como um nó do Inspetor de transação sintético externo) ou em um limite de confiança dos serviços de domínio do Active Directory, podem exigir a configuração de um servidor de gateway do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b4a96-105">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="b4a96-106">Essa função do servidor permite que os agentes não tenham uma relação confiável com o Servidor de Gerenciamento Raiz para gerar alertas.</span><span class="sxs-lookup"><span data-stu-id="b4a96-106">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="b4a96-107">Para obter detalhes, consulte "Managing gateway Servers in Operations Manager 2007" na Biblioteca TechNet do System Center Operations Manager em [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .</span><span class="sxs-lookup"><span data-stu-id="b4a96-107">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="b4a96-108">Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b4a96-108">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="b4a96-109">Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher.</span><span class="sxs-lookup"><span data-stu-id="b4a96-109">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="b4a96-110">Para obter detalhes e baixar esses utilitários, consulte o artigo de blog "obtendo certificados para agentes que ingressaram em nenhum domínio com o assistente de geração de certificados" em [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .</span><span class="sxs-lookup"><span data-stu-id="b4a96-110">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

