---
title: 'Lync Server 2013: Configurando clientes para usar com o servidor do Office Web Apps'
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
ms.openlocfilehash: fb4b9b881d0f7d469c924a0ba032071092bddbbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Configurar clientes do Lync Server 2013 para uso com o servidor do Office Web Apps

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

Se você quiser que os usuários tenham os recursos completos do Office Web App Server, atualize-os para o Microsoft Lync 2013; somente os usuários do Lync 2013 poderão fazer coisas como rolar pelos slides do PowerPoint independentemente da apresentação real do PowerPoint. (Ou seja, esses usuários podem ver qualquer slide da apresentação a qualquer momento, sem interferir em qualquer forma com a apresentação real.) Os usuários que não estiverem usando o Lync 2013 ainda poderão participar de conferências online e exibir a apresentação do PowerPoint; no entanto, eles não poderão rolar de forma independente nos slides nem poderão ver as transições de slide nem exibir vídeos inseridos.

Observe que esses recursos estarão sempre disponíveis para os usuários do Lync 2013; Isso é verdadeiro mesmo que o apresentador do PowerPoint esteja executando o Microsoft Lync 2010. Se uma apresentação do PowerPoint estiver sendo hospedada por um usuário que está executando o Lync 2010, o Lync Server 2013 irá coordenar com o servidor do Office Web Apps para garantir que os usuários do Lync 2013 exibirão a versão do servidor dos Office Web Apps dessa apresentação. O Office Web Apps Server não fornece serviços do PowerPoint para usuários que executam clientes que não sejam o Lync 2013. Em vez disso, esses usuários se conectam ao serviço do servidor de conferência e exibem apresentações do PowerPoint da mesma forma que no Microsoft Lync Server 2010. Isso também significa que esses usuários terão acesso somente aos recursos mais limitados oferecidos pelo Lync Server 2010.

Embora não seja necessária nenhuma configuração do cliente para o Office Web Apps Server (exceto para atualizar usuários para o Lync 2013), é recomendável que os participantes da conferência sejam atualizados para o Internet Explorer 9. Embora as conferências possam ser acessadas usando o Internet Explorer 8, há algumas limitações para usar o navegador da Web. Por exemplo, os usuários do Internet Explorer 8 não serão capazes de redimensionar a fase do PowerPoint para um tamanho personalizado; em vez disso, eles serão limitados a usar um dos três tamanhos de estágio predefinidos. Da mesma forma, os usuários do Internet Explorer 8 não serão capazes de reproduzir arquivos de mídia.

</div>

<span> </span>

</div>

</div>

</div>

