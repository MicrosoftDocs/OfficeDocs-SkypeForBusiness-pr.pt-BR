---
title: 'Lync Server 2013: Implantando Aplicativo ou Servidor de Filial Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7cf894fe6650ff3c06eaaa37f6ba05d70f50eeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Implantando Aplicativo ou Servidor de Filial Persistente com Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-10_

O recurso de voz corporativo resistente refere-se à resiliência de filiais, ou seja, a capacidade de fornecer serviço contínuo de voz empresarial a usuários de sites de filiais em caso de o link para o site central ficar indisponível.

Para sites de filiais de pequeno e médio porte (sites de filiais com 25 a 1.000 usuários), recomendamos implantar um aparelho de ramificação sobreviventes, que encerrará chamadas PSTN (rede telefônica pública comutada) usando seu gateway PSTN embutido ou um tronco SIP para um telefone provedor de serviços. Um aparelho de ramificação sobreviventes é um dispositivo de terceiros que inclui um servidor blade executando o sistema operacional Windows Server 2008 R2, o Lync Server 2013 registrador, o software do servidor de mediação e um gateway PSTN, tudo em um chassi único de dispositivo.

Para sites de filiais com 1.000 a 5.000 usuários e sem conexão de longa distância, recomendamos um servidor de ramificação sobreviventes conectado a um gateway PSTN ou um tronco SIP para um provedor de serviços de telefonia. Um servidor de ramificação sobreviventes é um computador baseado no Windows Server que tem o software servidor de registrador e mediação instalado.

<div>


> [!NOTE]  
> Para sites de filiais com mais de 5.000 usuários e administradores dedicados do Lync Server, recomendamos uma implantação completa do Lync Server 2013, separada do site central.<BR>Para obter detalhes sobre como escolher a melhor solução de resiliência para os sites de filiais em sua organização, incluindo pré-requisitos e considerações de planejamento, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site para o Lync Server 2013</A> na documentação de planejamento.



</div>

<div>


> [!NOTE]  
> Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013 - Tarefas do site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Implantar Servidor ou Aparelho de Filial Persistente com Lync Server 2013 - tarefa de site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configurando usuários para resiliência de site da filial no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Usuários domésticos em um Home users on a Aparelho de Filial Persistente ou Servidor no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Anexos: Servidores e Aplicativos de Filial Persistente no Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

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

