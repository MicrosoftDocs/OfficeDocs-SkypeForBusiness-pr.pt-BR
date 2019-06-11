---
title: 'Lync Server 2013: Definindo seus requisitos para o Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definindo os requisitos de sua organização para o Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-15_

Antes de implantar o servidor de chat persistente para a sua organização, é essencial considerar as seguintes perguntas importantes para otimizar a implantação:

  - Quem (perfil do usuário) deve ser habilitado para o servidor de chat persistente? O servidor de chat persistente está habilitado por uma política que pode ser definida em um nível global, de site, de grupo ou de usuário.

  - Quantos usuários (escala) devem ser habilitados para o servidor de chat persistente? O servidor de chat persistente dá suporte ao 150.000 usuários provisionados (habilitados pela política) e um máximo de 80.000 usuários simultâneos que usam o servidor de chat persistente. Um único Servidor de Chat Persistente pode suportar 20.000 usuários conectados e um único pool de Servidor de Chat Persistente pode ter até 4 servidores ativos para um total de 80.000 usuários conectados simultâneos.

  - Você está migrando de uma versão anterior do servidor de chat de grupo ou está implantando o servidor de chat persistente pela primeira vez?

  - Há requisitos de conformidade? O servidor de chat persistente dá suporte à conformidade. O serviço de conformidade é executado no servidor front-end persistente do servidor de chat, ao contrário do requisito para um computador separado em implantações de servidor de chat de grupo anteriores. A conformidade é opcional e, se escolhida, requer um banco de dados de conformidade que deve ser configurado para armazenar dados de conformidade e eventos. Você também pode configurar um adaptador para obter os dados do banco de dados de conformidade e convertê-los em outro formato (como arquivos XML ou arquivos hospedados pelo Exchange).

  - Como você deseja controlar escopos, limites éticos e acesso? Você pode definir **categorias** para segregar esses limites e escolher quem tem permissão para estar em salas criadas em cada uma dessas categorias.

  - Como você deseja controlar quem pode criar salas? Você pode configurar os **criadores**, apropriadamente às suas categorias, que podem criar salas. Os criadores podem atribuir outros membros como **gerentes de sala de chat** para gerenciamento contínuo das salas (adicionando ou removendo membros adicionais), de acordo com o escopo para **AllowedMembers/DeniedMembers** configurado pela categoria.

  - Como você deseja criar salas? O servidor de chat persistente fornece um recurso baseado na Web para a criação e o gerenciamento de salas. Isso pode ser iniciado pelo cliente do Lync 2013. Você pode optar por definir uma solução personalizada (usando o kit de desenvolvimento de software (SDK) do servidor de chat persistente) que implementa suas necessidades comerciais e fluxos de trabalho e configura o servidor de chat persistente para direcionar os usuários para sua solução personalizada.

  - Que tipo de suplemento você deseja provisionar? Os **suplementos** aprimoram a experiência da sala aproveitando o painel extensibilidade no cliente do Lync 2013 para fornecer contexto que é relevante para a sala. É possível escolher quais suplementos gerais podem ser mais úteis (por exemplo, o site da sua empresa, documentos de colaboração interna etc.). Os gerentes das salas de chat podem escolher um dos suplementos registrados e associá-lo às salas, se desejado.

  - Que tipo de requisito de alta disponibilidade e recuperação de desastre você tem? O servidor de chat persistente dá suporte ao espelhamento do SQL Server e ao agrupamento do SQL Server para alta disponibilidade e dá suporte a até 8 servidores (4 ativos e 4 em standby) em um pool ampliado com o envio de log do SQL Server para recuperação de desastres.

  - Há requisitos regulatórios? Se a sua empresa estiver em um país/região onde os dados precisam ser mantidos dentro do país, talvez seja necessário implantar vários pools de servidores de chat persistentes, cada um local para uma geografia específica. Uma sala, categoria ou suplemento não abrange pools — ele pertence a apenas um pool persistente do servidor de chat. Você pode gerenciar o conjunto de categorias, suplementos e salas para cada pool de servidores de chat persistente. Os usuários podem ser configurados para ter acesso a salas em um ou mais pools usando o escopo de associação do escopo ou da sala de AllowedMembers de categorias, dependendo de como projetar suas categorias.
    
    <div>
    

    > [!IMPORTANT]  
    > Ter vários pools de servidores de chat persistentes não oferece mais escalabilidade (você ainda pode ter apenas 80.000 usuários conectados simultaneamente em todos os seus pools de servidores de chat persistentes). O principal motivo para dar suporte a vários pools de servidores de chat persistentes é dar suporte a questões de regulamentação.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

