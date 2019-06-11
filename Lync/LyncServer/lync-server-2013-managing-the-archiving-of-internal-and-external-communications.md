---
title: Gerenciando o arquivamento de comunicações internas e externas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Gerenciar o arquivamento de comunicações internas e externas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

No Lync Server 2013, você usa políticas de arquivamento para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas se você não usar a integração com o Microsoft Exchange ou se tiver usuários que não são hospedados no Exchange 2013 com suas caixas de correio colocadas em Bloqueio in-loco. Isso inclui as seguintes políticas de arquivamento:

  - Uma política global criada por padrão quando você implanta o Lync Server 2013.

  - Políticas opcionais no nível do site e no nível do usuário que você pode criar e usar para especificar como o arquivamento é implementado para sites ou usuários específicos.

Inicialmente, você define as políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir políticas após a implantação. No painel de controle do Lync Server 2013, você pode usar a página **política** de arquivamento do grupo **arquivamento e monitoramento** para gerenciar políticas em nível global, nível de site e nível de usuário. Se você integrar o armazenamento do Lync Server ao armazenamento do Exchange 2013, as políticas de usuário do Exchange terão precedência sobre as políticas de arquivamento do Lync Server 2013.

Para obter detalhes sobre como as políticas são implementadas, incluindo a hierarquia de políticas, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.

<div>


> [!NOTE]
> Para controlar a implementação do arquivamento, você deve especificar opções em configurações de arquivamento, como se deseja arquivar mensagens instantâneas ou conferências, o uso do modo crítico e as opções de limpeza. Por padrão, nenhuma opção é habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de site ou de pool. Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento para comunicações internas ou externas nas políticas de arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</A> na documentação de operações.<BR>Se você habilitar a integração do Microsoft Exchange para a implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio no bloqueio in-loco. Para obter detalhes, consulte Configurando <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [Alterar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sua organização, sites ou usuários](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [Aplicação de uma política de arquivamento a usuários no Lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Excluindo uma política de arquivamento no Lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

