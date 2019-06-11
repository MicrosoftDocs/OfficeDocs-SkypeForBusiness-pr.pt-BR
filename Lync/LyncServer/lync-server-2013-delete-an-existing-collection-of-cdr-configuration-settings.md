---
title: 'Lync Server 2013: excluir uma coleção existente de definições de configuração de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Excluir uma coleção existente de definições de configuração de CDR no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.

Quando você instala o Microsoft Lync Server 2013, uma única coleção global de definições de configuração de CDR é criada para você. Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais. Através do design, as definições configuradas no escopo do site têm precedência sobre aquelas no escopo global. Se você excluir as definições no escopo do site, então o CDR será gerenciado nesse site usando as definições globais.

Observe que também é possível "excluir" as definições globais. No entanto, as definições globais não serão realmente removidas. Em vez disso, todas as propriedades nessa coleção serão redefinidas para os valores padrão. Por exemplo, como padrão, a limpeza está ativada em uma coleção de definições de configuração de CDR. Suponha que você modifique a coleção global de forma que a limpeza seja desativada. Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão. Neste caso, isso significa que a limpeza será novamente ativada.

Você pode remover as configurações de configuração de CDR usando o painel de controle do Lync Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Para remover as configurações de configuração de CDR com o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.

2.  Na guia **Registro de Detalhes de Chamada**, selecione a coleção (ou coleções) de definições de CDR a ser removida. Para selecionar várias coleções, clique na primeira coleção, mantenha pressionada a tecla CTRL e clique em mais coleções.

3.  Clique em **Editar** e então em **Excluir**.

4.  Na caixa de diálogo painel de controle do Lync Server, clique em **OK**.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as definições de configuração de CDR usando cmdlets do Windows PowerShell

Você pode excluir as configurações de registro de detalhes da chamada usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Para remover uma coleção especificada das definições de configuração de CDR

  - Este comando remove as definições de configuração de CDR aplicadas ao site da Redmond:
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de CDR aplicadas ao escopo do site

  - Este comando remove todas as definições de configuração de CDR aplicadas ao escopo do site:
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para remover todas as definições de configuração de CDR que desativam a gravação de detalhes de chamada

  - Este comando remove todas as definições de configuração de CDR onde a gravação de detalhes de chamada foi desativada:
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

