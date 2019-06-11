---
title: Excluir uma coleção existente de definições de configuração de reunião
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d564cf8fbcfb8c66df5e84841aae456913f1dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Excluir uma coleção existente de definições de configuração de reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Você pode excluir uma configuração de site ou de usuário. A configuração global não pode ser removida. Se você excluir a configuração global, ela automaticamente retorna para os valores padrão.

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>Para excluir uma configuração de reunião de site ou de usuário

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.

4.  Na lista de configuração de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de reunião usando cmdlets do Windows PowerShell

As configurações de reunião podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsMeetingConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>Para remover uma coleção especificada de definições de configuração de reunião

  - Este comando remove as definições de configuração de reunião aplicadas ao site Redmond:
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de reunião aplicadas ao escopo do site

  - Esse comando Remove todas as definições de configuração de reunião aplicadas ao escopo do site:
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>Para remover todas as configurações de reunião que admitem usuários anônimos por padrão

  - E isso remove todas as configurações que permitem que os usuários anônimos sejam admitidos por padrão:
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

