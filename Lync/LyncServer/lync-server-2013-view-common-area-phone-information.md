---
title: 'Lync Server 2013: exibir informações de telefone de área comum'
description: 'Lync Server 2013: exibir informações de telefone de área comum.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572467"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="540b0-103">Exibir informações de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="540b0-103">View common area phone information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="540b0-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="540b0-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="540b0-105">Você pode exibir informações sobre os telefones de área comum configurados para uso em sua organização usando o cmdlet **Get-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="540b0-105">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="540b0-106">Usado sem qualquer parâmetro, este cmdlet retorna informações sobre todos os telefones de área comum.</span><span class="sxs-lookup"><span data-stu-id="540b0-106">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="540b0-107">Parâmetros opcionais fornecem maneiras diferentes de filtrar informações.</span><span class="sxs-lookup"><span data-stu-id="540b0-107">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="540b0-108">Por exemplo, você pode retornar todos os telefones de área comum que possuem objetos de contato em uma UO (unidade organizacional) especificada ou todos os objetos de contatos localizados em um edifício especificado.</span><span class="sxs-lookup"><span data-stu-id="540b0-108">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="540b0-109">Para obter detalhes sobre os parâmetros **Get-CsCommonAreaPhone** , consulte [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="540b0-109">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="540b0-110">Execute **Get-CsCommonAreaPhone** do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="540b0-110">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="540b0-111">Exibindo informações sobre todos os telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="540b0-111">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="540b0-112">Para exibir informações sobre todos os telefones de área comum, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="540b0-112">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="540b0-113">Você receberá informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="540b0-113">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="540b0-114">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="540b0-114">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

