---
title: 'Lync Server 2013: Configurando opções de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configurando opções de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-10_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para especificar como o arquivamento é implementado. Isso inclui as seguintes configurações de arquivamento:

  - Uma configuração global criada por padrão quando você implanta o Lync Server 2013.

  - Configurações opcionais de nível de site e de pool que você pode criar e usar para especificar como o arquivamento é implementado para sites ou pools específicos.

Inicialmente, você define o arquivamento de configurações ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação. No painel de controle do Lync Server 2013, você pode usar a página de **configuração** de arquivamento do grupo **arquivamento e monitoramento** para gerenciar as configurações no nível global, no nível do site e no nível do pool. Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia de configurações de arquivamento, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, implantação documentação ou documentação de operações. Para obter detalhes sobre como gerenciar as configurações após a implantação, consulte [Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) na documentação de operações.

<div>


> [!NOTE]  
> Para usar o arquivamento, configure as políticas de arquivamento para especificar se o arquivamento de comunicações internas deve ser habilitado, para comunicações externas ou para os usuários hospedados no Lync Server 2013. Por padrão, o arquivamento não está habilitado para comunicações internas ou externas. Antes de habilitar o arquivamento em qualquer política, você deve especificar as configurações de arquivamento adequadas para a implantação e, opcionalmente, sites e pools específicos, conforme descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar e atribuir políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.<BR>Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, configure as políticas de arquivamento para especificar se o arquivamento deve ser habilitado para comunicações internas, para comunicações externas ou para ambos. Por padrão, o arquivamento não está habilitado para comunicações internas ou externas para o arquivamento de dados ao usar bancos de dados de arquivamento do Lync Server 2013. Antes de habilitar o arquivamento em qualquer política, você deve especificar as configurações de arquivamento adequadas para sua implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento para uso com bancos de dados de arquivamento do Lync Server 2013, Confira como <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar e atribuir políticas de arquivamento no Lync server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configuração de opções de arquivamento no nível global do Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configurando opções de arquivamento para um site no Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configurando opções de arquivamento para um pool no Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

