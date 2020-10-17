---
title: Migrar o Servidor de Mediação
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d1e9eaee83f4db6c1ca30cd143d62d45852988
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527518"
---
# <a name="migrate-mediation-server"></a>Migrar o Servidor de Mediação

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Seu servidor de mediação é mesclado na topologia piloto do Lync Server 2013 quando você executa o assistente de mesclagem. No entanto, você configura o servidor de mediação do Lync Server 2013, depois que todos os usuários são migrados porque um pool do Office Communications Server 2007 R2 não pode se comunicar com um servidor de mediação 2013 do Lync Server. Durante a migração lado a lado, o pool do Lync Server 2013 se comunica com o servidor de mediação do Office Communications Server 2007 R2.

Ao configurar seu servidor de mediação do Lync Server 2013, você também deve atualizar ou substituir seus gateways do Office Communications Server 2007 R2. Os gateways do Office Communications Server 2007 R2 não oferecem suporte ao Lync Server 2013 Mediation Server. Você precisa implantar gateways certificados para o Lync Server 2013 e associá-los ao servidor de mediação do Lync Server 2013. Esta etapa é necessária para que você possa encerrar completamente sua implantação do Office Communications Server 2007 R2.

Os tópicos desta seção descrevem tarefas de configuração que você precisa realizar depois de concluir a migração do servidor de mediação do Lync Server 2013. A transição do Servidor de mediação colocado para um Servidor de mediação independente é uma tarefa opcional.

  - [Configurar o servidor de mediação](configure-mediation-server.md)

  - [Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo (opcional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

