---
title: 'Lync Server 2013: testar definições de configuração do tronco SIP'
description: 'Lync Server 2013: testar as definições de configuração do tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44fe2ef5123bec31fafaff2d811a501e5cca4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558267"
---
# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d9d14-103">Testar as definições de configuração do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d14-103">Test SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9d14-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d9d14-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d9d14-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="d9d14-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="d9d14-107">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="d9d14-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="d9d14-108">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="d9d14-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="d9d14-109">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="d9d14-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="d9d14-110">Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="d9d14-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d9d14-111">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="d9d14-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="d9d14-112">Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar que um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.</span><span class="sxs-lookup"><span data-stu-id="d9d14-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="d9d14-113">As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d9d14-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="d9d14-114">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9d14-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d9d14-115">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="d9d14-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="d9d14-116">Para testar as definições de configuração do tronco SIP</span><span class="sxs-lookup"><span data-stu-id="d9d14-116">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="d9d14-117">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="d9d14-117">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

