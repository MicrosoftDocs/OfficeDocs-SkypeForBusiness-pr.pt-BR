---
title: 'Lync Server 2013: novos recursos do servidor de chat persistente'
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
ms.openlocfilehash: dd9288fea9105be27428ac94d992de6e147f4900
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534178"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Novos recursos do servidor de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários tópicos, com base em tópico que persistem ao longo do tempo. O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:

  - Melhorar a comunicação entre equipes geograficamente distante e multifuncionais

  - Ampliar a conscientização e participação da informação

  - Melhorar a comunicação com sua organização estendida

  - Reduzir sobrecarga informacional

  - Melhorar a conscientização da informação

  - Melhorar a dispersão de informações e conhecimentos importantes

Lync Server 2013, servidor de chat persistente não está disponível no Microsoft 365 ou no Office 365. No momento, ele está disponível somente para os clientes do Lync 2013 local.

No Lync 2013, a funcionalidade de chat persistente é integrada ao cliente Lync 2013. Como resultado, os usuários têm acesso a mensagens instantâneas/presença, áudio/vídeo, conferência e chat persistente, tudo no cliente do Lync 2013. Para obter mais informações sobre o cliente Lync 2013, consulte <https://go.microsoft.com/fwlink/p/?linkid=270877> .

Este tópico descreve as alterações de recursos entre a nova versão do Lync Server 2013, o servidor de chat persistente e a versão anterior (Microsoft Lync Server 2010, chat de grupo), incluindo:

  - Fornecer uma experiência administrativa no painel de controle do Lync Server e eliminar a ferramenta de administração de chat de grupo

  - Integre as definições de configuração para o servidor de chat persistente no construtor de topologias eliminando a ferramenta de configuração de chat de grupo

  - Facilitar a migração e a atualização de versões anteriores do servidor de chat persistente

  - Fornecer soluções de alta disponibilidade e recuperação de desastre

Para obter detalhes adicionais sobre a versão mais recente do servidor de chat persistente, confira o seguinte:

  - A ajuda de chat persistente em <https://go.microsoft.com/fwlink/p/?linkid=270945> que fornece uma lista detalhada de recursos de chat persistente, como eles funcionam e como usá-los ao executar o servidor de chat persistente.

  - O [planejamento para servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento [implantando servidor de chat persistente no Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) na documentação de implantação, [migração do Lync Server 2010, chat de grupo ou Office Communications Server 2007 R2 group chat to Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) na documentação de migração e [Gerenciando o Lync Server 2013, servidor](managing-lync-server-2013-persistent-chat-server.md) de chat persistente na documentação operações, todos fornecem instruções para configurar o servidor de chat persistente.

  - O arquivo de Documentation.msi do servidor de chat persistente (arquivo do Windows Installer) permite que os usuários acessem uma documentação offline abrangente sobre o servidor de chat persistente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Alterações de topologia de chave para o servidor de chat persistente

As seguintes alterações de alto nível para o servidor de chat persistente incluem:

O servidor de chat persistente agora é uma função de servidor. No Microsoft Lync Server 2010, o servidor de chat de grupo era um aplicativo confiável de terceiros para o Microsoft Lync Server 2010. O chat persistente pode ser adicionado à sua topologia do Lync Server 2013 usando o construtor de topologias. No Lync Server 2013, a funcionalidade do servidor de chat persistente é implementada usando três novas funções de servidor:

  - **PersistentChatService:** Esta é a função de front-end para chat persistente. Nas implantações Standard Edition, a função de serviço servidor de chat persistente é posicionada no servidor Standard Edition implantado pelo bootstrapper, como qualquer outra função do Lync Server. Nas implantações Enterprise Edition, a função de serviço de chat persistente é implantada em computadores autônomos pelo bootstrapper, como qualquer outra função do Lync Server.

  - **PersistentChatStore:** Servidor back-end que corresponde ao banco de dados de conteúdo de chat persistente, onde todo o conteúdo de chat é armazenado.

  - **PersistentChatComplianceStore:** Função de servidor back-end que corresponde ao banco de dados de conformidade de chat persistente, onde todos os eventos de conformidade são armazenados.

Essas funções de servidor de chat persistente são opcionais e são instaladas apenas por clientes que desejam uma funcionalidade abrangente de servidor de chat persistente. A função **PersistentChatComplianceStore** é necessária somente se você optar por implantar a conformidade de chat persistente.

A função **PersistentChatService** executa dois serviços:

  - Serviço de chat persistente

  - Serviço de conformidade de chat persistente

A execução desses serviços em cada servidor de chat persistente oferece alta disponibilidade para esses serviços em um pool de servidor de chat persistente de muitos servidores.

Além disso, para dar suporte ao upload e download de arquivos em salas de chat persistente, o servidor de chat persistente inclui um serviço Web. Anteriormente, esse serviço foi colocado no servidor de chat persistente, servidor front-end e IIS (serviços de informações da Internet) necessários para serem instalados como um pré-requisito. No servidor de chat persistente do Lync Server 2013, o serviço Web de upload/download de arquivos é colocado com o servidor front-end do Lync Server 2013. Como efeito colateral, o IIS (serviços de informações da Internet) não é mais um pré-requisito para o servidor de chat persistente. O serviço Web de upload/download de arquivos é identificado como **PersistentChat** no Gerenciador dos serviços de informações da Internet (IIS).

<div>


> [!IMPORTANT]  
> A função <STRONG>PersistentChatService</STRONG> pode ser executada no mesmo servidor que um &nbsp; servidor front-end do Lync Server 2013 somente se esse servidor front-end for um &nbsp; servidor front-end Standard Edition. A função <STRONG>PersistentChatService</STRONG> não pode ser executada independentemente de um &nbsp; servidor front-end do Lync Server 2013. Ele só pode ser instalado no contexto de uma implantação do Lync Server 2013.



</div>

No servidor de chat persistente, o serviço de pesquisa foi eliminado. No Lync Server 2010, chat de grupo, o serviço de pesquisa foi executado em cada servidor de front-end do servidor de chat de grupo e executou o roteamento para um dos servidores de canal. O Lync Server 2013 depende do roteamento usando objetos de contato, onde cada pool de servidor de chat persistente é representado por um objeto de contato que é usado pelos servidores front-end do Lync Server para identificar e rotear solicitações para um pool de servidor de chat persistente apropriado e para um dos computadores que executam o servidor de chat persistente no pool.

No Lync Server 2013, há modificações no serviço de conformidade:

  - No Lync Server 2010, o serviço de conformidade executou autônomo (não posicionado) e somente em um único servidor. O serviço de conformidade agora é executado em todos os servidores de front-end do servidor de chat persistente, junto com o serviço de chat persistente, e, portanto, oferece alta disponibilidade em um pool de servidor de chat persistente de muitos servidores. Um único adaptador de conformidade pode ser configurado para extrair dados do banco de dados de conformidade e para um dos outros sistemas (arquivo XML, arquivos hospedados no Exchange e assim por diante). O servidor de chat persistente inclui um adaptador XML.

  - A fila de enfileiramento de mensagens (também conhecida como MSMQ) que é compartilhada pelo serviço de chat persistente e o serviço de conformidade em cada servidor de front-end do servidor de chat persistente agora é uma fila privada compartilhada apenas pelos dois serviços. Todos os serviços de conformidade gravam no mesmo banco de dados de back-end de conformidade. Eles também são lidos a partir desse banco de dados, com o objetivo de enviar os dados para sua instância do adaptador. O servidor back-end de conformidade é representado como uma nova função de servidor back-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Como nas versões anteriores, todos os dados de conformidade são processados apenas uma vez. Os dados podem ser processados por qualquer instância do adaptador invocada pelo serviço de conformidade executado nos vários computadores do servidor de chat persistente do Lync Server 2013. No servidor de chat persistente, qualquer uma das instâncias de adaptador poderia processar os dados.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obter informações sobre como instalar o enfileiramento de mensagens, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">instalar sistemas operacionais e software de pré-requisito nos servidores do Lync Server 2013</A> na documentação de implantação.

    
    </div>

No Lync Server 2013, há melhorias na alta disponibilidade e recuperação de desastres:

  - Melhorias de alta disponibilidade: o espelhamento do SQL Server é usado para fornecer alta disponibilidade para o banco de dados de conteúdo do servidor de chat persistente e o banco de dados de conformidade de chat persistente em um Data Center (in-site).

  - Melhorias de recuperação de desastre: o servidor de chat persistente oferece suporte a uma arquitetura de pool estendido que permite que um único pool de servidor de chat persistente seja estendido entre dois sites (ou seja, um único pool lógico na topologia, com os servidores do pool fisicamente localizados em dois sites). O envio de logs do SQL Server é usado para recuperação de desastre entre sites.

Para obter mais informações sobre alta disponibilidade e recuperação de desastre, consulte [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) na documentação de implantação.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Chave de administração e gerenciamento de alterações para servidor de chat persistente

O Lync Server 2013 facilitou a administração e o gerenciamento do servidor de chat persistente fornecendo:

  - Administração e gerenciamento unificados. O Lync Server 2013 facilita o gerenciamento e a administração do servidor de chat persistente usando ferramentas que já são familiares aos administradores do Lync. Servidor de chat persistente inclui uma experiência de interface de usuário administrativa que é integrada ao painel de controle do Lync Server, que aborda problemas de desempenho com as versões anteriores da interface de usuário do servidor de chat de grupo. Além disso, o servidor de chat persistente inclui uma coleção de cmdlets do Windows PowerShell para administrar e gerenciar categorias de servidor de chat persistente, salas de servidor de chat persistente (incluindo a exclusão de salas e limpeza de conteúdo obsoleto) e suplementos.

  - Modelo de administração simplificado. O Lync Server 2013 alterou e simplificou o modelo de servidor de chat persistente atendendo aos seguintes requisitos principais do cliente:
    
      - Remova as hierarquias complexas aninhadas de escopos e categorias.
    
      - Suporte para definir listas de negações, bem como listas permitidas (escopos) para os clientes atuais do MindAlign que estão planejando migrar para o servidor de chat persistente.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>O que há de diferente nas funções de usuário das versões anteriores do servidor de chat de grupo?

Lync Server 2010, o chat de grupo tinha uma função de administrador de usuários, uma função de administrador de salas de chat e uma função de administrador do Lync Server que pudesse gerenciar suplementos. Servidor de chat persistente simplesmente fornece uma função de administrador de chat persistente (que é semelhante a outras funções RBAC (controle de acesso baseado em função) do Lync Server). Qualquer pessoa que seja membro dessa função RBAC pode gerenciar salas de chat, suplementos e categorias (e, portanto, obter acesso de usuário para essas categorias) e configuração do pool do servidor de chat persistente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>O que há de diferente nas categorias de sala de chat de versões anteriores do servidor de chat de grupo?

As categorias de sala de chat não podem mais ser aninhadas e a categoria raiz não pode mais ser modificada. Membros permitidos/DeniedMembers abrangem o que um escopo costumava ser em versões do servidor de chat de grupo herdado (exceto pelo fato de não suportar a especificação de uma lista negada). Escopos não podem mais ser substituídos, porque não há categorias aninhadas. Um administrador de chat persistente no Lync Server 2013 pode criar e gerenciar categorias de sala de chat. Como parte da criação e gerenciamento de categorias de sala de chat, um administrador de chat persistente pode configurar entidades (grupos/usuários/usuários do Active Directory) que têm acesso a membros/criadores de salas de chat de uma determinada categoria. Um administrador de chat persistente também pode adicionar DeniedMembers a uma categoria, e essas se tornam exclusões explícitas para a lista de permissões. DeniedMembers substitui o que está em AllowedMembers.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>O que há de diferente nas propriedades de sala de chat de versões anteriores do servidor de chat de grupo?

Há um novo conceito de salas de chat abertas no Lync Server 2013, servidor de chat persistente. Todos os membros permitidos podem participar da sala de chat, sem associação exclusiva.

As seguintes propriedades de sala de chat que foram incluídas nas versões anteriores do servidor de chat persistente foram eliminadas:

  - Tópico: uma sala agora tem apenas uma descrição.

  - Criar uma nova lista de membros: no servidor de chat persistente, todas as salas de bate-papo começam com associação vazia (e podem maximizar para uma associação que equivale aos membros permitidos).

  - Upload de arquivo: usado para ser uma configuração por sala de chat para controlar se o carregamento de arquivos/downloads foram permitidos. Agora, ele é definido somente o nível de categoria e se aplica a todas as salas nessa categoria.

  - Histórico de chat: usado para ser uma configuração por sala de chat para controlar se o histórico de chat foi habilitado, mas agora está definido apenas no nível de categoria e se aplica a todas as salas nessa categoria.

  - Convites: uma sala sempre herda a configuração de convites para a categoria; ou pode ser desativado na sala. Uma sala não poderá ativar convites se a categoria tiver sido previamente definida para convites.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>O que há de diferente em relação às políticas de versões anteriores do servidor de chat de grupo?

O servidor de chat persistente tem uma nova política do Lync habilitada com chat persistente, por usuário/pool/site/definições globais. No cliente do Lync 2013, o ambiente de chat persistente está disponível somente para usuários habilitados pela política para chat persistente (seja diretamente ou por meio da configuração pool/site/global).

Versões anteriores do servidor de chat de grupo não tinham nenhuma política integrada às políticas do Lync Server. Em uma base por usuário e por categoria/sala, usando o recurso **pode carregar arquivos** por usuário, você poderia tornar o usuário um administrador de usuário, um administrador de salas de chat ou configurar a capacidade do usuário de carregar arquivos. O recurso de **carregamento de arquivo** do servidor de chat persistente é apenas por categoria.

</div>

<div>

## <a name="logging"></a>Registro em log

O registro em log para o servidor de chat persistente e o System Center Operations Manager é integrado no log de rastreamento do Lync Server 2013.

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
