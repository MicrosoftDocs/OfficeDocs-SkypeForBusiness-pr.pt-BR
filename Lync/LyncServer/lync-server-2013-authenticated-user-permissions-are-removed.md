---
title: 'Lync Server 2013: as permissões de usuário autenticado são removidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf9f63fbe5340b3a241fc60b8623f54906dd8cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515758"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>As permissões de usuário autenticado são removidas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Em um ambiente bloqueado do Active Directory, as ACEs (entradas de controle de acesso) de usuário autenticado são removidas dos contêineres padrão do Active Directory, incluindo Usuários, Configuração ou Sistema, e de unidades organizacionais em que objetos de Usuário e Computador estão armazenados. A remoção das ACEs de usuário autenticado impede o acesso de leitura às informações do Active Directory. No entanto, a remoção dos Ases cria problemas para o Lync Server 2013 porque ele depende das permissões de leitura desses contêineres para permitir que os usuários executem a preparação do domínio.

Nessa situação, o membro do grupo Admins. do Domínio, que é necessário para executar a preparação do domínio, a ativação do servidor e a criação de pool, não concede acesso de leitura às informações do Active Directory armazenadas em contêiners padrão. Você deve conceder manualmente as permissões de acesso de leitura em vários contêineres no domínio raiz da floresta para verificar se o procedimento de pré-requisito de preparação da floresta foi concluído.

Para permitir que um usuário execute a preparação do domínio, a ativação do servidor e a criação do pool em qualquer domínio raiz que não seja da floresta, você tem as seguintes opções:

  - Use uma conta que seja membro do grupo Administradores de empresa para executar a preparação do domínio.

  - Usar uma conta que seja membro do grupo Admins. do Domínio e conceder a essa conta permissões de acesso de leitura em cada um dos seguintes contêineres no domínio raiz da floresta:
    
      - Domínio
    
      - Configuração ou Sistema

Se você não deseja usar uma conta que seja membro do grupo Administradores de Empresa para executar a preparação do domínio ou outras tarefas de instalação, conceda explicitamente acesso de leitura à conta que você deseja usar nos contêineres relevantes da raiz da floresta.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>Para concecer permissões de acesso de leitura a usuários em contêineres do domínio raiz da floresta

1.  Faça logon no computador associado ao domínio raiz da floresta com uma conta que seja membro do grupo Admins. do Domínio para o domínio raiz da floresta.

2.  Execute adsiedit.msc para o domínio raiz da floresta.
    
    Se as ACEs de usuário autenticado tiverem sido removidas do contêiner Domínio, Configuração ou Sistema, você deverá conceder permissões somente leitura no contêiner, conforme descrito nas etapas a seguir.

3.  Clique com o botão direito do mouse no contêiner e clique em **Propriedades**.

4.  Clique na guia **Segurança**.

5.  Clique em **Avançado**.

6.  Na guia **Permissões**, clique em **Adicionar**.

7.  Digite o nome do usuário ou grupo permissões de recebimento usando o seguinte formato: `domain\account name` e clique em **OK**.

8.  Na guia **Objetos**, em **Aplica-se a**, clique em **Somente Este Objeto**.

9.  Em **Permissões**, selecione as seguintes ACEs permitidas clicando na coluna **Permitir**: **Listar Conteúdo**, **Ler Todas as Propriedades** e **Permissões de Leitura**.

10. Clique em **OK** duas vezes.

11. Repita essas etapas para qualquer contêiner relevante listado na Etapa 2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

