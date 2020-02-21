---
title: 'Lync Server 2013: Configurando para notificações por push'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad1967bea18e0a03ac3a34bf187c1248ec5a1ab2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configurando notificações por push no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-12_

Notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas a um dispositivo móvel mesmo quando o aplicativo móvel está inativo. As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal. O serviço de mobilidade do Lync Server 2013 envia as notificações para o serviço de notificação por push do Lync Server baseado na nuvem, que envia as notificações ao Apple Push Notification Service (APNS) (para um dispositivo Apple executando o Lync 2010 Mobile Client) ou o Microsoft Push Notification Service (MPNS) (para um dispositivo Windows Phone executando o Lync 2010 Mobile ou o cliente móvel do Lync 2013).

<div>


> [!IMPORTANT]  
> Se você usa o Windows Phone com o Lync 2010 Mobile ou o cliente móvel do Lync 2013, a notificação por push é uma consideração importante.<BR>Se você usar o Lync 2010 Mobile em dispositivos Apple, a notificação por push é uma consideração importante.<BR>Se você usar o Lync 2013 Mobile em dispositivos Apple, você não precisa mais de notificação por push.



</div>

Configure sua topologia para suportar as notificações por push fazendo o seguinte:

  - Se seu ambiente tiver um servidor de borda do Lync Server 2010 ou do Lync Server 2013, você precisará adicionar um novo provedor de hospedagem, o Microsoft Lync Online e configurar a Federação do provedor de hospedagem entre sua organização e o Lync Online.

  - Se seu ambiente tiver um servidor de borda do Office Communications Server 2007 R2, você precisará configurar a Federação SIP direta com o push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com é um domínio do Microsoft Office 365 para o Serviço de Notificação de Push.

    
    </div>

  - Para habilitar as notificações por push, você precisa executar o cmdlet **Set-CsPushNotificationConfiguration**. Por padrão, as notificações por push estão desativadas.

  - Teste a configuração de federação e as notificações por push.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Para configurar as notificações por push com o Lync Server 2013 ou o servidor de borda do Lync Server 2010

1.  Faça logon em um computador onde o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro do grupo RtcUniversalServerAdmins.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Adicionar um provedor de hospedagem do Lync Server online. Na linha de comando, digite:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Por exemplo:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Não é possível ter mais de um relacionamento de federação com um único provedor de hospedagem. Ou seja, se você já tiver configurado um provedor de hospedagem que tenha um relacionamento de federação com sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo se a identidade do provedor de hospedagem for algo além de LyncOnline.

    
    </div>

4.  Configure a federação do provedor de hospedagem entre sua organização e o Serviço de Notificação por Push no Lync Online. Na linha de comando, digite:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Para configurar as notificações por push com o servidor de borda do Office Communications Server 2007 R2

1.  Faça logon no servidor de borda como um membro do grupo RtcUniversalServerAdmins.

2.  Clique em **Iniciar**, em **Todos os Programas**, em **Ferramentas Administrativas** e clique em **Gerenciamento do Computador**.

3.  Na árvore do console, expanda **Serviços e Aplicativos**, clique com o botão direito do mouse em **Microsoft Office Communications Server 2007 R2** e clique em **Propriedades**.

4.  Na guia **Permitir**, clique em **Adicionar**.

5.  Na caixa de diálogo **Adicionar Parceiro Federado**, execute o seguinte procedimento:
    
      - Em **Nome de domínio do parceiro federado:**, digite **push.lync.com**.
    
      - Em **Servidor de Borda de Acesso do parceiro Federado**, digite **sipfed.online.lync.com**.
    
      - Clique em **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Para habilitar as notificações por push

1.  Faça logon em um computador onde o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Habilite as notificações por push. Na linha de comando, digite:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Habilite a federação. Na linha de comando, digite:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Para testar a federação e as notificações por push

1.  Faça logon em um computador onde o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Teste a configuração de federação. Na linha de comando, digite:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Por exemplo:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Teste as notificações por push. Na linha de comando, digite:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Por exemplo:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Consulte também


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

