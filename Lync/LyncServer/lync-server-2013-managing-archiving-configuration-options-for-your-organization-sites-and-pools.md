---
title: 'Lync Server 2013: Gerenciando opções de configuração de arquivamento para sua organização, sites e pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para especificar como o arquivamento é implementado. Isso inclui as seguintes configurações de arquivamento:

  - Uma configuração global criada por padrão quando você implanta o Lync Server 2013.

  - Configurações opcionais de nível de site e de pool que você pode criar e usar para especificar como o arquivamento é implementado para sites ou pools específicos.

Inicialmente, você define o arquivamento de configurações ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação. No painel de controle do Lync Server 2013, você pode usar a página de **configuração de arquivamento** do grupo **arquivamento e monitoramento** para gerenciar as configurações no nível global, no nível do site e no nível do pool. Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia de configurações de arquivamento, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.

<div>


> [!NOTE]  
> Para usar o arquivamento, configure as políticas de arquivamento para especificar se o arquivamento deve ser habilitado para comunicações internas, para comunicações externas ou para todos os usuários em um local no Lync Server 2013. Por padrão, o arquivamento não está habilitado para comunicações internas ou externas. Se você usa a integração do Microsoft Exchange, deve habilitar e configurar o Exchange 2013 para dar suporte ao arquivamento para todos os usuários hospedados no Exchange 2013 que tiveram suas caixas de correio colocadas no bloqueio in-loco.<BR>Antes de habilitar o arquivamento, você deve especificar as configurações de arquivamento adequadas para a sua implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar e atribuir políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.



</div>

**Para exibir as informações de configuração de arquivamento usando cmdlets do Windows PowerShell**

  - Você pode exibir informações de configuração de arquivamento usando o Windows PowerShell e o cmdlet **Get-CsArchivingConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.
    
    No Shell de gerenciamento do Lync Server, use o seguinte comando para exibir informações sobre todas as suas configurações de arquivamento:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criando uma configuração de arquivamento no Lync Server 2013 para gerenciar o arquivamento de sites ou pools específicos](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Habilitar ou desabilitar o arquivamento de sessões de mensagens instantâneas ou de conferência no Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Habilitar ou desabilitar a limpeza de dados arquivados no Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Habilitar ou desabilitar o modo crítico no Lync Server 2013 para bloquear ou permitir sessões de mensagens instantâneas e webconferência se o arquivamento falhar](lync-server-2013-enable-disable-critical-mode.md)

  - [Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados no Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitando ou desabilitando a integração do Lync Server 2013 com armazenamento do Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Excluindo uma configuração de arquivamento no Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando Arquivamento do Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

