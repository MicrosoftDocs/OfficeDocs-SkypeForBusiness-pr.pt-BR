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
ms.openlocfilehash: e4bcf8ccda422468416ae4c0b486e2e224b17f9f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515468"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="a1e8a-102">Habilitar ou desabilitar notificações por push para Windows phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e8a-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1e8a-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a1e8a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a1e8a-104">As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um telefone Windows, mesmo quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="a1e8a-105">As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="a1e8a-106">Você pode habilitar ou desabilitar notificações por push para dispositivos do Windows Phone usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="a1e8a-107">Para habilitar as notificações por push para o Windows Phone usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a1e8a-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1e8a-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1e8a-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1e8a-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1e8a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1e8a-111">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="a1e8a-112">Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a1e8a-113">Clique na caixa de seleção **Habilitar as notificações por push da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="a1e8a-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="a1e8a-115">Para desativar as notificações por push para o Windows Phone usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a1e8a-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1e8a-116">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1e8a-117">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1e8a-118">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1e8a-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1e8a-119">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="a1e8a-120">Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a1e8a-121">Apague a caixa de seleção **Habilitar as notificações por push da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="a1e8a-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1e8a-123">Habilitar ou desabilitar notificações por push para o Windows Phone usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1e8a-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1e8a-124">Você pode habilitar ou desabilitar notificações por push para o Windows Phone usando o cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a1e8a-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="a1e8a-125">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1e8a-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1e8a-126">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a1e8a-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="a1e8a-127">Para habilitar as notificações por push para o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a1e8a-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="a1e8a-128">Para habilitar as notificações por push para o Windows Phone, defina o valor da propriedade EnableMicrosoftPushNotificationService como true ($True).</span><span class="sxs-lookup"><span data-stu-id="a1e8a-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="a1e8a-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a1e8a-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="a1e8a-130">Para desativar as notificações por push para o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a1e8a-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="a1e8a-131">Para desabilitar as notificações por push para o Windows Phone, defina o valor da propriedade EnableMicrosoftPushNotificationService como false ($False).</span><span class="sxs-lookup"><span data-stu-id="a1e8a-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="a1e8a-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a1e8a-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="a1e8a-133">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a1e8a-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1e8a-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1e8a-134">See Also</span></span>


[<span data-ttu-id="a1e8a-135">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e8a-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

