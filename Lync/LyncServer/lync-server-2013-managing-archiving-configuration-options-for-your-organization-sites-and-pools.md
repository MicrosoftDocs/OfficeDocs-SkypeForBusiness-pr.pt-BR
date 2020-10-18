---
title: 'Lync Server 2013: Gerenciando opções de configuração de arquivamento para sua organização, sites e pools'
description: 'Lync Server 2013: Gerenciando opções de configuração de arquivamento para sua organização, sites e pools.'
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
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576617"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para especificar como o arquivamento é implementado. Isso inclui as seguintes configurações de Arquivamento:

  - Uma configuração global criada por padrão ao implantar o Lync Server 2013.

  - Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.

Inicialmente, as configurações de Arquivamento são definidas ao implantar o Arquivamento, mas você pode alterar, adicionar e excluir configurações depois da implantação. No painel de controle do Lync Server 2013, você pode usar a página **configuração de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar as configurações no nível global, nível de site e nível de pool. Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]  
> Para usar o arquivamento, você deve configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento de comunicações internas, para comunicações externas ou para todos os usuários hospedados no Lync Server 2013. Por padrão, o arquivamento não está ativado para comunicações internas ou externas. Se você usar a integração com o Microsoft Exchange, deverá habilitar e configurar o Exchange 2013 para oferecer suporte ao arquivamento para todos os usuários hospedados no Exchange 2013 que tiveram suas caixas de correio colocadas em In-Place.<BR>Antes de habilitar o arquivamento, é preciso especificar as configurações de arquivamento apropriadas para sua implantação e, como opção, para sites e pool específicos, como descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.



</div>

**Para exibir informações de configuração de arquivamento usando cmdlets do Windows PowerShell**

  - Você pode exibir as informações de configuração de arquivamento usando o Windows PowerShell e o cmdlet **Get-CsArchivingConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    No Shell de gerenciamento do Lync Server, use o seguinte comando para exibir informações sobre todas as suas definições de configuração de arquivamento:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar uma configuração de arquivamento no Lync Server 2013 para gerenciar o arquivamento de sites ou pools específicos](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Habilitar ou desabilitar o arquivamento de sessões de IM ou de conferência no Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Habilitando ou desabilitando a limpeza de dados arquivados no Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Habilitar ou desabilitar o modo crítico no Lync Server 2013 para bloquear ou permitir mensagens instantâneas e sessões de conferência da Web se o arquivamento falhar](lync-server-2013-enable-disable-critical-mode.md)

  - [Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar ou desabilitar a integração do Lync Server 2013 com o armazenamento do Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Excluindo uma configuração de arquivamento no Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando o arquivamento do Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

