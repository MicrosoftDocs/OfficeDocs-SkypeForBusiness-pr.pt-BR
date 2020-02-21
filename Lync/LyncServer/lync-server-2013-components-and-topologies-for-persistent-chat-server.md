---
title: 'Lync Server 2013: componentes e topologias para servidor de chat persistente'
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
ms.openlocfilehash: 45707cafca4a7ed9da7cdeb5e162128ccd73468d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Componentes e topologias para servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

O servidor de chat persistente oferece suporte a configurações de servidor único e de vários servidores. O servidor de chat persistente também pode ser executado em um servidor do Lync Server 2013 Standard Edition. Essas configurações consistem nos seguintes componentes e topologias do servidor de chat persistente.

<div>

## <a name="persistent-chat-server-components"></a>Componentes do servidor de chat persistente

A instalação da versão mais recente do servidor de chat persistente requer os seguintes componentes:

  - Um ou mais computadores que executam o servidor de chat persistente e fornecem os seguintes serviços:
    
      - Serviço de chat persistente
    
      - Serviço de conformidade, que é ativado quando a conformidade é habilitada
    
    <div>
    

    > [!IMPORTANT]  
    > No Lync Server 2013, os serviços Web de chat persistente para upload/download de arquivo agora estão posicionados com o&nbsp;servidor front-end do Lync Server 2013.<BR>Os serviços Web de chat persistente para gerenciamento de salas de chat também são colocados com o&nbsp;servidor front-end do Lync Server 2013.

    
    </div>

  - Servidor (es) (mais de um servidor se o espelhamento for usado) que hospeda o banco de dados de back-end do SQL Server para hospedar o banco de dados de conteúdo de chat persistente onde o conteúdo da sala de chat, salas e categorias são armazenados.
    
    <div>
    

    > [!NOTE]  
    > O banco de dados de back-end armazena dados de histórico de chat, incluindo informações sobre categorias e salas de chat persistente criadas.

    
    </div>

  - Se a conformidade foi habilitada, um (s) servidor (es) (mais de um servidor se o espelhamento for usado) que hospeda o banco de dados de back-end do SQL Server para hospedar o banco de dados de conformidade de chat persistente, em que os eventos de conformidade e o conteúdo de chat com o objetivo de conformidade são armazenados.

Para administrar o servidor de chat persistente de um computador separado (como um console administrativo), use o painel de controle do Lync Server no computador. Esse computador deve ser implantado em um domínio de serviços de domínio do Active Directory, com pelo menos um servidor de catálogo global na raiz da floresta.

Para obter detalhes sobre os requisitos de hardware e software do servidor de chat persistente, consulte [Technical Requirements for persistent chat Server in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md)e [suporte a infraestrutura e software de servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.

</div>

<div>

## <a name="supported-collocation"></a>Colocação suportada

O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, fornecendo a flexibilidade para salvar os custos de hardware executando vários componentes em um servidor (se você tiver uma organização pequena) ou para executar componentes individuais em servidores diferentes (se você tiver um organização maior que precisa de escalabilidade e desempenho). Os fatores de escalabilidade certamente devem ser considerados antes de você decidir se quer colocar componentes.

O serviço de conformidade do chat persistente, se a conformidade estiver habilitada, será colocado com o servidor front-end do Lync Server 2013.

O servidor de chat persistente pode ser implantado no servidor Standard Edition. O servidor back-end do servidor de chat persistente e o banco de dados de conformidade de chat persistente podem ser colocados no servidor Standard Edition no servidor back-end do SQL Server Express local. Para obter detalhes sobre os componentes que podem ser colocados no local, consulte [suporte à colocação de servidor no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

Para o Lync Server 2013 Enterprise Edition, os servidores de chat persistente não podem ser colocados no servidor Enterprise Edition. O banco de dados do SQL Server para servidor de chat persistente pode ser colocado com o banco de dados de servidor back-end de um pool de front-ends Enterprise Edition. O banco de dados do SQL Server para conformidade de chat persistente também pode ser colocado com o banco de dados de servidor back-end de um pool Enterprise Edition.

<div>


> [!IMPORTANT]  
> O servidor que hospeda o banco de dados de chat persistente pode hospedar outros bancos de dados. No entanto, quando você considerar o posicionamento do banco de dados de chat persistente com outros bancos de dados, lembre-se de que se você estiver armazenando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados de chat persistente poderá crescer muito grande. Por esse motivo, não recomendamos colocar o banco de dados de chat persistente com o banco de dados back-end.



</div>

Se você colocar o banco de dados de chat persistente com o banco de dados back-end, poderá usar uma única instância do SQL Server para qualquer um ou todos os bancos de dados ou poderá usar uma instância separada do SQL Server para cada banco de dados, com a seguinte limitação:

  - Cada instância do SQL Server pode conter apenas um único banco de dados de back-end e um único banco de dados de chat persistente.

Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [supported Server Coexistence no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologias do servidor de chat persistente

O servidor de chat persistente suporta as seguintes topologias:

  - Servidor front-end do servidor de chat persistente do Lync Server 2013 Enterprise Edition Single Server

  - Lync Server 2013 Enterprise Edition servidor de front end do servidor de chat persistente de vários servidores

  - Servidor do Lync Server 2013 Standard Edition usando o SQL Server Express

  - Lync Server 2013 Standard Edition Server e servidor de chat persistente em um servidor separado usando o Standard Edition Server como servidor de próximo salto.

Você pode adicionar o servidor de chat persistente à sua implantação do Lync Server 2013 usando o construtor de topologias. Você pode adicionar um único servidor ou um pool de servidor de chat persistente de vários servidores à sua topologia.

<div>


> [!IMPORTANT]  
> Depois de criar um pool de servidor de chat persistente com um único servidor usando o construtor de topologias, não é possível adicionar mais servidores ao pool.



</div>

<div>

## <a name="single-server-topology"></a>Topologia de servidor único

A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma topologia de servidor front-end de servidor de chat persistente única. Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospeda o banco de dados do SQL Server e, se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.

<div>


> [!IMPORTANT]  
> Não é possível adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias. Recomendamos usar a topologia de pool de vários servidores, mesmo se você for usar um único servidor, para que possa adicionar mais servidores no futuro se for necessário.



</div>

A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.

**Servidor de Chat Persistente único**

![Topologia de servidor único com serviço de conformidade](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia de vários servidores

Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastre permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em espera). Cada servidor pode suportar até 20.000 usuários simultâneos, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores. Uma topologia de vários servidores é o mesmo que a topologia de servidor único, exceto pelo fato de que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados de forma mais alta. Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio de serviços de domínio do Active Directory do Lync Server e no serviço de conformidade.

A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.

**Vários Servidores de Chat Persistente**

![Topologia de vários servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")

As topologias de vários servidores fornecem a funcionalidade de pool de servidores. Em um pool de servidores, os serviços de chat persistente se comunicam e compartilham dados. Por exemplo, o histórico de chat que foi lançado originalmente em um serviço de chat persistente está disponível em qualquer serviço de chat persistente no sistema. Um arquivo carregado por meio de um serviço de chat persistente pode ser acessado por qualquer serviço de chat persistente. Os usuários podem estar conectados a servidores de front-end do servidor de chat persistente diferentes e podem estar batendo papo e se comunicar uns com os outros.

A porta padrão do TCP 8011 conecta um servidor a um pool de servidores e é usada pelo serviço de chat persistente para se comunicar entre si ou para fins administrativos.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

