---
title: Excluir um conjunto existente das configurações do Tronco SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Excluir uma coleção existente de definições de configuração de tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. Essas configurações realizam atividades como especificar:

  - Se o desvio de mídia deve ser ativado nos troncos.

  - As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.

  - Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.

Ao instalar o Microsoft Lync Server 2013, uma coleção global de configurações de tronco SIP é criada para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o painel de controle do Lync Server ou o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) para "redefinir" as propriedades na coleção global para os valores padrão. Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.

Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:

  - Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.

  - Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Para remover as configurações de tronco com o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **Roteamento de voz** e, em seguida, clique em **configuração de tronco**.

2.  Na guia **Configuração do Tronco**, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e, então, clique em **Excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.

3.  A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.

4.  Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.

5.  Na caixa de diálogo **painel de controle do Microsoft Lync Server 2013** , clique em **OK**.

6.  If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. Quando a caixa de diálogo **painel de controle do Microsoft Lync Server 2013** for exibida, clique em **OK**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de tronco usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Para remover uma coleção especificada das definições

  - O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Para remover todos os conjuntos aplicados ao escopo do site

  - Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Para remover todos os conjuntos em que o bypass de mídia está habilitado

  - O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

