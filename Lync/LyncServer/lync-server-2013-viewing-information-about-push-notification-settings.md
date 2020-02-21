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
ms.openlocfilehash: 075deabdbc57bd809fce4bf3e4635309f367d69c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="d074e-102">Exibindo informações sobre configurações de notificação por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d074e-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d074e-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d074e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d074e-104">Notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas a um dispositivo móvel mesmo quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="d074e-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="d074e-105">As notificações de push notificam um usuário de eventos como um convite de IM novo ou perdido e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d074e-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="d074e-106">Você pode exibir as configurações de notificações por push de informações para dispositivos móveis usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d074e-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="d074e-107">Para exibir informações de notificação por push no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="d074e-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d074e-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d074e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d074e-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d074e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d074e-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d074e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d074e-111">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração de notificação de push**.</span><span class="sxs-lookup"><span data-stu-id="d074e-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="d074e-112">Na página **configuração de notificação por push** , clique no site que você deseja exibir, clique no menu **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d074e-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d074e-113">Exibindo informações de notificação por push usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d074e-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d074e-114">Você pode exibir as definições de configuração de notificação por push usando o Windows PowerShell e o cmdlet **Get-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d074e-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="d074e-115">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d074e-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d074e-116">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="d074e-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="d074e-117">Para exibir informações de configuração de notificação de push</span><span class="sxs-lookup"><span data-stu-id="d074e-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="d074e-118">Para exibir informações sobre todas as suas definições de configuração de notificação por push, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d074e-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="d074e-119">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="d074e-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="d074e-120">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d074e-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d074e-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="d074e-121">See Also</span></span>


[<span data-ttu-id="d074e-122">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d074e-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

