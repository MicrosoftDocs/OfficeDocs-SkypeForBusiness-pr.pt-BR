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
ms.openlocfilehash: 2bf4519995abf75db7807f8cd80f07ea477c8d4b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498548"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Instalar um certificado em um nó do Inspetor localizado fora da rede de perímetro do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Os agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Lync Server), fora da empresa (como um nó do Inspetor de transação sintético externo) ou em um limite de confiança dos serviços de domínio do Active Directory, podem exigir a configuração de um servidor de gateway do System Center Operations Manager. Essa função do servidor permite que os agentes não tenham uma relação confiável com o Servidor de Gerenciamento Raiz para gerar alertas. Para obter detalhes, consulte "Managing gateway Servers in Operations Manager 2007" na Biblioteca TechNet do System Center Operations Manager em [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .

Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher. Para obter detalhes e baixar esses utilitários, consulte o artigo de blog "obtendo certificados para agentes que ingressaram em nenhum domínio com o assistente de geração de certificados" em [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .

</div>

<span> </span>

</div>

</div>

</div>

