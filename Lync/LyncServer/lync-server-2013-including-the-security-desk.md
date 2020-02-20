---
title: 'Lync Server 2013: incluindo a central de segurança'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114efc7af1b4b566aa7af6ea558961966dd0c60b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a>Incluindo a central de segurança no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Sua empresa pode exigir que a central de segurança se envolva em uma chamada de emergência. Para ajudar a decidir como integrar a Central de Segurança à sua implantação do E9-1-1, você deve responder às perguntas a seguir.

  - **Você deseja que o suporte de segurança seja notificado quando houver uma chamada de emergência?**  
    Você pode configurar a política de local para que o Lync Server envie alertas de mensagens instantâneas (IM) para os endereços SIP do Lync de um ou mais funcionários de segurança. Esses alertas contêm o nome, o número e o local da pessoa que está fazendo a chamada de emergência e facilitam a segurança na assistência com a situação de emergência.

<!-- end list -->

  - **Deseja estabelecer conferência com o suporte de segurança em cada chamada de emergência?**  
    Se tiver suporte do provedor de serviços de emergência, você poderá configurar a política de local para incluir um número de retorno de chamada com cada chamada de emergência. Esse número é usado pelo provedor para estabelecer conferência com a equipe de segurança da sua organização em chamadas de emergência. Essa conferência pode ser configurada na política de local para ser unidirecional (somente escuta) ou bidirecional.

<div>


> [!NOTE]  
> Se desejar, você pode configurar uma equipe de segurança diferente para cada política de local. Isso permite personalizar a resposta para áreas diferentes da empresa ou criar um comportamento diferente para chamadas de emergência que originam da parte interna em oposição à parte externa da rede. Você pode usar grupos de distribuição para especificar o pessoal que você deseja notificar.



</div>

</div>

<span> </span>

</div>

</div>

</div>

