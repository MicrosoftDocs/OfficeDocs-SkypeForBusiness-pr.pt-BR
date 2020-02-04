---
title: Migrar servidor de mediação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3478bb3bb837e44ed33597f72738b181b4c67561
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migrar servidor de mediação

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

O servidor de mediação é mesclado à sua topologia piloto do Lync Server 2013 quando você executa o assistente de mesclagem. No entanto, você pode configurar o servidor de mediação do Lync Server 2013, quando todos os usuários forem migrados porque um pool do Office Communications Server 2007 R2 não pode se comunicar com um servidor de mediação do Lync Server 2013. Durante a migração lado a lado, o pool do Lync Server 2013 se comunica com o servidor de mediação do Office Server 2007 R2.

Ao configurar o servidor de mediação do Lync Server 2013, você também deve atualizar ou substituir seus gateways do Office Communications Server 2007 R2. Os gateways do Office Communications Server 2007 R2 não oferecem suporte ao Lync Server 2013 Media Server. Você precisa implantar gateways certificados para o Lync Server 2013 e associá-los ao servidor do Lync Server 2013 Media Server. Esta etapa é necessária para que você possa encerrar completamente a implantação do Office Communications Server 2007 R2.

Os tópicos desta seção descrevem tarefas de configuração que você precisa executar após concluir a migração do servidor de mediação do Lync Server 2013. A transição do servidor de mediação posicionado para um servidor de mediação autônomo é uma tarefa opcional.

  - [Configurar o servidor de mediação](configure-mediation-server.md)

  - [Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Fazer a transição de um servidor de mediação posicionado para um servidor autônomo de mediação (opcional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

