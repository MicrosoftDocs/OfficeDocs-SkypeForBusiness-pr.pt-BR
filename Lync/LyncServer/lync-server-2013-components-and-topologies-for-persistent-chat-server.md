---
title: 'Lync Server 2013: componentes e topologias do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Componentes e topologias do servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

O servidor de chat persistente tem suporte para configurações de servidor único e de vários servidores. O servidor de chat persistente também pode ser executado em um servidor do Lync Server 2013 Standard Edition. Essas configurações consistem nos seguintes componentes e topologias de servidor de chat persistente.

<div>

## <a name="persistent-chat-server-components"></a>Componentes persistentes do servidor de chat

A instalação da versão mais recente do servidor de chat persistente exige os seguintes componentes:

  - Um ou mais computadores que executam o servidor de chat persistente e fornecimento dos seguintes serviços:
    
      - Serviço de chat persistente
    
      - Serviço de conformidade, que é ativado quando a conformidade é habilitada
    
    <div>
    

    > [!IMPORTANT]  
    > No Lync Server 2013, os serviços Web de chat persistente para carregamento/download de arquivo agora são posicionados com o&nbsp;servidor front-end do Lync Server 2013.<BR>Os serviços Web de chat persistente para gerenciamento de sala de chat também são posicionados com&nbsp;o servidor front-end do Lync Server 2013.

    
    </div>

  - Servidor (es) (s) (mais de um servidor, se o espelhamento for usado) que hospedam o banco de dados back-end do SQL Server para hospedar o banco de dados de conteúdo de chat persistente no qual o conteúdo da sala de chat, salas e categorias são armazenados.
    
    <div>
    

    > [!NOTE]  
    > O banco de dados back-end armazena dados do histórico do chat, incluindo informações sobre categorias e salas de chat persistentes que são criadas.

    
    </div>

  - Se a conformidade foi habilitada, um (s) servidor (es) (mais de um servidor se o espelhamento for usado) que hospeda o banco de dados back-end do SQL Server para hospedar o banco de dados de conformidade de chat persistente, em que os eventos de conformidade e o conteúdo de chat com a finalidade de conformidade são armazenados.

Para administrar o servidor de chat persistente a partir de um computador separado (como um console administrativo), use o painel de controle do Lync Server no computador. Esse computador deve ser implantado em um domínio de serviços de domínio Active Directory, com pelo menos um servidor de catálogo global na raiz da floresta.

Para obter detalhes sobre os requisitos de hardware e software para o servidor de chat persistente, consulte [requisitos técnicos para servidor de chat persistente no Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md)e [suporte a infraestrutura e software do servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.

</div>

<div>

## <a name="supported-collocation"></a>Colocação compatível

O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, oferecendo a flexibilidade para economizar custos de hardware executando vários componentes em um servidor (se você tiver uma pequena organização) ou para executar componentes individuais em servidores diferentes (se você tiver uma organização maior que precisa de escalabilidade e desempenho). Fatores de escalabilidade certamente devem ser considerados antes de você decidir se deseja posicionar componentes.

Se a conformidade estiver habilitada, o serviço de conformidade de chat persistente será posicionado com o servidor front-end do Lync Server 2013.

O servidor de chat persistente pode ser implantado no servidor Standard Edition. O servidor back-end persistente do servidor de chat e o banco de dados de conformidade de chat persistente podem ser posicionados no servidor Standard Edition no servidor back-end do SQL Server Express local. Para obter detalhes sobre os componentes que podem ser posicionados, consulte [colocação do servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

Para o Lync Server 2013 Enterprise Edition, os servidores de chat persistentes não podem ser posicionados no servidor Enterprise Edition. O banco de dados do SQL Server para servidor de chat persistente pode ser posicionado com o banco de dados de servidor back-end de um pool de front-end Enterprise Edition. O banco de dados do SQL Server para conformidade de chat persistente também pode ser posicionado com o banco de dados de servidor back-end de um pool da edição Enterprise.

<div>


> [!IMPORTANT]  
> O servidor que hospeda o banco de dados de chat persistente pode hospedar outros bancos de dados. No entanto, quando você considera posicionar o banco de dados de chat persistente com outros bancos de dados, lembre-se de que, se você estiver armazenando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados de chat persistente pode crescer muito grande. Por esse motivo, não recomendamos posicionar o banco de dados de chat persistente com o banco de dados back-end.



</div>

Se você colocar o banco de dados de chat persistente com o banco de dados back-end, poderá usar uma única instância do SQL Server para qualquer um ou todos os bancos de dados ou poderá usar uma instância separada do SQL Server para cada banco de dados, com a seguinte limitação:

  - Cada instância do SQL Server pode conter apenas um único banco de dados back-end e um único banco de dados persistente de chat.

Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [colocação de servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologias persistentes do servidor de chat

O servidor de chat persistente tem suporte para as seguintes topologias:

  - Lync Server 2013 Enterprise Edition Single Server persistent chat servidor front end Server

  - Lync Server 2013 Enterprise Edition vários servidores servidor de chat persistente servidor front-end

  - Servidor do Lync Server 2013 Standard Edition usando SQL Server Express

  - Lync Server 2013 Standard Edition Server e servidor de chat persistente em um servidor separado usando o Standard Edition Server como o próximo servidor de salto.

Você pode adicionar um servidor de chat persistente à implantação do Lync Server 2013 usando o construtor de topologias. Você pode adicionar um único servidor ou um pool de servidores de chat persistente do servidor múltiplo à sua topologia.

<div>


> [!IMPORTANT]  
> Depois de criar um pool de servidores de chat persistentes com um único servidor usando o construtor de topologias, não é possível adicionar mais servidores ao pool.



</div>

<div>

## <a name="single-server-topology"></a>Topologia de servidor único

A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma única topologia de servidor front-end persistente do servidor de chat. Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospede o banco de dados do SQL Server e se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.

<div>


> [!IMPORTANT]  
> Você não pode adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias. Recomendamos usar a topologia de pool de vários servidores, mesmo se você estiver usando um único servidor, para que você possa adicionar mais servidores mais tarde, se necessário...



</div>

A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.

**Único servidor de chat persistente**

![Topologia de servidor único com serviço de conformidade](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia de vários servidores

Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [planejamento para servidor de chat persistente no Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastres permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em standby). Cada servidor pode oferecer suporte a quantos usuários simultâneos do 20.000, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores. Uma topologia de vários servidores é a mesma que a topologia de servidor único, exceto que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados para maior. Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio dos serviços de domínio Active Directory do Lync Server e no serviço de conformidade.

A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.

**Vários servidores de chat persistentes**

![Topologia de vários servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")

As topologias de vários servidores fornecem a funcionalidade de pool de servidores. Em um pool de servidores, os serviços de chat persistente se comunicam e compartilham dados. Por exemplo, o histórico de chats originalmente lançado em um serviço de chat persistente está disponível em qualquer serviço de chat persistente do sistema. Um arquivo carregado por meio de um serviço de chat persistente pode ser acessado por qualquer serviço de chat persistente. Os usuários podem ser conectados a diferentes servidores de front-end do servidor de chat persistente e podem ser chats e se comunicar uns com os outros.

A porta padrão do TCP 8011 conecta um servidor a um pool de servidores e é usada pelo serviço de chat persistente para se comunicar entre si ou para fins administrativos.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

