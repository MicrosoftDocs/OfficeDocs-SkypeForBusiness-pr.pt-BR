---
title: 'Lync Server 2013: habilitando ou desabilitando notificações por push para telefones Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Habilitar ou desabilitar notificações por push para telefones Windows no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um telefone Windows, mesmo quando o aplicativo móvel está inativo. As notificações por push notificam um usuário de eventos como um convite de mensagem instantânea novo ou perdido e caixa postal. Você pode habilitar ou desabilitar as notificações por push para dispositivos Windows Phone usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Para ativar as notificações por push para Windows Phone usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração por push de notificação** .

4.  Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.

5.  Clique na caixa de seleção **habilitar notificações por push da Microsoft** .

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Para desativar as notificações por push para Windows Phone usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração por push de notificação** .

4.  Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.

5.  Desmarque a caixa de seleção **habilitar notificações por push da Microsoft** .

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar notificações por push para Windows Phone usando cmdlets do Windows PowerShell

Você pode habilitar ou desabilitar as notificações por push para Windows Phone usando o cmdlet **set-CsPushNotificationConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Para ativar as notificações por push para Windows Phone

  - Para habilitar as notificações por push para Windows Phone, defina o valor da propriedade EnableMicrosoftPushNotificationService como true ($True). Por exemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Para desativar as notificações por push para Windows Phone

  - Para desativar as notificações por push para Windows Phone, defina o valor da propriedade EnableMicrosoftPushNotificationService como false ($False). Por exemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .

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

