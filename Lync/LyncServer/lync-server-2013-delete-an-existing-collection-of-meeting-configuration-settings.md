---
title: Excluir um conjunto existente de definições de configuração de reunião
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971bde33feee35d91c0cbefe0fea931533818862
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Excluir um conjunto existente de definições de configuração de reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode excluir uma configuração de site ou de usuário. A configuração global não pode ser removida. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>Para excluir uma configuração de site ou de reunião

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.

4.  Na lista de configurações de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar**e em **excluir**.

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de reunião usando os cmdlets do Windows PowerShell

As configurações de reunião podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsMeetingConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>Para remover um conjunto especificado de definições de configuração de reunião

  - Este comando remove as definições de configuração de reunião aplicadas ao site da Redmond:
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de reunião aplicadas ao escopo do site

  - Este comando remove todas as definições de configuração de reunião aplicadas ao escopo do site:
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>Para remover todas as definições de configuração de reunião que admitem usuários anônimos por padrão

  - E este remove todas as configurações que permitem que usuários anônimos sejam admitidos como padrão:
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

