---
title: 'Lync Server 2013: definindo seus requisitos para servidor de chat persistente'
description: 'Lync Server 2013: definindo seus requisitos para servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af3fab1d91b78a5993f723b8fc6b375e4ab7cee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545347"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definindo os requisitos de sua organização para o servidor de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-15_

Antes de implantar o servidor de chat persistente para sua organização, é essencial considerar as seguintes perguntas importantes para otimizar sua implantação:

  - Quem (perfil do usuário) deve ser habilitado para o servidor de chat persistente? O servidor de chat persistente está habilitado por uma política que pode ser definida em um nível global, de site, de pool ou de usuário.

  - Quantos usuários (escala) devem ser habilitados para o servidor de chat persistente? O servidor de chat persistente oferece suporte a 150.000 usuários provisionados (habilitados por política) e um máximo de 80.000 usuários simultâneos usando o servidor de chat persistente. Um único servidor de chat persistente pode suportar 20.000 usuários conectados e um único pool de servidor de chat persistente pode ter até quatro servidores ativos para um total de 80.000 usuários conectados simultaneamente.

  - Você está migrando de uma versão anterior do servidor de chat de grupo ou está implantando o servidor de chat persistente pela primeira vez?

  - Há requisitos de conformidade? O servidor de chat persistente oferece suporte à conformidade. O serviço de conformidade é executado no servidor de front-end do servidor de chat persistente, em oposição ao requisito para um computador separado nas implantações anteriores do servidor de chat de grupo. A conformidade é opcional e, se escolhida, requer um banco de dados de conformidade que deve ser configurado para armazenar dados e eventos de conformidade. Você também pode configurar um adaptador para obter os dados do banco de dados de conformidade e convertê-los em outro formato (como arquivos XML ou arquivos mortos hospedados no Exchange).

  - Como você deseja controlar escopos, limites éticos e acesso? É possível definir as **Categorias** para segregar esses limites e escolher quem estará habilitado para estar nas salas que forem criadas para cada uma dessas categorias.

  - Como você deseja controlar quem pode criar salas? É possível configurar em **Criadores**, de forma adequada para a suas categorias, quem pode criar salas. Os criadores podem atribuir outros membros como **Gerentes de Sala de Chat** para gerenciamento contínuo das salas (adicionando ou removendo membros adicionais), de acordo com o escopo para **AllowedMembers/DeniedMembers** configurados por categoria.

  - Como você deseja criar salas? O servidor de chat persistente fornece um recurso baseado na Web para a criação e o gerenciamento de salas. Isso pode ser iniciado no cliente do Lync 2013. Você pode optar por definir uma solução personalizada (usando o Software Development Kit (SDK) do servidor de chat persistente que implementa seus requisitos de negócios e fluxos de trabalho e configura o servidor de chat persistente para direcionar os usuários para sua solução personalizada.

  - Que tipo de suplementos você deseja provisionar? Os **suplementos** aprimoram a experiência na sala aproveitando o painel de extensibilidade no cliente do Lync 2013 para fornecer contexto relevante à sala. É possível escolher quais suplementos gerais podem ser mais úteis (por exemplo, o site da sua empresam documentos de colaboração interna e etc.). Os gerentes das salas de chat podem escolher um dos suplementos registrados e associá-lo às salas, se desejado.

  - Quais tipos de requisitos de alta disponibilidade e recuperação de desastres você tem? O servidor de chat persistente suporta o espelhamento do SQL Server e o cluster do SQL Server para alta disponibilidade e oferece suporte a até 8 servidores (4 ativos e 4 em espera) em um pool estendido com o envio de logs do SQL Server para recuperação de desastres.

  - Há requisitos da regulamentação? Se sua empresa estiver em um país/região onde os dados precisam ser mantidos no país, talvez você precise implantar vários pools de servidores de chat persistentes, cada local em uma geografia específica. Uma sala, uma categoria ou um suplemento não abrange pools, ele pertence a apenas um pool de servidor de chat persistente. Você pode gerenciar o conjunto de categorias, suplementos e salas para cada pool do servidor de chat persistente. Os usuários podem ser configurados para ter acesso a salas em um ou mais pools usando o escopo Membros permitidos de categoria ou o escopo de associação da sala, dependendo de como projetar suas categorias.
    
    <div>
    

    > [!IMPORTANT]  
    > Ter vários pools de servidores de chat persistente não dá mais escala (você ainda pode ter apenas 80.000 usuários conectados simultaneamente em todos os pools de servidores de chat persistentes). O principal motivo para o suporte a vários pools de servidores de chat persistente é dar suporte a questões regulamentares.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

