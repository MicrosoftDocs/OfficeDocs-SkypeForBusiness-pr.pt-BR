---
title: 'Lync Server 2013: Implantando um servidor ou aparelho de filial persistente'
description: 'Lync Server 2013: Implantando um servidor ou aparelho de filial persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558587"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-10_

O Enterprise Voice resistente refere-se à resiliência de site de filial, ou seja, a capacidade de fornecer serviço de Enterprise Voice contínuo para usuários de filiais no caso de o link para o site central se tornar indisponível.

Para sites de filiais de pequeno e médio porte (sites de filiais com 25 a 1.000 usuários), recomendamos a implantação de um aparelho de filial persistente, que encerrará chamadas PSTN (rede telefônica pública comutada) usando seu gateway PSTN interno ou um tronco SIP para um provedor de serviços de telefonia. Um aparelho de filial persistente é um dispositivo de terceiros que inclui um servidor de lâmina executando o sistema operacional Windows Server 2008 R2, o servidor do Lync Server 2013, o software do servidor de mediação e um gateway PSTN, tudo em um chassi único de dispositivo.

Para sites de filiais com 1.000 a 5.000 usuários e nenhuma WAN resistente, recomendamos um servidor de filial persistente conectado a um gateway PSTN ou um tronco SIP para um provedor de serviços de telefonia. Um servidor de filial persistente é um computador baseado no Windows Server que tem o software servidor de registrador e mediação instalado nele.

<div>


> [!NOTE]  
> Para sites de filiais com mais de 5.000 usuários e administradores dedicados do Lync Server, recomendamos uma implantação completa do Lync Server 2013, separada do site central.<BR>Para obter detalhes sobre como escolher a melhor solução de resiliência para os sites de filial em sua organização, incluindo pré-requisitos e considerações de planejamento, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliência Requirements for Lync Server 2013</A> na documentação de planejamento.



</div>

<div>


> [!NOTE]  
> Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefas do site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configurando usuários para resiliência de site de filial no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Apêndices: servidores e aparelhos de filial persistente no Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

