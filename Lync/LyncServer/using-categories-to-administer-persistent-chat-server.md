---
title: Usando categorias para administrar o Servidor de Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fed28ecc7c2698f4b320729c68de9c5d56b435b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Usando categorias para administrar o Servidor de Chat Persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-01_

Sua implantação do servidor de chat persistente pode hospedar muitas salas de chat persistentes persistentes. Essas salas podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base no objetivo comercial, bem como facilita a administração delegada e o gerenciamento simplificado.

<div>


> [!NOTE]  
> Embora muitos dos recursos de gerenciamento de salas de chat estejam disponíveis em computadores que executam o chat persistente (cliente do Lync) para o usuário, administradores de chat persistente (na função <STRONG>cspersistentchatadministrator</STRONG> ) devem usar o painel de controle do Lync Server ou Cmdlets do Windows PowerShell para criar ou gerenciar categorias.



</div>

Administradores de chat persistentes usam o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar e gerenciar categorias e para criar acesso a salas de chat para os usuários de sua organização.

Os gerentes de sala de chat persistentes, que têm a capacidade de gerenciar uma ou mais salas de chat, podem usar o cliente do Lync para iniciar um aplicativo Web de gerenciamento de salas para criar e gerenciar salas (ou clientes podem criar soluções e fluxos de trabalho personalizados para serem invocados). Os administradores de chat persistente também podem usar o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar e gerenciar salas.

<div>


> [!NOTE]  
> Uma sala de chat persistente não pode ter o mesmo nome de uma categoria de chat persistente.



</div>

Os gerentes de salas de chat podem fazer alterações em todas as propriedades dessas salas, exceto alterar a sua categoria. Eles devem ter permissão para executar as seguintes ações:

  - Desabilitar uma sala de chat

  - Alterar o nome de uma sala de chat

  - Alterar a descrição de uma sala de chat

  - Alterar um tipo de sala de chat (Auditório versus Normal)

  - Alterar a privacidade de uma sala (aberta verso fechada verso secreta)

  - Adicionar ou remover membros

  - Adicionar ou remover gerentes de salas de chat

  - Adicionar ou remover um suplemento

  - Alterar configurações, como convites (de acordo com o que é permitido pela categoria)

<div>

## <a name="delegated-administration"></a>Administração delegada

Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias. Um administrador de chat persistente pode definir **AllowedMembers** e **criadores** para cada categoria e também pode definir as configurações e os comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria. Administradores de chat persistentes criam e gerenciam categorias usando o painel de controle do Lync Server ou cmdlets do Windows PowerShell.

Usuários, Unidades Organizacionais (OUs) e grupos de usuários identificados como Criadores da categoria são os únicos indivíduos e grupos que porem criar salas na categoria. Após a categoria ser criada, eles podem escolher usuários, OUs e grupos de usuários da lista  **AllowedMembers** da categoria como gerentes da sala de chat e membros para gerenciar e participar da sala.

As salas de chat criadas em uma categoria aderem às políticas e configurações impostas pela categoria (por exemplo, quem pode estar na associação da sala, quem pode gerenciar a sala, se os carregamentos de arquivo são permitidos, se os convites são enviados e assim por diante).

</div>

</div>

<span> </span>

</div>

</div>

</div>

