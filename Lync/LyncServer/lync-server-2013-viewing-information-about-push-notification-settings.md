---
title: 'Lync Server 2013: exibindo informações sobre configurações de notificação de push'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74bbc90b0b7ef27da6b38b626fc91bc04383685
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Exibindo informações sobre configurações de notificação por push no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas a um dispositivo móvel mesmo quando o aplicativo móvel está inativo. As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal. Você pode exibir as configurações de notificações por push de informações para dispositivos móveis usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Para exibir informações de notificação por push no painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.

4.  Na página **configuração de notificação por push** , clique no site que você deseja exibir, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de notificação por push usando cmdlets do Windows PowerShell

Você pode exibir as definições de configuração de notificação por push usando o Windows PowerShell e o cmdlet **Get-CsPushNotificationConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-push-notification-configuration-information"></a>Para exibir informações de configuração de notificação de push

  - Para exibir informações sobre todas as suas definições de configuração de notificação por push, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsPushNotificationConfiguration
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando notificações por push no Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

