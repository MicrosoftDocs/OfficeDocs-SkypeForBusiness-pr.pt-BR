---
title: Excluir um conjunto existente de definições de configuração do tronco SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bd2dd62116f0d48a2a3169c91d8d04486c86418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514668"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Excluir um conjunto existente de definições de configuração do tronco SIP no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

  - Se o bypass de mídia deve ser habilitado nos troncos.

  - As condições nas quais os pacotes RTCP são enviados.

  - Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o painel de controle do Lync Server ou o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) para "redefinir" as propriedades na coleção global para seus valores padrão. Por exemplo, se você tiver definido a propriedade Enable3pccRefer como true, ao redefinir a coleção global, a propriedade Enable3pccRefer será revertida para o valor padrão false.

Os administradores também podem criar definições de configuração de tronco personalizadas no escopo do site ou no escopo do serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas. Ao remover essas configurações personalizadas, lembre-se do seguinte:

  - Se você remover as configurações de escopo de serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao seu site, caso existam. Se as configurações do site não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.

  - Se você remover as configurações no escopo do site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pelo conjunto global de definições de configuração de tronco.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Para remover as definições de configuração de tronco com o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **Roteamento de voz** e em **configuração de tronco**.

2.  Na guia **configuração de tronco** , selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e em **excluir**. Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída e, em seguida, pressione a tecla CTRL e clique em qualquer coleção adicional que você deseja remover.

3.  A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.

4.  Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.

5.  Na caixa de diálogo **Painel de Controle do Microsoft Lync Server 2013**, clique em **OK**.

6.  Se você mudar de ideia e optar por não excluir a coleção, clique em **confirmar** e em **cancelar todas as alterações não confirmadas**. Quando a caixa de diálogo **painel de controle do Microsoft Lync Server 2013** for exibida, clique em **OK**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de tronco usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Para remover uma coleção especificada de configurações

  - O comando a seguir remove as definições de configuração do tronco aplicadas ao site Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Para remover todas as coleções aplicadas ao escopo do site

  - Este comando Remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Para remover todas as coleções nas quais o bypass de mídia está habilitado

  - O comando a seguir remove todas as definições de configuração de tronco em que o bypass de mídia foi habilitado:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

