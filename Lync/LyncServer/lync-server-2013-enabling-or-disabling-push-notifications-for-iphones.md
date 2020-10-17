---
title: 'Lync Server 2013: habilitando ou desabilitando notificações por push para iPhones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942a9f12727a73125809113080a25ddd11a3f5d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515458"
---
# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="a8275-102">Habilitar ou desabilitar notificações por push para iPhones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8275-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8275-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a8275-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a8275-104">As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um iPhone, mesmo quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="a8275-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="a8275-105">As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="a8275-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="a8275-106">Você pode habilitar ou desabilitar notificações por push para iPhone usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8275-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="a8275-107">Para habilitar as notificações por push para iPhone usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8275-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a8275-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a8275-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a8275-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a8275-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8275-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8275-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a8275-111">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="a8275-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="a8275-112">Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a8275-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a8275-113">Clique na caixa de seleção **Habilitar as notificações por push da Apple**.</span><span class="sxs-lookup"><span data-stu-id="a8275-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="a8275-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a8275-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="a8275-115">Para desabilitar as notificações por push para iPhone usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8275-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a8275-116">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a8275-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a8275-117">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a8275-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8275-118">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8275-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a8275-119">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="a8275-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="a8275-120">Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a8275-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a8275-121">Apague a caixa de seleção **Habilitar as notificações por push da Apple**.</span><span class="sxs-lookup"><span data-stu-id="a8275-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="a8275-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a8275-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a8275-123">Habilitar ou desabilitar notificações por push para o iPhone usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8275-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a8275-124">As notificações por push para o iPhone da Apple podem ser habilitadas ou desabilitadas usando o cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a8275-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="a8275-125">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8275-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a8275-126">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a8275-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="a8275-127">Para habilitar as notificações por push para iPhone</span><span class="sxs-lookup"><span data-stu-id="a8275-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="a8275-128">Para habilitar as notificações por push para iPhone, defina o valor da propriedade EnableApplePushNotificationService como true ($True).</span><span class="sxs-lookup"><span data-stu-id="a8275-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="a8275-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8275-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="a8275-130">Para desabilitar as notificações por push para iPhone</span><span class="sxs-lookup"><span data-stu-id="a8275-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="a8275-131">Para desativar as notificações por push para iPhone, defina o valor da propriedade EnableApplePushNotificationService como false ($False).</span><span class="sxs-lookup"><span data-stu-id="a8275-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="a8275-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8275-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="a8275-133">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a8275-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8275-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="a8275-134">See Also</span></span>


[<span data-ttu-id="a8275-135">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8275-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

