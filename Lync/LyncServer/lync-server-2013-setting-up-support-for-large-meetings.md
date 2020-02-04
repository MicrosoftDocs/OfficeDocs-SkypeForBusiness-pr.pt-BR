---
title: 'Lync Server 2013: Configurando o suporte para reuniões grandes'
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
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configurando o suporte para reuniões grandes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-12_

Dar suporte a reuniões grandes de até 1000 os usuários exigem a criação de uma topologia apropriada, os pré-requisitos de hardware e software de reunião e a configuração apropriada do ambiente.

<div>

## <a name="topology-requirements"></a>Requisitos de topologia

Uma grande reunião exige pelo menos um Servidor Front-End e um Servidor Back-End. No entanto, para fornecer alta disponibilidade, recomendamos um pool de servidores front-end com servidores back-end espelhados.

O usuário que hospeda as reuniões grandes deve ter sua conta de usuário hospedada neste pool. No entanto, não recomendamos que você hospede outras contas de usuário nesse pool. Em vez disso, use-o apenas para reuniões grandes. A prática recomendada é criar uma conta de usuário especial nesse pool para ser usada apenas para hospedar reuniões grandes. Já que a definição de grandes reuniões é otimizada para um melhor desempenho, usá-la como usuário normal poderia gerar problemas como incapacidade de promover uma sessão de P2P em uma reunião quando um ponto de extremidade de PSTN estiver envolvido.

Gerenciar um pool com exatamente dois Servidores Front-End exige algumas considerações especiais. Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Além disso, se você quiser oferecer failover e backup de recuperação de desastres para o pool usado em grandes reuniões, poderá emparelhar com um pool dedicado de configuração semelhante em outro datacenter. Para obter detalhes, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configuração de pool de reuniões grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuração de pool de reuniões grandes")

As notas adicionais sobre a topologia incluem:

  - Um compartilhamento de arquivo é necessário para armazenar conteúdo da reunião e, se o Servidor de Arquivamento estiver implantado e habilitado, armazenar os arquivos de arquivo. O compartilhamento de arquivo pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivo usado por outro pool no site em que o pool é implantado. Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [Configurar o armazenamento de arquivos para o Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - Um servidor do Office Web Apps é necessário para habilitar a funcionalidade de apresentação do PowerPoint em reuniões grandes. O servidor do Office Web Apps pode ser dedicado ao grande pool de reuniões ou pode ser o mesmo servidor dos Office Web Apps usado por outros pools no site em que o pool dedicado é implantado.

  - Os Servidores Front-End exige balanceamento de carga para tráfego HTTP (como download de conteúdo de reunião). O balanceamento de carga DNS é recomendado para tráfego SIP. Para obter detalhes, consulte [requisitos de balanceamento de carga para o Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Se você quiser usar o Monitoring Server para o pool de reunião dedicado a grandes dimensões, recomendamos usar o Monitoring Server e seu banco de dados que são compartilhados entre todos os pools de servidores front-end na implantação do Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

Os requisitos de hardware para servidores em um pool de reunião grande dedicado são iguais aos dos outros servidores do Lync Server 2013. Para obter detalhes sobre os requisitos de hardware, consulte "[plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Os servidores em um pool de reunião dedicado a grandes devem atender a todos os requisitos de software do Lync Server 2013. Para saber mais sobre os requisitos de software, consulte a seguinte documentação:

  - [Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisitos adicionais de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Além disso, o Lync Server 2013 e todos os clientes do Lync Server 2013 devem ter as atualizações mais recentes.

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuração

Recomendamos a criação de uma nova política de conferência especificamente para reuniões grandes e, em seguida, a atribuição da política de conferência aos usuários que estão hospedados no pool de reunião grande dedicada. Configure a política de conferência usando os seguintes ajustes:

  - Defina a opção **MaxMeetingSize** para **1000**. (O padrão é **250**).

  - Defina a opção **AllowLargeMeetings** para **Verdadeiro**.

  - Defina a opção **EnableAppDesktopSharing** para **Nenhum**.

  - Defina a opção **AllowUserToScheduleMeetingsWithAppSharing** para **Falso**.

  - Defina a opção **AllowSharedNotes** para **Falso**.

  - Defina a opção **AllowAnnotations** para **Falso**.

  - Defina a opção **DisablePowerPointAnnotations** para **Verdadeiro**.

  - Defina a opção **AllowMultiview** para **Falso**.

  - Defina a opção **EnableMultiviewJoin** para **Falso**.

<div>


> [!NOTE]  
> O suporte para o usuário do 1000 reuniões grandes no Lync Server 2013 requer a configuração <STRONG>AllowLargeMeetings</STRONG> na política de conferência para que o Agendador de reunião seja definido como true. Quando essa configuração é definida como true, a experiência do Lync será otimizada para reuniões extras grandes quando os usuários ingressarem em tal reunião. Especificamente, em uma reunião grande, o Lync não mostrará a inicial ou a atualização da lista de participantes da reunião completa, que é um afunilamento de desempenho do cliente e do Lync Server 2013. Em vez disso, o Lync mostrará apenas as informações sobre o usuário e a lista de apresentadores da reunião. O Lync ainda exibirá corretamente o número total de participantes disponíveis nas reuniões grandes.



</div>

Exceto pela configuração **Tamanho máximo das reuniões**, todas as outras configurações de política de conferência especificadas aqui são obrigatórias para desativar as funcionalidades de conferência que não são necessárias em grandes reuniões.

Além disso, você precisa configurar o pool de reunião longa dedicada para que cada usuário do Lync Server 2013 hospedado no pool e responsável por gerenciar o cronograma da reunião tenha as permissões apropriadas. Para tanto, siga estes passos:

  - Defina a opção **Designar como apresentador** para **Nenhum**. Normalmente, um ou apenas alguns usuários de todos os participantes em uma grande reunião são apresentadores, então os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores. Em vez disso, os apresentadores devem ser designados explicitamente na hora da programação da reunião, ou serem promovidos explicitamente durante uma grande reunião.

  - Certifique-se de que a caixa de seleção **Tipo de conferência atribuído por padrão** não está selecionada. Esta configuração controla se o suplemento de reunião online para o Lync 2013 sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as reuniões agendadas têm a mesma URL de junção e informações de áudio. Em cenários de colaboração de pequenos grupos, ter tal tipo de conferência atribuído funciona bem, pois todos têm sua própria conferência atribuída individualmente e a URL de ingresso e informações de áudio constantes ajudam a facilitar um ingresso mais rápido à reunião. No entanto, no caso de grandes reuniões, a equipe as agenda usando um conjunto simples de credenciais de usuário e, depois, fornece URLs de ingresso de informações de áudio para os solicitantes. Neste caso, usar uma URL diferente para ingressar em cada reunião funciona melhor.

  - Certifique-se de que a caixa de seleção **Admitir usuários anônimos por padrão** não esteja selecionada, a menos que seja obrigatória. Essa configuração afeta o tipo padrão de acesso à reunião agendado pelo suplemento de reunião online do Lync 2013 quando não estiver usando uma conferência atribuída. A opção apropriada para essa configuração depende das necessidades da sua organização. Se a maioria das grandes reuniões da sua organização for interna, não selecione essa opção. Se a maioria das grandes reuniões exigir que usuários externos possam participar, selecione essa opção.

</div>

</div>

<span> </span>

</div>

</div>

</div>

