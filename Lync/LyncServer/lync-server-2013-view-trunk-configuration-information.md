---
title: 'Lync Server 2013: exibir informações de configuração do tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 102fb942397b8329da067d8c41c16ec393076a00
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="05166-102">Exibir informações de configuração de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05166-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05166-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="05166-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="05166-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="05166-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="05166-106">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="05166-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="05166-107">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="05166-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="05166-108">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="05166-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="05166-109">Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="05166-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="05166-110">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="05166-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="05166-111">Para exibir informações de configuração do tronco SIP usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="05166-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="05166-112">No painel de controle do Lync Server, clique em **Roteamento de voz** e em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="05166-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="05166-113">Na guia **configuração de tronco** , você verá uma lista de todas as definições de configuração de tronco; para cada coleção, você verá os valores das propriedades de **nome**, **escopo**, **estado**e **bypass de mídia** , juntamente com o número de **usos de PSTN**, regras de número de **chamada**e **regras de número chamadas** associadas à coleção.</span><span class="sxs-lookup"><span data-stu-id="05166-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="05166-114">Para exibir informações adicionais sobre um coleção de configurações de tronco, clique na coleção de interesse, clique em **Editar** e depois clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="05166-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="05166-115">Observe que você pode exibir informações detalhadas somente de uma coleção de configurações de tronco por vez.</span><span class="sxs-lookup"><span data-stu-id="05166-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="05166-116">Exibindo informações de configuração do tronco SIP usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05166-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="05166-117">As definições de configuração do tronco SIP podem ser exibidas usando o Lync Server PowerShell e o cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="05166-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="05166-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05166-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="05166-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="05166-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="05166-120">Para exibir informações de configuração do tronco SIP</span><span class="sxs-lookup"><span data-stu-id="05166-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="05166-121">Para exibir informações sobre todas as suas definições de configuração de tronco SIP, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="05166-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="05166-122">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="05166-122">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

<span data-ttu-id="05166-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="05166-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

