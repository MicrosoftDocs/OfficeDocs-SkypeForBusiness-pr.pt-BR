---
title: As topologias do Lync Server 2013 suportadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a74be867305f3e42d1e9e303baedbddd22f485
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologias com suporte no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-14_

O Lync Server 2013 oferece suporte à implantação de sites no local em uma organização e à integração de implantações locais com implantações do Lync Online, que é conhecido como implantação híbrida. Em uma implantação híbrida, alguns usuários são hospedados no local e outros, online.

Para implantações locais, o Lync Server 2013 oferece suporte à implantação de um ou mais sites que podem ser dimensionados para atender aos requisitos de alta disponibilidade e local. É possível estruturar esses sites e seus componentes para atender aos requisitos de acesso e resiliência de sua organização.

Uma implantação local do Lync Server 2013 consiste no seguinte:

  - A implantação deve conter pelo menos um site central (também conhecido como data center). Cada site central deve conter pelo menos um pool de Front-Ends Enterprise Edition ou servidor Standard Edition. Isso consiste no seguinte:
    
      - O pool de Front-Ends Enterprise Edition, que consiste em um ou mais servidores de Front-End  (normalmente, pelo menos dois servidores de Front-End para dimensionamento) e um servidor de Back-End separado. Um pool de front-ends pode conter no máximo doze servidores front-end. O balanceamento de carga é exigido para servidores de Front-End. Para o tráfego SIP, é recomendável o balanceamento de carga DNS, mas o balanceamento de carga de hardware também é suportado. Se usar o balanceamento de carga DNS para o tráfego SIP, você ainda precisará de um balanceador de carga de hardware para o tráfego HTTP. Recomendamos o espelhamento do SQL Server para alta disponibilidade de bancos de dados. O banco de dados de back-end exige uma instância separada, mas você pode colocar o banco de dados de arquivamento, de monitoramento, de chat persistente e de conformidade do chat persistente com ele. O Lync Server 2013 suporta o uso de um cluster compartilhado para os compartilhamentos de arquivos em sua implantação. Para obter detalhes sobre os requisitos de armazenamento de banco de dados, consulte [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md). Para obter detalhes sobre os requisitos de armazenamento de arquivos, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Se você colocar os bancos de dados do Lync Server, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho. Para verificar os recursos de failover, é recomendável testar todos os cenários de failover.

        
        </div>
    
      - Servidor Standard Edition que inclui um banco de dados do SQL Server Express colocado.

  - A implantação também pode ter uma ou mais filiais associadas a um site central.

Esta seção descreve os sites e os componentes de uma implantação do Lync Server 2013. Para obter detalhes sobre o site, a topologia e o planejamento de componentes do Lync Server 2013, consulte [noções básicas de topologia que você deve saber antes de planejar o Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento. Para obter detalhes sobre a integração de componentes de versões anteriores, consulte [supported Migration Paths and coexistência Scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Não há suporte para pools estendidos para as funções de servidor front-end, Edge, mediação e diretor.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologias e componentes do site central (local)

Embora uma topologia de site central deva incluir um pool de Front-Ends ou servidor Standard Edition, cada site central também pode conter o seguinte:

  - Diversos pools de Front-Ends, que podem estar no mesmo domínio ou em domínios diferentes. No entanto, todos os servidores de Front-End de um pool de Front-Ends e o servidor de Back-End desse pool devem estar no mesmo domínio.

  - Diversos Servidores Standard Edition.

  - O servidor do Office Web Apps, que é usado com o Office Web Applications no Lync Server 2013 para lidar com o compartilhamento e a renderização de apresentações do Microsoft PowerPoint.

  - Servidor de borda ou o pool de borda em sua rede de perímetro, se você quiser que sua implantação dê suporte a parceiros federados, conectividade de IM pública, um Gateway XMPP (Extensible Messaging and Presence Protocol), acesso de usuário remoto, participação de usuários anônimos em reuniões, ou UM (Unificação de mensagens) do Exchange. Não é possível colocar nenhuma outra função de servidor com o servidor de borda. É recomendável o balanceamento de carga DNS, quando apropriado, mas o balanceamento de carga de hardware também é suportado. As interfaces de borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda. Para obter detalhes sobre os requisitos de balanceamento de carga e suporte, consulte [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e [implantação de acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.

  - Servidor ou pool de mediação, se você quiser dar suporte à conferência de discagem ou voz corporativa em um pool de front-ends no site central. Dependendo de como você implantou o suporte do Enterprise Voice, pode colocar o servidor de mediação em um pool de front-ends (o padrão) ou implantar um servidor ou pool de mediação autônomo. Você pode usar o balanceamento de carga de aplicativo, de hardware ou de DNS (quando apropriado) para distribuir o tráfego de um ponto de gateway de um pool de servidores de mediação, incluindo um gateway PSTN, IP-PBX ou controle de borda de sessão de tronco SIP (SBC). Para obter detalhes sobre como planejar a topologia do servidor de mediação apropriada, consulte [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) na documentação de planejamento.

  - Servidor de chat persistente, se você quiser que os usuários sejam capazes de participar de conversas com base em um tópico que persistem ao longo do tempo. Para fornecer mais capacidade e maior confiabilidade, sua topologia pode incluir vários computadores que executam o servidor de chat persistente. Não é possível colocar o servidor de chat persistente com outras funções de servidor em um pool corporativo. No entanto, você pode colocar o servidor de chat persistente em um servidor Standard Edition. O chat persistente exige um banco de dados e, se você implementar a conformidade de chat persistente, um banco de dados de conformidade de chat persistente, porém os bancos de dados poderão ser colocados com o banco de dados de arquivamento, de monitoramento ou no servidor de Back-End de um pool de Front-Ends Enterprise Edition. Para obter detalhes sobre como planejar a topologia do servidor de chat persistente apropriada, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

  - Monitoramento, se quiser oferecer suporte à coleta de dados sobre sua QoE (experiência de qualidade) de áudio/vídeo e CDR (gravação de detalhes da chamada) para o Enterprise Voice e as conferências de áudio/vídeo de sua implantação. Opcionalmente, você pode instalar o Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa o monitoramento de dados de CDR e QoE para gerar alertas quase em tempo real que mostram a integridade da chamada e a qualidade da mídia. O monitoramento, quando implantado, é colocado em servidores Fron-End ou um servidor Standard Edition. O monitoramento exige um banco de dados, mas o banco de dados pode ser colocado com o banco de dados de arquivamento, de chat persistente, do conformidade de chat persistente ou no servidor Back-End de um pool de Front-Ends Enterprise Edition.

  - Arquivamento, se quiser arquivar comunicações de mensagens instantâneas e conteúdo de reuniões (por motivos de conformidade) em sua implantação. O arquivamento, quando implantado, é colocado em servidores de Front-End ou em um servidor Standard Edition. O armazenamento de arquivamento requer a implantação de um banco de dados de arquivamento ou integração com o armazenamento do Exchange 2013. Se você usar ambos, que é conhecido como *modo misto*, o armazenamento 2013 do Exchange é usado para armazenar dados de arquivamento para usuários hospedados no Exchange 2013, e o banco de dados de arquivamento é usado para arquivar dados de todos os outros usuários em sua implantação. Se precisar de uma banco de dados de arquivamento, ele poderá ser colocado no banco de dados de monitoramento, de chat persistente, de conformidade do chat persistente ou no servidor de Back-End de um pool de Front-Ends. Para obter detalhes sobre como planejar a topologia de arquivamento adequada, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.

  - Pool de diretor ou diretor, se você quiser facilitar a resiliência e o redirecionamento de solicitações de usuário do Lync Server 2013 para o pool de local do usuário, que pode ser um pool de front-ends Enterprise Edition ou um servidor Standard Edition. É recomendável que seja implantado um diretor ou pool de diretores em cada site central que ofereça suporte ao acesso de usuários externos e em cada site central no qual é feita a implantação de um ou mais pools de Front-Ends. Cada pool de diretores pode conter um máximo de dez diretores. Um diretor não pode ser colocado com nenhuma outra função de servidor. Para obter detalhes sobre como planejar a topologia de diretor apropriada, consulte [cenários para o diretor no Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.

  - O proxy reverso, que não é um componente do Lync Server 2013, mas será necessário se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados ou para oferecer suporte ao tráfego de mobilidade. Não é possível colocar um servidor de proxy reverso com nenhuma função de servidor do Lync Server 2013, mas você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013, configurando o suporte em um servidor de proxy reverso existente em sua organização usado para outros Emprego. Para obter detalhes sobre servidores de proxy reverso, confira [Configurando servidores de proxy reverso para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) na documentação de implantação.

<div>


> [!NOTE]  
> No Lync Server 2013, A conferência A/V, o monitoramento e o arquivamento são executados em servidores front-end e não são mais funções de servidor separadas.



</div>

Todos os pools de front-ends e servidores Standard Edition que você implanta em um site central compartilham qualquer um dos seguintes itens implantados para o site central:

  - Diretor ou pool de diretor

  - Servidor ou pool de mediação autônomo

  - Servidor do Office Web Apps

  - Servidor de borda ou pool de borda

  - Servidor ou pool de chat persistente

  - Monitoramento

  - Arquivamento

<div>


> [!NOTE]  
> Um servidor de UM do Exchange pode ser implementado com sua implantação do Lync Server 2013 se você deseja oferecer suporte à integração da Unificação de mensagens do Exchange 2013, mas não é um componente do site do Lync Server 2013.



</div>

Vários sites centrais também podem compartilhar qualquer um dos seguintes itens implantados em um site central:

  - Servidor ou pool de mediação autônomo

  - Servidor de borda ou pool de borda

  - Servidor ou pool de chat persistente

  - Arquivamento

  - Monitoramento

<div>


> [!NOTE]  
> Um servidor de UM do Exchange pode ser implementado com sua implantação do Lync Server 2013 e compartilhado por vários sites centrais, mas não é um componente do site do Lync Server 2013.



</div>

Para obter detalhes sobre funções e funcionalidades de servidor do Lync Server 2013, consulte [Server Roles in Lync server 2013](lync-server-2013-server-roles.md) na documentação de planejamento.

Para obter um resumo do suporte à colocação do servidor do Lync Server 2013, consulte [colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md).

Além das funções e funcionalidades de servidor abordadas anteriormente nesta seção, o Lync Server 2013 tem componentes e opções adicionais, que podem incluir alguns ou todos os seguintes itens:

  - Firewalls

  - Gateways PSTN (se estiver implantando o Enterprise Voice)

  - Servidor UM do Exchange

  - Balanceamento de carga DNS

  - Balanceadores de carga de hardware

  - Bancos de dados do SQL Server

  - Compartilhamentos de arquivo

Para obter detalhes sobre todos os recursos, componentes e opções do Lync Server 2013, consulte a documentação de planejamento.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologias e componentes do site de filial (local)

Um site de filial é associado a um site central, e cada aparelho de filial persistente em um site de filial é associado a um pool de front-ends Enterprise Edition ou um servidor Standard Edition no site central associado. Os sites de filiais dependem do site central para a maioria de suas funcionalidades, de forma que os componentes em um site de filial contenham apenas o seguinte:

  - Um aparelho de filial persistente, que combina um gateway PSTN (rede telefônica pública comutada) com algumas funcionalidades do Lync Server. Um servidor de mediação pode ser colocado com a instância do registrador no aparelho de filial persistente, e você pode implantar um servidor de mediação autônomo ou pool de servidores de mediação.

  - Um servidor de filial persistente, que é um servidor que executa o Windows Server e que tem o software de servidor de mediação do Lync Server 2013 instalado.

  - Um gateway PSTN autônomo (não faz parte do aparelho de filial persistente) e um servidor de mediação autônomo.

Os requisitos para servidores de filial persistentes são os mesmos dos requisitos para qualquer função de servidor do Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

