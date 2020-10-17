---
title: 'Lync Server 2013: excluir um conjunto existente de definições de configuração de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebf7ce01e435a0a47d3468509485e96fa669192a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514638"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Excluir um conjunto existente de definições de configuração de CDR no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.

Quando você instala o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de CDR é criado para você. Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais. Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global. Se você excluir as configurações no escopo do site, o CDR será gerenciado nesse site usando as configurações globais.

Observe que você também pode “excluir” as definições globais. Contudo, elas não serão realmente removidas. Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão. Por exemplo, por padrão, a limpeza é habilitada em um conjunto de definições de configuração de CDR. Digamos que você modifique o conjunto global para que a exclusão seja desabilitada. Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão. Nesse caso, isso significa que a exclusão será habilitada novamente.

Você pode remover as definições de configuração de CDR usando o painel de controle do Lync Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Para remover as definições de configuração de CDR com o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.

2.  Na guia **registro de detalhes das chamadas** , selecione a coleção (ou coleções) das configurações de CDR a serem removidas. Para selecionar várias coleções, clique na primeira coleção, pressione a tecla CTRL e clique em coleções adicionais.

3.  Clique em **Editar**e em **excluir**.

4.  Na caixa de diálogo painel de controle do Lync Server, clique em **OK**.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de CDR usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de registro de detalhes da chamada usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Para remover um conjunto especificado de definições de configuração de CDR

  - Este comando remove as definições de configuração de CDR aplicadas ao site de Redmond:
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de CDR aplicadas ao escopo do site

  - Este comando Remove todas as definições de configuração de CDR aplicadas ao escopo do site:
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para remover todas as definições de configuração de CDR que desativam a gravação de detalhes da chamada

  - Este comando Remove todas as definições de configuração de CDR onde a gravação de detalhes da chamada foi desativada:
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

