---
title: 'Lync Server 2013: Configurando notificações por push'
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
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configurando notificações por push no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-12_

As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um dispositivo móvel mesmo quando o aplicativo móvel estiver inativo. As notificações por push notificam um usuário de eventos como um convite de mensagem instantânea novo ou perdido e caixa postal. O serviço de mobilidade do Lync Server 2013 envia as notificações para o serviço de notificação por push do Lync Server baseado na nuvem, que envia as notificações para o serviço de notificação por push da Apple (APNS) (para um dispositivo Apple executando o Lync 2010 Mobile cliente) ou o Serviço de notificação por push da Microsoft (MPNS) (para um dispositivo Windows Phone executando o Lync 2010 Mobile ou o Lync 2013 Mobile Client).

<div>


> [!IMPORTANT]  
> Se você usa o Windows Phone com o Lync 2010 Mobile ou o Lync 2013 Mobile Client, a notificação por push é uma consideração importante.<BR>Se você usa o Lync 2010 Mobile em dispositivos Apple, a notificação por push é uma consideração importante.<BR>Se você usa o Lync 2013 Mobile em dispositivos Apple, você não precisa mais de notificação por push.



</div>

Configure sua topologia para dar suporte a notificações por push fazendo o seguinte:

  - Se o seu ambiente tiver um servidor do Lync Server 2010 ou Lync Server 2013 Edge Server, você precisará adicionar um novo provedor de hospedagem, o Microsoft Lync Online e, em seguida, configurar a Federação do provedor de hospedagem entre sua organização e o Lync Online.

  - Se o seu ambiente tiver um servidor de borda do Office Communications Server 2007 R2, você precisará configurar a Federação SIP direta com o push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > O Push.lync.com é um domínio do Microsoft Office 365 para o serviço de notificação por push.

    
    </div>

  - Para habilitar as notificações por push, você precisa executar o cmdlet **set-CsPushNotificationConfiguration** . Por padrão, as notificações por push estão desativadas.

  - Teste a configuração de Federação e as notificações por push.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Para configurar notificações por push com o Lync Server 2013 ou o Lync Server 2010 Edge Server

1.  Faça logon em um computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro do grupo RtcUniversalServerAdmins.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Adicionar um provedor de hospedagem online do Lync Server. Na linha de comando, digite:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Por exemplo:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Você não pode ter mais de uma relação de Federação com um único provedor de hospedagem. Ou seja, se você já configurou um provedor de hospedagem que tem uma relação de Federação com o sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo que a identidade do provedor de hospedagem seja algo diferente de LyncOnline.

    
    </div>

4.  Configurar a Federação do provedor de hospedagem entre sua organização e o serviço de notificação por push no Lync Online. Na linha de comando, digite:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Para configurar notificações por push com o servidor de borda do Office Communications Server 2007 R2

1.  Faça logon no servidor de borda como membro do grupo RtcUniversalServerAdmins.

2.  Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **Gerenciamento do computador**.

3.  Na árvore de console, expanda **serviços e aplicativos**, clique com o botão direito do mouse em **Microsoft Office communications Server 2007 R2**e, em seguida, clique em **Propriedades**.

4.  Na guia **permitir** , clique em **Adicionar**.

5.  Na caixa de diálogo **Adicionar parceiro federado** , faça o seguinte:
    
      - Em **nome do domínio do parceiro federado**, digite **Push.Lync.com**.
    
      - No **servidor de borda de acesso do parceiro federado**, digite **sipfed.online.Lync.com**.
    
      - Clique em **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Para ativar as notificações por push

1.  Faça logon em um computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Habilite as notificações por push. Na linha de comando, digite:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Habilite a Federação. Na linha de comando, digite:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Para testar as notificações por push e de Federação

1.  Faça logon em um computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Testar a configuração de Federação. Na linha de comando, digite:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Por exemplo:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Teste as notificações por push. Na linha de comando, digite:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Por exemplo:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

