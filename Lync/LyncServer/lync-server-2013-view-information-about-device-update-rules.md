---
title: 'Lync Server 2013: exibir informações sobre regras de atualização de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506378"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="60dee-102">Exibir informações sobre as regras de atualização de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60dee-102">View information about Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60dee-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="60dee-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="60dee-104">Exibir detalhes sobre as regras de atualização de dispositivos que já foram importadas, incluindo o tipo, o modelo e a marca de dispositivos aos quais a atualização se aplica; versão e tipo de atualização; e a localidade e o pool para a atualização.</span><span class="sxs-lookup"><span data-stu-id="60dee-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="60dee-105">As informações estão disponíveis para todas as regras de atualização de dispositivo importadas, que estão aguardando aprovação, implantadas (aprovadas), recuperadas (restauradas) e aquelas que você optou por não usar (Redefinir).</span><span class="sxs-lookup"><span data-stu-id="60dee-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="60dee-106">Acessar essas informações do painel de controle do Lync Server ou do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60dee-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60dee-107">Para obter detalhes sobre como importar, aprovar, redefinir, restaurar e remover regras, consulte os tópicos listados em <A href="lync-server-2013-device-update-rules.md">regras de atualização de dispositivos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="60dee-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="60dee-108">Para exibir as regras de atualização de dispositivo usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="60dee-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="60dee-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="60dee-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="60dee-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60dee-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60dee-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60dee-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="60dee-112">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **atualização de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="60dee-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="60dee-113">As regras importadas são listadas na página **atualização de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="60dee-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="60dee-114">Exibindo regras de atualização de dispositivo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60dee-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="60dee-115">Informações detalhadas sobre todas as suas regras de atualização de dispositivo também podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="60dee-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="60dee-116">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60dee-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60dee-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="60dee-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="60dee-118">Para exibir todas as suas regras de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="60dee-118">To view all your device update rules</span></span>

  - <span data-ttu-id="60dee-119">O comando a seguir retorna informações sobre todas as regras de atualizações de dispositivo configuradas para uso na sua organização:</span><span class="sxs-lookup"><span data-stu-id="60dee-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="60dee-120">O comando retorna informações semelhantes às seguintes para cada uma das suas regras de atualização de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="60dee-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="60dee-121">Para exibir todas as regras de atualização de dispositivo em um servidor Web específico</span><span class="sxs-lookup"><span data-stu-id="60dee-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="60dee-122">Para exibir as regras de atualização de dispositivo em um computador específico, use o parâmetro Filter seguido da identidade do servidor e do caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="60dee-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="60dee-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="60dee-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="60dee-124">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="60dee-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

