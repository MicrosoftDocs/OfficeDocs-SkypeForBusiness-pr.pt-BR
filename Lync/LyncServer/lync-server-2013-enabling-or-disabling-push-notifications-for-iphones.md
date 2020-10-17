---
title: 'Lync Server 2013: habilitando ou desabilitando notificações por push para iPhones'
description: 'Lync Server 2013: habilitando ou desabilitando notificações por push para iPhones.'
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
ms.openlocfilehash: 07a9c5ec442c3628455797b987d8b2f22677e70e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546497"
---
# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="5898c-103">Habilitar ou desabilitar notificações por push para iPhones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5898c-103">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5898c-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5898c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5898c-105">As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um iPhone, mesmo quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="5898c-105">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="5898c-106">As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="5898c-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="5898c-107">Você pode habilitar ou desabilitar notificações por push para iPhone usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5898c-107">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="5898c-108">Para habilitar as notificações por push para iPhone usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5898c-108">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5898c-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5898c-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5898c-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5898c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5898c-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5898c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5898c-112">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="5898c-112">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="5898c-113">Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5898c-113">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5898c-114">Clique na caixa de seleção **Habilitar as notificações por push da Apple**.</span><span class="sxs-lookup"><span data-stu-id="5898c-114">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="5898c-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5898c-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="5898c-116">Para desabilitar as notificações por push para iPhone usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5898c-116">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5898c-117">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5898c-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5898c-118">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5898c-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5898c-119">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5898c-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5898c-120">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="5898c-120">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="5898c-121">Na página **configuração de notificação por push** , clique no site que você deseja editar, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5898c-121">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5898c-122">Apague a caixa de seleção **Habilitar as notificações por push da Apple**.</span><span class="sxs-lookup"><span data-stu-id="5898c-122">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="5898c-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5898c-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5898c-124">Habilitar ou desabilitar notificações por push para o iPhone usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5898c-124">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5898c-125">As notificações por push para o iPhone da Apple podem ser habilitadas ou desabilitadas usando o cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5898c-125">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="5898c-126">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5898c-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5898c-127">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="5898c-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="5898c-128">Para habilitar as notificações por push para iPhone</span><span class="sxs-lookup"><span data-stu-id="5898c-128">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="5898c-129">Para habilitar as notificações por push para iPhone, defina o valor da propriedade EnableApplePushNotificationService como true ($True).</span><span class="sxs-lookup"><span data-stu-id="5898c-129">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="5898c-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5898c-130">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="5898c-131">Para desabilitar as notificações por push para iPhone</span><span class="sxs-lookup"><span data-stu-id="5898c-131">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="5898c-132">Para desativar as notificações por push para iPhone, defina o valor da propriedade EnableApplePushNotificationService como false ($False).</span><span class="sxs-lookup"><span data-stu-id="5898c-132">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="5898c-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5898c-133">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="5898c-134">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="5898c-134">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5898c-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="5898c-135">See Also</span></span>


[<span data-ttu-id="5898c-136">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5898c-136">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

