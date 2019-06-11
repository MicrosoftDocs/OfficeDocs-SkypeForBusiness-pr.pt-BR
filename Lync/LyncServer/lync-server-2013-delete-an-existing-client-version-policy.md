---
title: 'Lync Server 2013: excluir uma política de versão do cliente existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0adc3ab47b3b441eff900c6a9202a782e524c22c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Excluir uma política de versão de cliente existente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Se você quiser excluir uma política de versão do cliente que foi configurada anteriormente, você poderá excluí-la do painel de controle do Lync Server 2013 ou do Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>Para excluir políticas de versão do cliente usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão navegação na **política de versão do cliente** .

4.  Na página **política de versão do cliente** , selecione a política de versão do cliente ou políticas que você deseja excluir, clique em **Editar**e, em seguida, clique em **excluir**.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Excluindo políticas de versão do cliente usando cmdlets do Windows PowerShell

Você pode excluir políticas de versão do cliente usando o cmdlet **Remove-CsClientVersionPolicy** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>Para remover uma política de versão de cliente específica

  - Este comando exclui a política de versão do cliente aplicada ao site Redmond:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>Para remover todas as políticas de versão do cliente aplicadas ao escopo do site

  - Esse comando Remove todas as políticas de versão do cliente configuradas no escopo do site:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>Para remover as políticas de versão do cliente que não incluem um agente de usuário específico

  - E esse comando remove qualquer política de versão do cliente que não inclua uma regra para o agente de usuário do Windows Phone Lync (WPLync):
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

