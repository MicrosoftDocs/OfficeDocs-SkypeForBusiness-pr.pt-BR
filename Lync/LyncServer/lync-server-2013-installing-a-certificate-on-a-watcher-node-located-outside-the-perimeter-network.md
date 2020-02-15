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
ms.openlocfilehash: 74d89b14b783e2b78050b2db8e71a1009c974384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Instalar um certificado em um nó do Inspetor localizado fora da rede de perímetro do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Lync Server), fora da empresa (como um nó do Inspetor de transação sintética externa) ou em um limite de confiança dos serviços de domínio do Active Directory, pode requer a configuração de um servidor gateway do System Center Operations Manager. Essa função do servidor permite que os agentes não tenham uma relação confiável com o Servidor de Gerenciamento Raiz para gerar alertas. Para obter detalhes, consulte "Managing gateway Servers in Operations Manager 2007" na Biblioteca TechNet do System Center [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)Operations Manager em.

Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher. Para obter detalhes e baixar esses utilitários, consulte o artigo de blog "obtendo certificados para agentes que ingressaram em nenhum domínio com o assistente de geração de [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)certificados" em.

</div>

<span> </span>

</div>

</div>

</div>

