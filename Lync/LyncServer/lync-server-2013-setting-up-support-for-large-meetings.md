---
title: 'Lync Server 2013: Configurando o suporte para grandes reuniões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8970d616d78cbfdafa591b58f123918cd20e0040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configurando o suporte para grandes reuniões no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-12_

O suporte a grandes reuniões de até 1000 usuários exige a criação de uma topologia apropriada, os pré-requisitos de software e hardware de reunião e a configuração adequada do ambiente.

<div>

## <a name="topology-requirements"></a>Requisitos de topologia

Uma única reunião grande requer pelo menos um servidor front-end e um servidor back-end. No entanto, para fornecer alta disponibilidade, recomendamos um pool de servidores front-end com servidores back-end espelhados.

O usuário que hospeda as grandes reuniões deve ter sua conta de usuário hospedada neste pool. No entanto, não recomendamos que você hospede outras contas de usuário nesse pool. Em vez disso, use-o apenas para grandes reuniões. A prática recomendada é criar uma conta de usuário especial nesse pool para ser usada apenas para hospedar grandes reuniões. Como a grande configuração de reunião é otimizada para desempenho, usá-la como um usuário normal pode ter problemas como a incapacidade de promover uma sessão P2P para uma reunião quando um ponto de extremidade PSTN está envolvido.

O gerenciamento de um pool com exatamente dois servidores front-end requer algumas considerações especiais. Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Além disso, se você quiser fornecer opcionalmente o backup de recuperação de desastres e o failover do pool usado para grandes reuniões, é possível emparelhar com uma configuração de pool dedicado de forma semelhante em um Data Center diferente. Para obter detalhes, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuração do pool de reuniões grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuração do pool de reuniões grandes")

As observações adicionais sobre a topologia incluem:

  - Um compartilhamento de arquivos é necessário para armazenar o conteúdo da reunião e, se o servidor de arquivamento estiver implantado e habilitado, para armazenar os arquivos de arquivamento. O compartilhamento de arquivos pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivo usado por outro pool no site no qual o pool é implantado. Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [Configure File Storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Um servidor do Office Web Apps é necessário para habilitar a funcionalidade de apresentação do PowerPoint em grandes reuniões. O servidor do Office Web Apps pode ser dedicado ao grande pool de reuniões ou pode ser o mesmo servidor do Office Web Apps usado por outros pools no site no qual o pool dedicado é implantado.

  - O balanceamento de carga dos servidores front-end requer o balanceamento de carga de hardware para o tráfego HTTP (como download de conteúdo de reunião). O balanceamento de carga de DNS é recomendado para tráfego SIP. Para obter detalhes, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Se você quiser usar o Monitoring Server para o pool dedicado de grandes reuniões, recomendamos o uso do Monitoring Server e do banco de dados compartilhado em todos os pools de servidores front-end na sua implantação do Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e de software

Os requisitos de hardware para servidores em um pool de grande reunião dedicado são os mesmos que para seus outros servidores do Lync Server 2013. Para obter detalhes sobre os requisitos de hardware, consulte "[plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Os servidores em um pool de reunião grande dedicado devem atender a todos os requisitos de software do Lync Server 2013. Para obter detalhes sobre os requisitos de software, confira a seguinte documentação:

  - [Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Além disso, o Lync Server 2013 e todos os clientes do Lync Server 2013 devem ter as atualizações mais recentes.

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuração

Recomendamos a criação de uma nova política de conferência especificamente para grandes reuniões e, em seguida, a atribuição da política de conferência aos usuários hospedados no pool dedicado de grandes reuniões. Configure a política de conferência usando as seguintes configurações:

  - Defina a opção **MaxMeetingSize** para **1000**. (O padrão é **250**).

  - Defina a opção **AllowLargeMeetings** como **true**.

  - Defina a opção **EnableAppDesktopSharing** para **nenhum**.

  - Defina a opção **AllowUserToScheduleMeetingsWithAppSharing** para **falso**.

  - Defina a opção **AllowSharedNotes** para **falso**.

  - Defina a opção **AllowAnnotations** para **falso**.

  - Defina a opção **DisablePowerPointAnnotations** como **true**.

  - Defina a opção **AllowMultiview** para **falso**.

  - Defina a opção **EnableMultiviewJoin** para **falso**.

<div>


> [!NOTE]  
> O suporte para o usuário 1000 grandes reuniões no Lync Server 2013 requer que a configuração <STRONG>AllowLargeMeetings</STRONG> na política de conferência do Agendador de reunião seja definida como true. Quando essa configuração for definida como true, a experiência do Lync será otimizada para reuniões extras grandes quando os usuários ingressarem em reunião. Especificamente, em uma grande reunião, o Lync não mostrará a inicial ou a atualização da lista de participantes da reunião completa, que é um afunilamento de desempenho para o cliente e o Lync Server 2013. Em vez disso, o Lync mostrará apenas informações sobre o usuário e a lista de apresentadores da reunião. O Lync ainda exibirá corretamente o número total de participantes disponíveis nas grandes reuniões.



</div>

Com exceção da configuração do **tamanho máximo da reunião** , todas as outras configurações de política de conferência especificadas aqui são necessárias para desabilitar os recursos de conferência que não são necessários em grandes reuniões.

Além disso, você precisa configurar o pool de reunião grande dedicado para que cada usuário do Lync Server 2013 hospedado no pool e responsável pelo gerenciamento da agenda da reunião tenha as permissões apropriadas. Para tanto, siga estes passos:

  - Defina a opção **designar como apresentador** como **nenhum**. Normalmente, um ou apenas alguns usuários de todos os participantes de uma grande reunião são os apresentadores, portanto, os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores. Em vez disso, os apresentadores devem ser explicitamente designados no horário do plano de reunião ou ser promovidos explicitamente durante a grande reunião.

  - Certifique-se de que a caixa de seleção **tipo de conferência atribuído por padrão** não esteja selecionada. Esta configuração controla se o suplemento de reunião online para o Lync 2013 sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as reuniões agendadas têm a mesma URL de ingresso e informações de áudio. Em pequenos cenários de colaboração de grupo, ter esse tipo de conferência atribuído funciona bem porque todos têm sua própria conferência atribuída individualmente e a URL de ingresso e as informações de áudio constantes ajudam a facilitar a reunião mais rápida. No entanto, no cenário de reunião grande, a equipe de suporte de grande reunião agenda as grandes reuniões usando um único conjunto de credenciais de usuário e, em seguida, fornece URLs de ingresso e informações de áudio aos solicitantes da reunião. Nesse caso, o uso de uma URL diferente para ingressar em cada reunião funciona melhor.

  - Certifique-se de que a caixa de seleção **admitir usuários anônimos por padrão** não esteja selecionada, a menos que seja necessária. Essa configuração afeta o tipo de acesso de reunião padrão agendado pelo suplemento reunião online para Lync 2013 quando não estiver usando uma conferência atribuída. A opção apropriada para essa configuração depende das necessidades da sua organização. Se a maioria das grandes reuniões da sua organização forem reuniões internas, não selecione essa opção. Se a maioria das reuniões grandes exigir que usuários externos possam participar, selecione essa opção.

</div>

</div>

<span> </span>

</div>

</div>

</div>

