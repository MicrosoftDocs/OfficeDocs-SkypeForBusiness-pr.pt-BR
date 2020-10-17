---
title: 'Lync Server 2013: visão geral do diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb187711174785833716b2d14ffe7979cedcbc96
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520818"
---
# <a name="overview-of-the-director-in-lync-server-2013"></a>Visão geral do diretor no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Um diretor é um servidor executando o Lync Server 2013 que autentica solicitações do usuário, mas não hospeda contas de usuário. Opcionalmente, você pode implantar um diretor nos dois cenários a seguir:

  - Se você habilitar o acesso por usuários externos implantando servidores de borda, também deverá implantar um diretor. Neste cenário, o diretor autentica os usuários externos e, em seguida, passa o tráfego para servidores internos. Quando um diretor é usado para autenticar usuários externos, ele alivia os servidores do pool de front-ends da sobrecarga de execução de autenticação desses usuários. Também ajuda a isolar pools de front-ends internos de tráfego mal-intencionado, como ataques de negação de serviço. Se a rede é preenchida com tráfego externo inválido em tal ataque, este tráfego termina no Diretor.

  - Se você implantar vários pools de front-ends em um site central, adicionando um diretor a esse site, você poderá simplificar as solicitações de autenticação e melhorar o desempenho. Neste cenário, todas as solicitações vão primeiro para o diretor, que as direciona para o pool de front-ends correto.

</div>

<span> </span>

</div>

</div>

</div>

