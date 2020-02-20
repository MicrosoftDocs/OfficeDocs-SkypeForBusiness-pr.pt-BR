---
title: Usando categorias para administrar o servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2aa30e39594bfa0a294b4ad0d5755cdcb60c090
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Usando categorias para administrar o servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-01_

Sua implantação de servidor de chat persistente pode hospedar várias salas de chat persistentes simultâneas. As salas de chat podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria, e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base em suas finalidades de negócio e facilita a administração delegada e o gerenciamento simplificado.

<div>


> [!NOTE]  
> Embora muitos dos recursos de gerenciamento de salas de chat estejam disponíveis em computadores que executam o chat persistente (Lync Client) para o usuário, os administradores de chat persistente (na função <STRONG>cspersistentchatadministrator</STRONG> ) devem usar o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar ou gerenciar categorias.



</div>

Os administradores de chat persistente usam o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar e gerenciar categorias e para projetar o acesso de salas de chat para os usuários em sua organização.

Gerentes de sala de chat persistente, que têm a capacidade de gerenciar uma ou mais salas de chat, podem usar o cliente Lync para iniciar um aplicativo Web de gerenciamento de salas para criar e gerenciar salas (ou os clientes podem criar soluções e fluxos de trabalho personalizados para serem invocados). Os administradores de chat persistente também podem usar o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar e gerenciar salas.

<div>


> [!NOTE]  
> Uma sala de chat persistente não pode ter o mesmo nome de uma categoria de chat persistente.



</div>

Os gerentes de sala de chat podem fazer alterações em todas as propriedades de sala de chat, exceto alterar a categoria da sala. Não é possível impedi-los de executar as seguintes ações:

  - Desabilitar uma sala de chat

  - Alterar o nome de uma sala de chat

  - Alterar a descrição de uma sala de chat

  - Alterar um tipo de sala de chat (Auditório versus Normal)

  - Alterar a privacidade de uma sala (aberta versus fechada versus segredo)

  - Adicionar ou remover membros

  - Adicionar ou remover gerentes de sala de chat

  - Adicionar ou remover um suplemento

  - Alterar configurações como convites (de acordo com o que é permitido pela categoria)

<div>

## <a name="delegated-administration"></a>Administração delegada

Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias. Um administrador de chat persistente pode definir **Membros permitidos** e **criadores** para cada categoria e também pode definir as configurações e os comportamentos de sala de chat padrão que serão aplicados a todas as salas de chat criadas na categoria. Administradores de chat persistente criam e gerenciam categorias usando o painel de controle do Lync Server ou cmdlets do Windows PowerShell.

Usuários, Unidades Organizacionais (OUs) e grupos de usuário identificados como Creators da categoria são os únicos indivíduos e grupos que têm permissão para criar salas na categoria. Após a criação da categoria, eles podem escolher usuários, OUs e grupos de usuário na lista **AllowedMembers** da categoria como gerentes de sala de chat e membros para gerenciar e participar na sala.

As salas de chat criadas em uma categoria aderem às políticas e configurações aplicadas pela categoria (por exemplo, quem pode estar na associação da sala, quem pode gerenciar a sala, se os carregamentos de arquivo são permitidos, se os convites são enviados e assim por diante).

</div>

</div>

<span> </span>

</div>

</div>

</div>

