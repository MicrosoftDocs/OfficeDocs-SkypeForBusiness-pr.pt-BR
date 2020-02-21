---
title: 'Lync Server 2013: configurar uma rota de voz do E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 767f49aa0074e269de386b2db017dc183e4eb92d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="35c20-102">Configurar uma rota de voz do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35c20-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35c20-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="35c20-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="35c20-104">Para implantar o E9-1-1, é preciso primeiro configurar uma rota de voz de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="35c20-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="35c20-105">Para obter detalhes sobre como criar rotas de voz, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="35c20-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="35c20-106">É possível definir mais de uma rota se, por exemplo, sua implantação incluir um tronco SIP primário e um secundário.</span><span class="sxs-lookup"><span data-stu-id="35c20-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35c20-107">Para incluir informações de localização em um E9-1-1 INVITE, você precisa configurar o tronco SIP que se conecta ao provedor de serviços de E9-1-1 para encaminhar as chamadas de emergência através do gateway.</span><span class="sxs-lookup"><span data-stu-id="35c20-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="35c20-108">Para isso, defina o sinalizador EnablePIDFLOSupport no cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> como True.</span><span class="sxs-lookup"><span data-stu-id="35c20-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="35c20-109">O valor padrão de EnablePIDFLOSupport é False.</span><span class="sxs-lookup"><span data-stu-id="35c20-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="35c20-110">Por exemplo:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="35c20-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="35c20-111">Não é necessário habilitar o recebimento de locais para os gateways ELIN (número de identificação de local de emergência) e os gateways PSTN (rede telefônica pública comutada) de fallback.</span><span class="sxs-lookup"><span data-stu-id="35c20-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="35c20-112">Para obter detalhes sobre como trabalhar com rotas de voz, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="35c20-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="35c20-113">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="35c20-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="35c20-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="35c20-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="35c20-115">**New-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="35c20-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="35c20-116">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="35c20-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="35c20-117">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="35c20-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="35c20-118">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="35c20-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="35c20-119">Para configurar uma rota de voz de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="35c20-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="35c20-120">Faça logon no computador com uma conta que seja membro dos grupos RTCUniversalServerAdmins ou membro da função administrativa CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="35c20-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="35c20-121">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="35c20-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="35c20-122">Execute o cmdlet a seguir para criar um novo registro de uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="35c20-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="35c20-123">Esse deve ser o mesmo nome que você usará para a configuração **PSTN** na política de local.</span><span class="sxs-lookup"><span data-stu-id="35c20-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="35c20-124">Embora sua implantação tenha vários registros de uso de telefone, o exemplo a seguir adiciona "Uso de emergência" à lista atual de usos de PSTN disponíveis.</span><span class="sxs-lookup"><span data-stu-id="35c20-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="35c20-125">Para obter detalhes, consulte [Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="35c20-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="35c20-126">Execute o cmdlet a seguir para criar uma nova rota de voz usando o registro de uso PSTN criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="35c20-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="35c20-127">O padrão de número deve ser o mesmo usado na configuração de **Cadeia de Caracteres de Discagem de Emergência** na política de local.</span><span class="sxs-lookup"><span data-stu-id="35c20-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="35c20-128">Um sinal "+" é necessário porque o Lync adiciona "+" a chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="35c20-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="35c20-129">"Co1-pstngateway-1" é a ID de serviço do tronco SIP do provedor de serviços de E9-1-1 ou a ID de serviço do gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="35c20-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="35c20-130">O exemplo a seguir usa "EmergencyRoute" como o nome da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="35c20-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="35c20-p105">Opcionalmente, para conexões de tronco SIP, recomendamos que você execute o cmdlet a seguir para criar uma rota local para as chamadas que não são manipuladas pelo tronco SIP do provedor de serviços de E9-1-1. Essa rota será usada quando a conexão com o provedor de serviços de E9-1-1 não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="35c20-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="35c20-133">O exemplo a seguir pressupõe que o usuário tenha o uso "Local" em sua política de voz.</span><span class="sxs-lookup"><span data-stu-id="35c20-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

