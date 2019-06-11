---
title: Implantar clientes do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Implantar clientes do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Depois de migrar usuários para o Lync Server 2013, faça o seguinte:

1.  Use o filtro de versão do cliente no novo servidor do Lync Server 2013 para permitir somente aos clientes com as atualizações mais recentes instaladas para entrar.

2.  Se necessário, defina as configurações de política de grupo necessárias para a inicialização do cliente. Para obter detalhes, consulte Configurando [as políticas de inicialização do cliente no Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) na documentação de implantação. A configuração dessas configurações só será necessária se você quiser alterar as políticas de inicialização do cliente existentes ou se quiser definir as novas políticas de inicialização do cliente. Se você não planejar configurar as políticas de inicialização do cliente ou se quiser que as políticas de inicialização do cliente herdadas permaneçam efetivas, nenhuma ação será necessária.

3.  Configurar outras políticas de usuário e de cliente para usuários específicos ou grupos de usuários usando o painel de controle do Lync Server 2013, o Shell de gerenciamento do Lync Server 2013 ou ambos. Para obter detalhes, consulte [configurações novas e alteradas para o Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) na documentação de planejamento.

4.  Implante a versão mais recente dos clientes do Lync Server 2013 juntamente com as atualizações cumulativas mais recentes. Para obter detalhes, consulte Implantando [clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) na documentação de implantação.

5.  Adicionais Se sua organização requer o modo de privacidade de presença avançada do Lync Server 2013, após a conclusão da migração, defina uma regra de política de versão do cliente para impedir que as versões anteriores do cliente sejam conectadas. Em seguida, habilite o modo de privacidade de presença avançada.
    
    <div>
    

    > [!IMPORTANT]  
    > Não habilite o modo de privacidade de presença avançada do Lync 2013 até que todos os usuários em um determinado pool de servidores tenham as versões do cliente mais recentes instaladas.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

