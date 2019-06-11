---
title: 'Lync Server 2013: Topologias suportadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologias suportadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-14_

O Lync Server 2013 dá suporte à implantação de sites locais em uma organização e à integração de implantações locais com implantações do Lync Online, que é conhecida como uma implantação híbrida. Em uma implantação híbrida, alguns usuários são hospedados localmente e alguns usuários são hospedados online.

Para implantações locais, o Lync Server 2013 é compatível com a implantação de um ou mais sites que podem ser dimensionados para atender aos requisitos de alta disponibilidade e local. Você pode estruturar esses sites e seus componentes para atender aos requisitos de acesso e adaptabilidade da sua organização.

Uma implantação local do Lync Server 2013 consiste no seguinte:

  - Sua implantação deve incluir pelo menos um site central (também conhecido como um Data Center). Cada site central deve conter pelo menos um pool de front-end do Enterprise Edition ou um servidor Standard Edition. Eles consistem nos seguintes:
    
      - Pool de front-end do Enterprise Edition, que consiste em um ou mais servidores front-end (geralmente, pelo menos dois servidores front-end para escalabilidade) e um servidor back-end separado. Um pool de front-ends pode conter no máximo doze servidores front end. O balanceamento de carga é necessário para vários servidores front-end. Para o tráfego SIP, recomendamos o balanceamento de carga de DNS, mas também há suporte para o balanceamento de carga de hardware. Se você usar o balanceamento de carga de DNS para o tráfego SIP, ainda precisará de um balanceador de carga de hardware para tráfego HTTP. Recomendamos o espelhamento do SQL Server para alta disponibilidade de bancos de dados. O banco de dados back-end requer uma instância separada, mas você pode posicionar o banco de dados de arquivamento, o banco de dados de monitoramento, o banco de dados de chat persistente e o banco de dados de conformidade de chat persistente O Lync Server 2013 oferece suporte ao uso de um cluster compartilhado para os compartilhamentos de arquivos na sua implantação. Para obter detalhes sobre requisitos de armazenamento de banco de dados, consulte [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md). Para obter detalhes sobre requisitos de armazenamento de arquivos, consulte [suporte ao armazenamento de arquivos no Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Se você posicionar bancos de dados do Lync Server, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho. Para verificar as capacidades de failover, recomendamos o teste de todos os cenários de failover.

        
        </div>
    
      - Standard Edition Server, que inclui um banco de dados do SQL Server Express posicionado.

  - Sua implantação também pode ter um ou mais sites de filiais associados a um site central.

Esta seção descreve os sites e os componentes de uma implantação do Lync Server 2013. Para obter detalhes sobre o site, a topologia e o planejamento de componentes do Lync Server 2013, consulte [noções básicas de topologia que você precisa saber antes de planejar o Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e as [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento. Para obter detalhes sobre a integração de componentes de versões anteriores, consulte [caminhos de migração e cenários de coexistência suportados no Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Pools ampliados não são compatíveis com as funções de servidor front-end, Edge, Mediation e director.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologias e componentes de sites centrais (local)

Embora uma topologia de site central deva incluir um pool de front-end ou um servidor Standard Edition, cada site central também pode conter o seguinte:

  - Vários pools de front-end, que podem estar no mesmo domínio ou domínios diferentes. No entanto, todos os servidores de front-end em um pool de front-end e o servidor back-end desse pool devem estar no mesmo domínio.

  - Vários servidores Standard Edition.

  - Office Web Apps Server, que é usado com os aplicativos Web do Office no Lync Server 2013 para manipular o compartilhamento e a renderização de apresentações do Microsoft PowerPoint.

  - Servidor de borda ou o pool de bordas na sua rede de perímetro, se você quiser que a implantação seja compatível com parceiros federados, conectividade de mensagem de chat pública, um gateway de protocolo de presença e mensagens extensível (XMPP), acesso de usuário remoto, participação de usuários anônimos em reuniões, ou UM (a) Unificação de mensagens do Exchange. Você não pode colocar nenhuma outra função de servidor com um servidor de borda. Recomendamos o balanceamento de carga de DNS, quando apropriado, mas também há suporte para o balanceamento de carga de hardware. As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda. Para obter detalhes sobre requisitos e suporte de balanceamento de carga, consulte [planejando o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.

  - Servidor de mediação ou pool, se você quiser dar suporte à conferência de voz ou discada em um pool de front-ends no site central. Dependendo de como você implantou o suporte do Enterprise Voice, pode colocar o servidor de mediação em um pool de front-end (o padrão) ou implantar um servidor ou pool autônomo de mediação. Você pode usar o DNS, o hardware ou o balanceamento de carga do aplicativo (quando adequado) para distribuir o tráfego de um peer de gateway do pool do servidor de mediação, incluindo um gateway PSTN, IP-PBX ou controle de borda de sessão de tronco SIP (SBC). Para obter detalhes sobre como planejar a topologia do servidor de mediação apropriada, consulte [diretrizes de implantação do servidor de mediação no Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) na documentação de planejamento.

  - Servidor de chat persistente, se você quiser que os usuários possam participar em conversas com vários participantes, com base em tópicos que persistem ao longo do tempo. Para fornecer mais capacidade e maior confiabilidade, a topologia pode incluir vários computadores que executam o servidor de chat persistente. Você não pode colocar o servidor de chat persistente com outras funções de servidor em um pool de empresas. No entanto, você pode colocar o servidor de chat persistente em um servidor Standard Edition. O chat persistente exige um banco de dados e, se você implementar a conformidade persistente de chat, um banco de dados de conformidade de chat persistente, mas os bancos de dados puderem ficar posicionados com o banco de dados de arquivamento, monitorando o banco de dados ou no servidor back-end de uma edição Enterprise Pool de front-ends. Para obter detalhes sobre como planejar a topologia do servidor de chat persistente apropriada, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

  - Monitoramento, se você quiser dar suporte a coleta de dados para a qualidade de qualidade de áudio/vídeo (QoE) e registro de detalhes de chamadas (CDR) para conferências do Enterprise Voice e de A/V na sua implantação. Opcionalmente, você pode instalar o Microsoft System Center Operations Manager (antigo Microsoft Operations Manager), que usa monitoramento de dados CDR e QoE para gerar alertas de tempo real, que mostram a integridade da confiabilidade das chamadas e a qualidade das mídias. O monitoramento, quando implantado, é posicionado em servidores front-end ou em um servidor Standard Edition. O monitoramento exige um banco de dados, mas o banco de dados pode ficar posicionado com o banco de dados de arquivamento, banco de dados de chat persistente, banco de dados de conformidade de chat persistente ou no servidor back-end de um pool Front-end da Enterprise Edition.

  - Arquivamento, se você quiser arquivar comunicações de mensagem instantânea e conteúdo da reunião (por motivos de conformidade) em sua implantação. O arquivamento, quando implantado, é posicionado em servidores front-end ou em um servidor Standard Edition. O armazenamento de arquivamento requer a implantação de um banco de dados de arquivamento ou integração com o armazenamento do Exchange 2013. Se você usar ambos, que é conhecido como *modo misto*, o armazenamento do Exchange 2013 é usado para armazenar dados de arquivo morto para os usuários que são hospedados no Exchange 2013, e o banco de dados de arquivamento é usado para arquivar dados para todos os outros usuários na sua implantação. Se você precisar de um banco de dados de arquivamento, o banco de dados poderá ser posicionado no banco de dados de monitoramento, banco de dados persistente de chat, banco de dados de conformidade de chat persistente ou no servidor back-end de um pool de front-ends. Para obter detalhes sobre como planejar a topologia de arquivamento apropriada, consulte [planejando o arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.

  - O director ou o pool do director, se você quiser facilitar a resiliência e o redirecionamento de solicitações de usuário do Lync Server 2013 para o pool primário do usuário, que pode ser um pool Front-end Enterprise Edition ou um servidor Standard Edition. Recomendamos que você implante um diretor ou um pool de diretor em cada site central compatível com acesso externo a usuários e em cada site central no qual você implanta um ou mais pools front-ends. Cada pool de directors pode conter no máximo dez directors. Um diretor não pode ser posicionado com nenhuma outra função de servidor. Para obter detalhes sobre como planejar a topologia de diretor apropriada, consulte [cenários do diretor do Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.

  - O proxy inverso, que não é um componente do Lync Server 2013, mas é necessário se você deseja dar suporte ao compartilhamento de conteúdo da Web para usuários federados ou dar suporte ao tráfego de mobilidade. Você não pode colocar um servidor proxy reverso com qualquer função de servidor do Lync Server 2013, mas pode implementar o suporte para proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativo. Para obter detalhes sobre servidores proxy invertido, consulte Configurando [servidores proxy inversos para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) na documentação de implantação.

<div>


> [!NOTE]  
> No Lync Server 2013, A conferência A/V, o monitoramento e o arquivamento são executados em servidores front-end e não são mais funções de servidor separadas.



</div>

Todos os pools de front-end e servidores Standard Edition que você implanta em um site central compartilham qualquer um dos itens a serem implantados para o site central:

  - Pool de directors ou diretor

  - Servidor ou pool de mediação autônomo

  - Servidor Office Web Apps

  - Servidor de borda ou o pool de bordas

  - Servidor ou pool de chat persistente

  - Monitoramento

  - Archiving

<div>


> [!NOTE]  
> Um servidor Exchange UM pode ser implementado com sua implantação do Lync Server 2013 se você quiser oferecer suporte à integração de mensagens unificadas do Exchange 2013, mas não é um componente do site do Lync Server 2013.



</div>

Vários sites centrais também podem compartilhar qualquer um dos seguintes itens implantados em um site central:

  - Servidor ou pool de mediação autônomo

  - Servidor de borda ou o pool de bordas

  - Servidor ou pool de chat persistente

  - Archiving

  - Monitoramento

<div>


> [!NOTE]  
> Um servidor Exchange UM pode ser implementado com a implantação do Lync Server 2013 e compartilhado por vários sites centrais, mas não é um componente do site do Lync Server 2013.



</div>

Para obter detalhes sobre funções e funcionalidades do servidor do Lync Server 2013, consulte [funções de servidor no Lync server 2013](lync-server-2013-server-roles.md) na documentação de planejamento.

Para obter um resumo do suporte à colocação do servidor do Lync Server 2013, consulte [colocação do servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md).

Além das funções de servidor e da funcionalidade abordada anteriormente nesta seção, o Lync Server 2013 tem componentes e opções adicionais, que podem incluir alguns ou todos os seguintes itens:

  - Firewalls

  - Gateways PSTN (se a implantação do Enterprise Voice estiver sendo implantada)

  - Servidor Exchange UM

  - Balanceamento de carga DNS

  - Balanceadores de carga de hardware

  - Bancos de dados do SQL Server

  - Compartilhamentos de arquivo

Para obter detalhes sobre todos os recursos, componentes e opções do Lync Server 2013, consulte a documentação de planejamento.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologias e componentes de sites de ramificação (local)

Um site de filial está associado a um site central, e cada aplicativo de ramificação sobreviventes em um site de filial está associado a um pool de front-end da edição Enterprise ou um servidor Standard Edition no site central associado. Os sites de filiais dependem do site central para a maioria da funcionalidade, para que os componentes em um site de filial contenham apenas os seguintes itens:

  - Um aparelho de ramificação sobreviventes que combina um gateway PSTN (rede telefônica pública comutada) com alguma funcionalidade do Lync Server. Um servidor de mediação pode ser colocado na instância do registrador do aplicativo de ramificação sobreviventes, e você pode implantar um servidor autônomo de mediação ou um pool de servidores de mediação autônomos.

  - Um servidor de ramificação sobreviventes, que é um servidor que executa o Windows Server com software do Lync Server 2013 registrador e Media Server instalado.

  - Um gateway PSTN autônomo (não faz parte do Appliance de ramificação sobreviventes) e um servidor de mediação autônomo.

Os requisitos para servidores de ramificações sobreviventes são os mesmos dos requisitos para qualquer função de servidor do Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

