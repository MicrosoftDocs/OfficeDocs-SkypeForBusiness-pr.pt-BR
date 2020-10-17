---
title: 'Lync Server 2013: Configurando para notificações por push'
description: 'Lync Server 2013: Configurando para notificações por push.'
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
ms.openlocfilehash: 24c22ff42f666add9eac4966134c88b9bf680046
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548327"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="3d1fb-103">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d1fb-103">Configuring for push notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d1fb-104">_**Última modificação do tópico:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="3d1fb-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="3d1fb-105">Notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas a um dispositivo móvel mesmo quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-105">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="3d1fb-106">As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="3d1fb-107">O serviço de mobilidade do Lync Server 2013 envia as notificações para o serviço de notificação por push do Lync Server baseado na nuvem, que envia as notificações ao Apple Push Notification Service (APNS) (para um dispositivo Apple executando o Lync 2010 Mobile Client) ou o Microsoft Push Notification Service (MPNS) (para um dispositivo Windows Phone executando o Lync 2010 Mobile ou o cliente móvel Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="3d1fb-107">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d1fb-108">Se você usa o Windows Phone com o Lync 2010 Mobile ou o cliente móvel do Lync 2013, a notificação por push é uma consideração importante.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-108">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="3d1fb-109">Se você usar o Lync 2010 Mobile em dispositivos Apple, a notificação por push é uma consideração importante.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-109">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="3d1fb-110">Se você usar o Lync 2013 Mobile em dispositivos Apple, você não precisa mais de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-110">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="3d1fb-111">Configure sua topologia para suportar as notificações por push fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-111">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="3d1fb-112">Se seu ambiente tiver um servidor de borda do Lync Server 2010 ou do Lync Server 2013, você precisará adicionar um novo provedor de hospedagem, o Microsoft Lync Online e configurar a Federação do provedor de hospedagem entre sua organização e o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-112">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="3d1fb-113">Se seu ambiente tiver um servidor de borda do Office Communications Server 2007 R2, você precisará configurar a Federação SIP direta com o push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-113">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d1fb-114">Push.lync.com é um domínio do Microsoft Office 365 para o Serviço de Notificação de Push.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-114">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="3d1fb-115">Para habilitar as notificações por push, você precisa executar o cmdlet **Set-CsPushNotificationConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-115">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="3d1fb-116">Por padrão, as notificações por push estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-116">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="3d1fb-117">Teste a configuração de federação e as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-117">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="3d1fb-118">Para configurar as notificações por push com o Lync Server 2013 ou o servidor de borda do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3d1fb-118">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="3d1fb-119">Faça logon em um computador onde o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro do grupo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-119">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3d1fb-120">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3d1fb-121">Adicionar um provedor de hospedagem do Lync Server online.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-121">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="3d1fb-122">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-122">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="3d1fb-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-123">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d1fb-p104">Não é possível ter mais de um relacionamento de federação com um único provedor de hospedagem. Ou seja, se você já tiver configurado um provedor de hospedagem que tenha um relacionamento de federação com sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo se a identidade do provedor de hospedagem for algo além de LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-p104">You cannot have more than one federation relationship with a single hosting provider. That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="3d1fb-p105">Configure a federação do provedor de hospedagem entre sua organização e o Serviço de Notificação por Push no Lync Online. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-p105">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online. At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="3d1fb-128">Para configurar as notificações por push com o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3d1fb-128">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="3d1fb-129">Faça logon no servidor de borda como um membro do grupo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-129">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3d1fb-130">Clique em **Iniciar**, em **Todos os Programas**, em **Ferramentas Administrativas** e clique em **Gerenciamento do Computador**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-130">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="3d1fb-131">Na árvore do console, expanda **Serviços e Aplicativos**, clique com o botão direito do mouse em **Microsoft Office Communications Server 2007 R2** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-131">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="3d1fb-132">Na guia **Permitir**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-132">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="3d1fb-133">Na caixa de diálogo **Adicionar Parceiro Federado**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-133">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="3d1fb-134">Em **Nome de domínio do parceiro federado:**, digite **push.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-134">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="3d1fb-135">Em **Servidor de Borda de Acesso do parceiro Federado**, digite **sipfed.online.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-135">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="3d1fb-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-136">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="3d1fb-137">Para habilitar as notificações por push</span><span class="sxs-lookup"><span data-stu-id="3d1fb-137">To enable push notifications</span></span>

1.  <span data-ttu-id="3d1fb-138">Faça logon em um computador onde o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-138">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="3d1fb-139">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3d1fb-p106">Habilite as notificações por push. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-p106">Enable push notifications. At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="3d1fb-p107">Habilite a federação. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-p107">Enable federation. At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="3d1fb-144">Para testar a federação e as notificações por push</span><span class="sxs-lookup"><span data-stu-id="3d1fb-144">To test federation and push notifications</span></span>

1.  <span data-ttu-id="3d1fb-145">Faça logon em um computador onde o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-145">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="3d1fb-146">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3d1fb-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3d1fb-p108">Teste a configuração de federação. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-p108">Test the federation configuration. At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="3d1fb-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-149">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="3d1fb-p109">Teste as notificações por push. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-p109">Test push notifications. At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="3d1fb-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3d1fb-152">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d1fb-153">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3d1fb-153">See Also</span></span>


[<span data-ttu-id="3d1fb-154">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="3d1fb-154">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="3d1fb-155">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="3d1fb-155">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

