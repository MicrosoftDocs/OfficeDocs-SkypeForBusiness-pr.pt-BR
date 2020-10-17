---
title: Gerenciando o arquivamento de comunicações internas e externas
description: Gerenciar o arquivamento de comunicações internas e externas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564127"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

No Lync Server 2013, você usa políticas de arquivamento para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas se você não usa a integração com o Microsoft Exchange ou se você tem usuários que não estão hospedados no Exchange 2013 com suas caixas de correio colocadas em In-Place isenção. Isso inclui as seguintes políticas de arquivamento:

  - Uma política global criada por padrão ao implantar o Lync Server 2013.

  - Políticas em nível de site e do usuário opcionais que você pode criar e utilizar para especificar como o arquivamento será implementado para sites e usuários específicos.

Inicialmente, você configurou as políticas de arquivamento quando implantou o arquivamento, mas é possível alterar, adicionar e excluir política depois da implantação. No painel de controle do Lync Server 2013, você pode usar a página **política de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar políticas no nível global, nível do site e nível do usuário. Se você integrar o armazenamento do Lync Server ao armazenamento do Exchange 2013, as políticas de usuário do Exchange terão precedência sobre as políticas de arquivamento do Lync Server 2013.

Para obter detalhes sobre como as políticas são implementadas, incluindo a hierarquia das políticas, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]
> Para controlar a implementação do arquivamento, você deve especificar opções nas configurações de arquivamento, como se deve arquivar mensagens instantâneas ou conferências, o uso do modo crítico e as opções de limpeza. Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento no site ou no pool. Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento para as comunicações internas ou externas nas políticas de arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools</A> na documentação de operações.<BR>Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em In-Place isenção. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Alterar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sua organização, sites ou usuários](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Aplicando uma política de arquivamento aos usuários no Lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Excluindo uma política de arquivamento no Lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

