---
title: Excluir uma coleção existente de definições de configuração de versão do cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3015358c27786b03b505e580acd599e26d4f3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Excluir uma coleção existente de definições de configuração de versão do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Se quiser remover as configurações de configuração do cliente que foram configuradas anteriormente para um site, você pode remover as configurações do painel de controle do Lync Server 2013 ou do Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>Para remover as definições de configuração do cliente usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de versão do cliente** .

4.  Selecione o site, clique em **Editar**, clique em **excluir**e, em seguida, clique em **OK**.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de versão do cliente usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de versão do cliente usando o cmdlet **Remove-CsClientVersionConfiguration** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>Para remover uma coleção especificada de definições de configuração de versão do cliente

  - O comando a seguir remove as definições de configuração de versão do cliente aplicadas ao site Redmond:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de versão do cliente aplicadas ao escopo do site

  - Esse comando Remove todas as definições de configuração de versão do cliente definidas no escopo do site:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>Para remover todas as definições de configuração de versão do cliente com base no valor da propriedade DefaultAction

  - E esse comando Remove todas as configurações de versão do cliente em que a ação padrão foi definida como "bloquear":
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

