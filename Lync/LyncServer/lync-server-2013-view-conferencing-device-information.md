---
title: 'Lync Server 2013: exibir informações sobre o dispositivo de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc0065416582dd87f1c48a2dd051c237fbd6868
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="dff27-102">Exibir informações do dispositivo de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff27-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dff27-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="dff27-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="dff27-104">Você pode exibir informações sobre os dispositivos de conferência configurados para uso na sua organização usando o Windows PowerShell e o cmdlet **Get-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="dff27-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="dff27-105">Execute o cmdlet **Get-CsMeetingRoom** do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dff27-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dff27-106">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="dff27-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="dff27-107">Se você usar o cmdlet **Get-CsMeetingRoom** sem nenhum parâmetro, ele retornará informações sobre todos os seus dispositivos de conferência.</span><span class="sxs-lookup"><span data-stu-id="dff27-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="dff27-108">Parâmetros opcionais fornecem maneiras diferentes de filtrar informações.</span><span class="sxs-lookup"><span data-stu-id="dff27-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="dff27-109">Para obter detalhes, consulte a seção de parâmetros de [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="dff27-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="dff27-110">Exibindo informações sobre todos os dispositivos de conferência</span><span class="sxs-lookup"><span data-stu-id="dff27-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="dff27-111">Para exibir detalhes sobre todos os seus dispositivos de conferência, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="dff27-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="dff27-112">Este cmdlet retorna informações semelhantes às seguintes para cada dispositivo de conferência.</span><span class="sxs-lookup"><span data-stu-id="dff27-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="dff27-113">Observe que este exemplo mostra apenas algumas das informações que você verá ao executar este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dff27-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="dff27-114">Exibindo informações sobre um dispositivo de conferência específico</span><span class="sxs-lookup"><span data-stu-id="dff27-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="dff27-115">Para exibir informações de um dispositivo de conferência específico, inclua o parâmetro Identity seguido da identidade do dispositivo de conferência (normalmente, o nome de exibição do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="dff27-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="dff27-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="dff27-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="dff27-117">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="dff27-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

