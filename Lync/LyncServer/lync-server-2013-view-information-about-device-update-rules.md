---
title: 'Lync Server 2013: exibir informações sobre as regras de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="1c6a9-102">Exibir informações sobre as regras de atualização de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c6a9-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c6a9-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1c6a9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1c6a9-104">Exiba detalhes sobre as regras de atualização de dispositivos que já foram importadas, incluindo o tipo, o modelo e a marca de dispositivos aos quais a atualização se aplica; versão e tipo de atualização; e a localidade e o pool para a atualização.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="1c6a9-105">As informações estão disponíveis para todas as regras de atualização de dispositivo importadas, que têm aprovação pendente, implantada (aprovada), recuperada (restaurada) e aquelas que você decidiu não usar (Redefinir).</span><span class="sxs-lookup"><span data-stu-id="1c6a9-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="1c6a9-106">Acesse essas informações de um painel de controle do Lync Server ou do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c6a9-107">Para obter detalhes sobre como importar, aprovar, redefinir, restaurar e remover regras, consulte os tópicos listados em <A href="lync-server-2013-device-update-rules.md">regras de atualização de dispositivos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="1c6a9-108">Para exibir as regras de atualização de dispositivos usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1c6a9-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1c6a9-109">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c6a9-110">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c6a9-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1c6a9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c6a9-112">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação de **atualização do dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="1c6a9-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="1c6a9-113">As regras importadas são listadas na página **atualização do dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="1c6a9-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1c6a9-114">Exibindo regras de atualização de dispositivos usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c6a9-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1c6a9-115">Informações detalhadas sobre todas as suas regras de atualização de dispositivo também podem ser visualizadas usando o Windows PowerShell e o cmdlet **Get-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="1c6a9-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="1c6a9-116">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c6a9-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="1c6a9-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="1c6a9-118">Para ver todas as suas regras de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="1c6a9-118">To view all your device update rules</span></span>

  - <span data-ttu-id="1c6a9-119">O comando a seguir retorna informações sobre todas as regras de atualizações de dispositivo configuradas para uso em sua organização:</span><span class="sxs-lookup"><span data-stu-id="1c6a9-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="1c6a9-120">O comando retorna informações semelhantes às seguintes para cada uma de suas regras de atualização de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="1c6a9-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="1c6a9-121">Para exibir todas as regras de atualização de dispositivos em um servidor Web específico</span><span class="sxs-lookup"><span data-stu-id="1c6a9-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="1c6a9-122">Para exibir as regras de atualização de dispositivo em um computador específico, use o parâmetro Filter seguido pela identidade do servidor e o caractere\*curinga ().</span><span class="sxs-lookup"><span data-stu-id="1c6a9-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="1c6a9-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1c6a9-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="1c6a9-124">Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="1c6a9-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

