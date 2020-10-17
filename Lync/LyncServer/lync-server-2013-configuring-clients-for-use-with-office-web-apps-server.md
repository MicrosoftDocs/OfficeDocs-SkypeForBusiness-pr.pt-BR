---
title: 'Lync Server 2013: Configurando clientes para uso com o servidor do Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf46a16d38e37dd8faac39a438053dcc7b8c103
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537058"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Configurando clientes do Lync Server 2013 para uso com o servidor do Office Web Apps

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

Se você quiser que os usuários experimentem todos os recursos do servidor do Office Web App, atualize-os para o Microsoft Lync 2013; somente os usuários do Lync 2013 poderão fazer coisas como rolar por slides do PowerPoint independentemente da apresentação real do PowerPoint. (Ou seja, esses usuários podem ver qualquer slide na apresentação a qualquer momento, sem interferir de qualquer forma com a apresentação real.) Os usuários que não estiverem usando o Lync 2013 ainda poderão participar de conferências online e exibir a apresentação do PowerPoint; no entanto, eles não poderão rolar de forma independente nos slides, nem poderão ver as transições de slide ou exibir vídeos incorporados.

Observe que esses recursos sempre estarão disponíveis para usuários do Lync 2013; Isso é verdadeiro mesmo se o apresentador do PowerPoint estiver executando o Microsoft Lync 2010. Se uma apresentação do PowerPoint estiver sendo hospedada por um usuário que executa o Lync 2010, o Lync Server 2013 coordenará com o servidor do Office Web Apps para garantir que os usuários do Lync 2013 exibirão a versão do servidor do Office Web Apps dessa apresentação. O servidor do Office Web Apps não fornece serviços do PowerPoint para usuários que executam clientes diferentes do Lync 2013. Em vez disso, os usuários se conectam ao serviço do servidor de conferência e exibem apresentações do PowerPoint da mesma forma que faziam no Microsoft Lync Server 2010. Isso também significa que esses usuários terão acesso apenas aos recursos mais limitados oferecidos pelo Lync Server 2010.

Embora nenhuma configuração de cliente seja necessária para o servidor do Office Web Apps (diferente de atualizar usuários para o Lync 2013), é recomendável que os participantes da conferência sejam atualizados para o Internet Explorer 9. Embora as conferências possam ser acessadas usando o Internet Explorer 8, existem algumas limitações ao usar esse navegador. Por exemplo, usuários do Internet Explorer 8 não serão capazes de redimensionar a tela do PowerPoint a um tamanho personalizado; ao invés disso, eles estarão limitados a usar um dos três tamanhos de tela predefinidos. Do mesmo modo, usuários do Internet Explorer 8 não serão capazes de reproduzir arquivos de mídia.

</div>

<span> </span>

</div>

</div>

</div>

