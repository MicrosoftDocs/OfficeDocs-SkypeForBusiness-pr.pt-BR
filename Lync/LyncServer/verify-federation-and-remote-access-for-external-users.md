---
title: Verifique o acesso remoto e de federação para usuários externos
description: Verificar a Federação e o acesso remoto para usuários externos.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555067"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verifique o acesso remoto e de federação para usuários externos

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-18_

Após a transição da rota de Federação para o servidor de borda do Lync Server 2013, você deve executar alguns testes funcionais para verificar se a Federação é realizada conforme o esperado. Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Teste a conectividade de usuários externos e do acesso externo

  - Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Lync Server 2010. Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.

  - Os usuários de cada provedor de serviços públicos de IM que sua organização suporta (e para o qual o provisionamento foi concluído) comunicando-se com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.

  - Verifique se usuários anônimos podem participar de conferências.

  - Um usuário hospedado no Lync Server 2010 usando acesso de usuário remoto (fazendo logon no Lync Server 2010 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Lync Server 2010. Testar a IM, presença, A/V e compartilhamento de área de trabalho.

  - Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Lync Server 2010. Testar a IM, presença, A/V e compartilhamento de área de trabalho.

</div>

</div>

<span> </span>

</div>

</div>

</div>

