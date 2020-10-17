---
title: 'Lync Server 2013: Configurando e atribuindo políticas de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af6a253de4d35b3505b5ffa8be42fae297221641
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517568"
---
# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Configurando e atribuindo políticas de arquivamento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

No Lync Server 2013, você usa políticas para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas para usuários hospedados no Lync Server 2013. Isso inclui as seguintes políticas de arquivamento:

  - Uma política global criada por padrão ao implantar o Lync Server 2013.

  - Políticas em nível de site e do usuário opcionais que você pode criar e utilizar para especificar como o arquivamento será implementado para sites e usuários específicos.

Inicialmente, você configurou as políticas de arquivamento quando implantou o arquivamento, mas é possível alterar, adicionar e excluir política depois da implantação. No painel de controle do Lync Server 2013, você pode usar a página **política de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar políticas no nível global, nível do site e nível do usuário.

<div>


> [!NOTE]  
> Para controlar a implementação do arquivamento, você deve especificar opções nas configurações de arquivamento, como se deve arquivar mensagens instantâneas ou conferências, o uso do modo crítico e as opções de limpeza. Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento no site ou no pool. Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento para as comunicações internas ou externas nas políticas de arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools</A> na documentação de operações.<BR>Se você integrar o armazenamento do Lync Server com o armazenamento do Exchange 2013, as políticas de usuário do Exchange terão precedência sobre as políticas de arquivamento do Lync Server 2013, mas apenas para os usuários hospedados no Exchange 2013 que tiveram suas caixas de correio colocadas em In-Place.



</div>

Para obter detalhes sobre como as políticas são implementadas, incluindo a hierarquia das políticas, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações. Para obter detalhes sobre como gerenciar políticas após a implantação, consulte [Managing the Archiving of Internal and external Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) na documentação operações.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando a política global para arquivamento no Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configurando políticas de site para arquivamento no Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configurando políticas de arquivamento para usuários no Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

