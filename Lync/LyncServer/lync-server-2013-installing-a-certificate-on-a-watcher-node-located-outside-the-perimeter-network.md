---
title: 'Lync Server 2013: instalando um certificado em um nó de Inspetor localizado fora da rede de perímetro'
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
ms.openlocfilehash: 10cd31639445fab6138ea77cb40a03d727ecce12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Instalar um certificado em um nó de Inspetor localizado fora da rede de perímetro do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Lync Server), fora da empresa (como um nó de Inspetor de transação sintético externo) ou em um limite de confiança dos serviços de domínio Active Directory, podem exija a configuração de um servidor de gateway do System Center Operations Manager. Esta função de servidor permite que agentes que não têm uma relação de confiança com o servidor de gerenciamento raiz gerem alertas. Para obter detalhes, consulte "Gerenciando servidores de gateway no Operations Manager 2007", na biblioteca do TechNet [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)do System Center Operations Manager em.

Se você implantar um agente em um desses locais, também será necessário solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo correto de certificado no computador do nó do Inspetor. Para obter detalhes e baixar esses utilitários, consulte o artigo "obtendo certificados para agentes associados a um domínio fácil com o assistente de geração de certificados" em [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421).

</div>

<span> </span>

</div>

</div>

</div>

