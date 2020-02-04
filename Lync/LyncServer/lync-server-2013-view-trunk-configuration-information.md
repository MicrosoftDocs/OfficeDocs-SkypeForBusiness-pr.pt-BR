---
title: 'Lync Server 2013: exibir informações de configuração de tronco'
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
ms.openlocfilehash: 77f53a4263fd0e0b64ccd6894d27e30c0c5be95c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="53fb0-102">Exibir informações de configuração de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53fb0-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53fb0-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="53fb0-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="53fb0-104">As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="53fb0-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="53fb0-105">Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="53fb0-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="53fb0-106">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="53fb0-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="53fb0-107">As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="53fb0-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="53fb0-108">Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="53fb0-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="53fb0-109">Ao instalar o Microsoft Lync Server 2013, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="53fb0-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="53fb0-110">Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="53fb0-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="53fb0-111">Para ver as informações de configuração do tronco SIP usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="53fb0-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="53fb0-112">No painel de controle do Lync Server, clique em **Roteamento de voz** e, em seguida, clique em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="53fb0-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="53fb0-113">Na guia **configuração de tronco** , você verá uma lista de todas as suas definições de configuração de tronco; para cada coleção, você verá os valores para as propriedades **nome**, **escopo**, **estado**e **ignorar mídia** , juntamente com o número de **usos de PSTN**, **as regras de número de chamada**e **as regras de número chamadas** associadas à coleção.</span><span class="sxs-lookup"><span data-stu-id="53fb0-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="53fb0-114">Para ver detalhes adicionais sobre uma coleção de definições de configuração de tronco, clique na coleção de interesse, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="53fb0-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="53fb0-115">Observe que você pode exibir informações detalhadas apenas para um conjunto de configurações de tronco de configuração de tronco de cada vez.</span><span class="sxs-lookup"><span data-stu-id="53fb0-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="53fb0-116">Exibindo informações de configuração de tronco SIP usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53fb0-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="53fb0-117">As configurações de tronco SIP podem ser exibidas usando o Lync Server PowerShell e o cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="53fb0-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="53fb0-118">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53fb0-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="53fb0-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="53fb0-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="53fb0-120">Para ver as informações de configuração do tronco SIP</span><span class="sxs-lookup"><span data-stu-id="53fb0-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="53fb0-121">Para ver as informações sobre todas as suas configurações de tronco SIP, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="53fb0-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="53fb0-122">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="53fb0-122">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="53fb0-123">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="53fb0-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

