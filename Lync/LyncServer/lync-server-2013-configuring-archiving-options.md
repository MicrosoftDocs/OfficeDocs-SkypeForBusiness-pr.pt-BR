---
title: 'Lync Server 2013: Configurando opções de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 243414dea5b7ca411e4511c3a82f269c9981147e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configurando opções de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para especificar como o arquivamento é implementado. Isso inclui as seguintes configurações de Arquivamento:

  - Uma configuração global criada por padrão ao implantar o Lync Server 2013.

  - Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.

Inicialmente, as configurações de Arquivamento são definidas ao implantar o Arquivamento, mas você pode alterar, adicionar e excluir configurações depois da implantação. No painel de controle do Lync Server 2013, você pode usar a página **configuração de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar as configurações no nível global, nível de site e nível de pool. Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações. Para obter detalhes sobre como gerenciar as configurações após a implantação, consulte [Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) na documentação de operações.

<div>


> [!NOTE]  
> Para usar o arquivamento, você deve configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento de comunicações internas, para comunicações externas ou para usuários hospedados no Lync Server 2013. Por padrão, o arquivamento não está ativado para comunicações internas ou externas. Antes de ativar o Arquivamento em qualquer política, é necessário especificar os configurações de Arquivamento apropriadas para a implantação e, opcionalmente, para sites e pools específicos, como descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.<BR>Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, deverá configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento para comunicações internas, para comunicações externas ou para ambos. Por padrão, o arquivamento não está habilitado para comunicações internas ou externas para o arquivamento de dados ao usar os bancos de dados de arquivamento do Lync Server 2013. Antes de ativar o Arquivamento em qualquer política, você deve especificar as configurações de Arquivamento apropriadas para a implantação e, opcionalmente, para sites e pools específicos, como descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento para uso com os bancos de dados de arquivamento do Lync Server 2013, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando opções de arquivamento no nível global no Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configurando opções de arquivamento para um site no Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configurando opções de arquivamento para um pool no Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

