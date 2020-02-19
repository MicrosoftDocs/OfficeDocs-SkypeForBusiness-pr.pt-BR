---
title: Implantar clientes do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331241dea4f047928913550764c995a7c6f05260
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Implantar clientes do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Após migrar usuários para o Lync Server 2013, faça o seguinte:

1.  Use o filtro de versão do cliente no novo servidor do Lync Server 2013 para permitir que apenas clientes com as atualizações mais recentes instaladas entrem.

2.  Caso seja necessário, defina as configurações da Política de Grupo necessárias para a inicialização do cliente. Para obter detalhes, consulte [Configuring Client Bootstrap Policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) na documentação de implantação. A definição destas configurações é necessária apenas se você deseja alterar as políticas de inicialização do cliente existentes ou se deseja definir as novas políticas de inicialização do cliente. Caso não planeje configurar as políticas de inicialização do cliente ou se deseja que as políticas de inicialização do cliente herdadas permaneçam em vigor, nenhuma ação é necessária.

3.  Configure outras políticas de usuário e de cliente para usuários ou grupos de usuários específicos usando o painel de controle do Lync Server 2013, o Shell de gerenciamento do Lync Server 2013 ou ambos. Para obter detalhes, consulte [configurações novas e alteradas para o Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) na documentação de planejamento.

4.  Implante a versão mais recente dos clientes do Lync Server 2013 junto com as atualizações cumulativas mais recentes. Para obter detalhes, consulte [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) na documentação de implantação.

5.  Opcion Se sua organização requer o modo de privacidade de presença avançada do Lync Server 2013, após a conclusão da migração, defina uma regra de política de versão do cliente para impedir que as versões anteriores do cliente entrem em entrar. Habilite, então, o modo de privacidade de presença avançada.
    
    <div>
    

    > [!IMPORTANT]  
    > Não habilite o modo de privacidade de presença avançada do Lync 2013 até que cada usuário em um determinado pool de servidores tenha as versões mais recentes do cliente instaladas.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

