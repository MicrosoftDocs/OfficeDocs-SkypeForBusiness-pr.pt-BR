---
title: 'Lync Server 2013: Novos recursos do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Novos recursos do Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários participantes, com base em tópicos que persistem ao longo do tempo. O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:

  - Melhorar a comunicação entre equipes geograficamente dispersas e de várias funções

  - Amplie o reconhecimento e a participação em informações

  - Melhorar a comunicação com a sua organização estendida

  - Reduzir a sobrecarga de informações

  - Melhorar o reconhecimento de informações

  - Aumentar a dispersão de informações e conhecimento importantes

O Lync Server 2013, o servidor de chat persistente não está disponível no Microsoft Office 365. No momento, ele só está disponível para clientes do Lync 2013 local.

No Lync 2013, a funcionalidade de chat persistente é integrada ao cliente Lync 2013. Como resultado, os usuários têm acesso a mensagens instantâneas/presença, áudio/vídeo, conferência e chat persistente em todos os clientes do Lync 2013. Para obter mais informações sobre o cliente Lync 2013, <http://go.microsoft.com/fwlink/p/?linkid=270877>consulte.

Este tópico descreve as alterações de recursos entre a nova versão do Lync Server 2013, o servidor de chat persistente e a versão anterior (Microsoft Lync Server 2010, chat em grupo), incluindo:

  - Oferecer uma experiência administrativa no painel de controle do Lync Server e eliminar a ferramenta de administração do chat em grupo

  - Integrar as configurações de servidor de chat persistente ao construtor de topologias eliminando a ferramenta de configuração de chat em grupo

  - Facilitar a migração e a atualização de versões anteriores do servidor de chat persistente

  - Fornecer alta disponibilidade e soluções de recuperação de desastres

Para obter mais detalhes sobre a versão mais recente do servidor de chat persistente, consulte o seguinte:

  - A ajuda de chat persistente <http://go.microsoft.com/fwlink/p/?linkid=270945> em que fornece uma lista detalhada de recursos de chat persistente, como eles funcionam e como usá-los durante a execução do servidor de chat persistente.

  - O [servidor de chat planejando para persistência no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento [implantando o servidor de chat persistente no Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) na documentação de implantação, [migração do Lync Server 2010, chat em grupo ou Office Communications Server 2007 R2 Grupo chat para o Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) na documentação de migração e [Gerenciamento do Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md) na documentação de operações e todos fornecem instruções para configurar Servidor de chat persistente.

  - O arquivo. msi da documentação do servidor de chat persistente (arquivo do Windows Installer) permite que os usuários acessem documentação offline abrangente sobre o servidor de chat persistente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Alterações de topologia de chave para o servidor de chat persistente

As seguintes alterações de alto nível para o servidor de chat persistente incluem:

O servidor de chat persistente agora é uma função de servidor. No Microsoft Lync Server 2010, o servidor de chat de grupo era um aplicativo confiável de terceiros para o Microsoft Lync Server 2010. O chat persistente pode ser adicionado à sua topologia do Lync Server 2013 usando o construtor de topologias. No Lync Server 2013, a funcionalidade do servidor de chat persistente é implementada usando três novas funções de servidor:

  - **PersistentChatService:** Esta é a função de front-end para chats persistentes. Nas implantações da edição padrão, a função serviço persistente do servidor de chat é posicionada no servidor do Standard Edition implantado pelo bootstrapper, como qualquer outra função do Lync Server. Nas implantações do Enterprise Edition, a função serviço de chat persistente é implantada em computadores autônomos pelo bootstrapper, como qualquer outra função do Lync Server.

  - **PersistentChatStore:** Servidor back-end que corresponde ao banco de dados de conteúdo de chat persistente, no qual todo o conteúdo do chat é armazenado.

  - **PersistentChatComplianceStore:** Função de servidor back-end que corresponde ao banco de dados de conformidade de chat persistente, em que todos os eventos de conformidade são armazenados.

Essas funções de servidor de chat persistente são opcionais e são instaladas apenas por clientes que desejam funcionalidades abrangentes de servidor de chat persistente. A função **PersistentChatComplianceStore** só será necessária se você optar por implantar a conformidade de chat persistente.

A função **PersistentChatService** executa dois serviços:

  - Serviço de chat persistente

  - Serviço de conformidade de chat persistente

Esses serviços são executados em cada servidor de chat persistente fornecem alta disponibilidade para esses serviços em um pool de servidores de chat persistentes de multiservidor.

Além disso, para dar suporte ao upload e download de arquivo em salas de chat persistente, o servidor de chat persistente inclui um serviço Web. Anteriormente, esse serviço era posicionado no servidor de chat persistente, no servidor front-end e nos serviços de informações da Internet (IIS) necessários para ser instalado como pré-requisito. No servidor de chat persistente do Lync Server 2013, o serviço de carregamento/download da Web é posicionado com o servidor front-end do Lync Server 2013. Como um efeito colateral, os serviços de informações da Internet (IIS) não são mais pré-requisitos para o servidor de chat persistente. O serviço Web de carregamento/download de arquivos é identificado como **PersistentChat** no Gerenciador dos serviços de informações da Internet (IIS).

<div>


> [!IMPORTANT]  
> A função <STRONG>PersistentChatService</STRONG> pode ser executada no mesmo servidor que um servidor front-&nbsp;end do Lync Server 2013 apenas se esse servidor front-end for&nbsp;um servidor front-end da edição padrão. A função <STRONG>PersistentChatService</STRONG> não pode ser executada independentemente de um servidor&nbsp;Front-End do Lync Server 2013. Ele só pode ser instalado no contexto de uma implantação do Lync Server 2013.



</div>

No servidor de chat persistente, o serviço de pesquisa foi eliminado. No Lync Server 2010, chat em grupo, o serviço de pesquisa foi executado em cada servidor de front-end do servidor de chat de grupo e executou o roteamento para um dos servidores de canal. O Lync Server 2013 depende do roteamento usando objetos de contato, em que cada pool de servidores de chat persistente é representado por um objeto de contato que é usado pelos servidores front-end do Lync Server para identificar e direcionar solicitações para um pool de servidores de chat persistente apropriado e para um dos computadores que executam o servidor de chat persistente no pool.

No Lync Server 2013, há modificações do serviço de conformidade:

  - No Lync Server 2010, o serviço de conformidade executou autônomo (não posicionado) e somente em um único servidor. O serviço de conformidade agora é executado em todos os servidores de front-end do servidor de chat persistente, juntamente com o serviço de chat persistente, e, portanto, fornece alta disponibilidade em um pool de servidores de chat persistentes de multiservidor. Um único adaptador de conformidade pode ser configurado para extrair dados do banco de dados de conformidade e em um dos outros sistemas (arquivo XML, arquivos hospedados pelo Exchange e assim por diante). O servidor de chat persistente inclui um adaptador XML.

  - A fila de enfileiramento de mensagens (também conhecida como MSMQ) que é compartilhada pelo serviço de chat persistente e o serviço de conformidade em cada servidor front-end de servidor de chat persistente é agora uma fila particular compartilhada somente pelos dois serviços. Todos os serviços de conformidade gravam no mesmo banco de dados back-end de conformidade. Eles também são lidos nesse banco de dados, com a finalidade de enviar os dados para a instância do adaptador. O servidor back-end de conformidade é representado como uma nova função de servidor back-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Como nas versões anteriores, todos os dados de conformidade são processados apenas uma vez. Os dados podem ser processados por qualquer uma das instâncias de adaptador invocadas pelo serviço de conformidade executado nos vários computadores do Lync Server 2013, do servidor de chat persistente. Em um servidor de chat persistente, qualquer uma das instâncias de adaptador pode processar os dados.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obter informações sobre como instalar o enfileiramento de mensagens, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">instalar sistemas operacionais e software de pré-requisito em servidores para o Lync Server 2013</A> na documentação de implantação.

    
    </div>

No Lync Server 2013, existem melhorias na alta disponibilidade e recuperação de desastres:

  - Melhorias de alta disponibilidade: o espelhamento do SQL Server é usado para fornecer alta disponibilidade para o banco de dados de conteúdo do servidor de chat persistente e o banco de dados de conformidade de chat persistente em um Data Center (no local).

  - Melhorias na recuperação de desastres: o servidor de chat persistente dá suporte a uma arquitetura de pool ampliada que permite que um único pool de servidor de chat persistente seja ampliado entre dois sites (ou seja, um único pool lógico na topologia, com servidores no pool fisicamente localizado em dois sites). O envio de log do SQL Server é usado para recuperação de desastres entre sites.

Para obter mais informações sobre alta disponibilidade e recuperação de desastres, consulte [Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) na documentação de implantação.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Principais alterações de administração e gerenciamento para o servidor de chat persistente

O Lync Server 2013 tornou mais fácil administrar e gerenciar o servidor de chat persistente fornecendo:

  - Administração e gerenciamento unificados. O Lync Server 2013 torna mais fácil gerenciar e administrar o servidor de chat persistente usando ferramentas que já são familiares aos administradores do Lync. O servidor de chat persistente inclui uma experiência de interface de usuário administrativa integrada ao painel de controle do Lync Server, que aborda problemas de desempenho com as versões anteriores da interface de usuário do servidor de chat do grupo. Além disso, o servidor de chat persistente inclui uma coleção de cmdlets do Windows PowerShell para administrar e gerenciar categorias persistentes do servidor de chat, salas persistentes do servidor de chat (incluindo excluir salas e limpar conteúdo obsoleto) e suplementos.

  - Modelo de administração simplificado. O Lync Server 2013 mudou e simplificou o modelo de servidor de chat persistente atendendo às principais exigências do cliente a seguir:
    
      - Remova as hierarquias complexas aninhadas de escopos e categorias.
    
      - Suporte para definir listas de negação e listas permitidas (escopos) para clientes atuais do MindAlign que estão planejando migrar para o servidor de chat persistente.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>O que há de diferente nas funções de usuário das versões anteriores do servidor de chat em grupo?

Lync Server 2010, o chat em grupo tinha uma função de administrador de usuários, uma função de administrador da sala de chat e uma função de administrador do Lync Server que pode gerenciar suplementos. o servidor de chat persistente simplesmente fornece uma função de administrador de chat persistente (que é semelhante a outro Lync Funções de controle de acesso baseado em função do servidor (RBAC)). Qualquer pessoa que é membro dessa função RBAC pode gerenciar salas de chat, suplementos e categorias (e, portanto, obter acesso do usuário para essas categorias) e a configuração do pool do servidor de chat persistente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>O que há de diferente nas categorias de salas de chat de versões anteriores do servidor de chat em grupo?

As categorias de sala de chat não podem mais ser aninhadas, e a categoria raiz não pode mais ser modificada. AllowedMembers/DeniedMembers compreende o que é um escopo usado para estar nas versões do servidor de chat de grupo herdado (exceto por não ter sido compatível com a especificação de uma lista negada). Escopos não podem mais ser substituídos porque não há categorias aninhadas. Um administrador de chat persistente no Lync Server 2013 pode criar e gerenciar categorias de salas de chat. Como parte da criação e do gerenciamento de categorias de salas de chat, um administrador de chat persistente pode configurar entidades de segurança (grupos/usuários/usuários do Active Directory) que têm acesso a membros/criadores de salas de chat de uma categoria específica. Um administrador de chat persistente também pode adicionar DeniedMembers a uma categoria, e essas são exclusões explícitas da lista de permissões. DeniedMembers substitui o que está em AllowedMembers.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>O que há de diferente nas propriedades da sala de chat das versões anteriores do servidor de chat em grupo?

Há um novo conceito de salas de chat abertas no Lync Server 2013, servidor de chat persistente. Todos os membros permitidos podem participar da sala de chat, sem associação exclusiva.

As seguintes propriedades de sala de chat que foram incluídas nas versões anteriores do servidor de chat persistente foram eliminadas:

  - Tópico: agora, uma sala tem apenas uma descrição.

  - Criar nova lista de membros: em um servidor de chat persistente, todas as salas de chat começam com associação vazia (e podem ser maximizadas para uma associação que equivale aos membros permitidos).

  - Carregamento de arquivos: usado para ser uma configuração por sala de chat para controlar se o carregamento de arquivos/downloads foi permitido. Agora, isso é definido somente o nível da categoria e se aplica a todas as salas da categoria.

  - Histórico de chats: usado para ser uma configuração por sala de chat para controlar se o histórico de chats foi habilitado, mas agora está definido somente no nível de categoria e se aplica a todas as salas da categoria.

  - Convites: uma sala sempre herda a configuração convites para a categoria; ou pode ser desativado na sala. Uma sala não poderá ativar convites se a categoria tiver sido previamente definida como convites.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>O que há de diferente em políticas de versões anteriores do servidor de chat em grupo?

O servidor de chat persistente tem uma nova política do Lync habilitada com chat persistente, por usuário/pool/site/configurações globais. No cliente do Lync 2013, o ambiente de chat persistente está disponível somente para usuários habilitados pela política de chat persistente (diretamente ou por meio da configuração pool/site/global).

As versões anteriores do servidor de chat em grupo não tinham políticas integradas às políticas do Lync Server. Em uma base por usuário e por categoria/sala, usando o recurso **pode carregar arquivos** por usuário, você pode transformar o usuário em um administrador de usuário, um administrador de salas de chat ou configurar a capacidade do usuário para carregar arquivos. O recurso de **carregamento de arquivo** persistente do servidor de chat é apenas por categoria.

</div>

<div>

## <a name="logging"></a>Registro em log

O registro em log para o servidor de chat persistente e o System Center Operations Manager é integrado ao log de rastreamento do Lync Server 2013.

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejando o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

