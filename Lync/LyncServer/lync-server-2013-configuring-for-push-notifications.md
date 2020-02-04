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

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="48e57-102">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e57-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e57-103">_**Tópico da última modificação:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="48e57-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="48e57-104">As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um dispositivo móvel mesmo quando o aplicativo móvel estiver inativo.</span><span class="sxs-lookup"><span data-stu-id="48e57-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="48e57-105">As notificações por push notificam um usuário de eventos como um convite de mensagem instantânea novo ou perdido e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="48e57-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="48e57-106">O serviço de mobilidade do Lync Server 2013 envia as notificações para o serviço de notificação por push do Lync Server baseado na nuvem, que envia as notificações para o serviço de notificação por push da Apple (APNS) (para um dispositivo Apple executando o Lync 2010 Mobile cliente) ou o Serviço de notificação por push da Microsoft (MPNS) (para um dispositivo Windows Phone executando o Lync 2010 Mobile ou o Lync 2013 Mobile Client).</span><span class="sxs-lookup"><span data-stu-id="48e57-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="48e57-107">Se você usa o Windows Phone com o Lync 2010 Mobile ou o Lync 2013 Mobile Client, a notificação por push é uma consideração importante.</span><span class="sxs-lookup"><span data-stu-id="48e57-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="48e57-108">Se você usa o Lync 2010 Mobile em dispositivos Apple, a notificação por push é uma consideração importante.</span><span class="sxs-lookup"><span data-stu-id="48e57-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="48e57-109">Se você usa o Lync 2013 Mobile em dispositivos Apple, você não precisa mais de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="48e57-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="48e57-110">Configure sua topologia para dar suporte a notificações por push fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="48e57-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="48e57-111">Se o seu ambiente tiver um servidor do Lync Server 2010 ou Lync Server 2013 Edge Server, você precisará adicionar um novo provedor de hospedagem, o Microsoft Lync Online e, em seguida, configurar a Federação do provedor de hospedagem entre sua organização e o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="48e57-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="48e57-112">Se o seu ambiente tiver um servidor de borda do Office Communications Server 2007 R2, você precisará configurar a Federação SIP direta com o push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="48e57-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48e57-113">O Push.lync.com é um domínio do Microsoft Office 365 para o serviço de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="48e57-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="48e57-114">Para habilitar as notificações por push, você precisa executar o cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="48e57-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="48e57-115">Por padrão, as notificações por push estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="48e57-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="48e57-116">Teste a configuração de Federação e as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="48e57-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="48e57-117">Para configurar notificações por push com o Lync Server 2013 ou o Lync Server 2010 Edge Server</span><span class="sxs-lookup"><span data-stu-id="48e57-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="48e57-118">Faça logon em um computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro do grupo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="48e57-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="48e57-119">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="48e57-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="48e57-120">Adicionar um provedor de hospedagem online do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48e57-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="48e57-121">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="48e57-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="48e57-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="48e57-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48e57-123">Você não pode ter mais de uma relação de Federação com um único provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="48e57-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="48e57-124">Ou seja, se você já configurou um provedor de hospedagem que tem uma relação de Federação com o sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo que a identidade do provedor de hospedagem seja algo diferente de LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="48e57-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="48e57-125">Configurar a Federação do provedor de hospedagem entre sua organização e o serviço de notificação por push no Lync Online.</span><span class="sxs-lookup"><span data-stu-id="48e57-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="48e57-126">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="48e57-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="48e57-127">Para configurar notificações por push com o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="48e57-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="48e57-128">Faça logon no servidor de borda como membro do grupo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="48e57-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="48e57-129">Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **Gerenciamento do computador**.</span><span class="sxs-lookup"><span data-stu-id="48e57-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="48e57-130">Na árvore de console, expanda **serviços e aplicativos**, clique com o botão direito do mouse em **Microsoft Office communications Server 2007 R2**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="48e57-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="48e57-131">Na guia **permitir** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="48e57-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="48e57-132">Na caixa de diálogo **Adicionar parceiro federado** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="48e57-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="48e57-133">Em **nome do domínio do parceiro federado**, digite **Push.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="48e57-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="48e57-134">No **servidor de borda de acesso do parceiro federado**, digite **sipfed.online.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="48e57-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="48e57-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="48e57-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="48e57-136">Para ativar as notificações por push</span><span class="sxs-lookup"><span data-stu-id="48e57-136">To enable push notifications</span></span>

1.  <span data-ttu-id="48e57-137">Faça logon em um computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48e57-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="48e57-138">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="48e57-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="48e57-139">Habilite as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="48e57-139">Enable push notifications.</span></span> <span data-ttu-id="48e57-140">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="48e57-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="48e57-141">Habilite a Federação.</span><span class="sxs-lookup"><span data-stu-id="48e57-141">Enable federation.</span></span> <span data-ttu-id="48e57-142">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="48e57-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="48e57-143">Para testar as notificações por push e de Federação</span><span class="sxs-lookup"><span data-stu-id="48e57-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="48e57-144">Faça logon em um computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48e57-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="48e57-145">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="48e57-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="48e57-146">Testar a configuração de Federação.</span><span class="sxs-lookup"><span data-stu-id="48e57-146">Test the federation configuration.</span></span> <span data-ttu-id="48e57-147">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="48e57-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="48e57-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="48e57-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="48e57-149">Teste as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="48e57-149">Test push notifications.</span></span> <span data-ttu-id="48e57-150">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="48e57-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="48e57-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="48e57-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48e57-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="48e57-152">See Also</span></span>


[<span data-ttu-id="48e57-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="48e57-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="48e57-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="48e57-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

