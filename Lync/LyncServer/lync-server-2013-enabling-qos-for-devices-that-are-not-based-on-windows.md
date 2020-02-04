---
title: 'Lync Server 2013: Habilitando a QoS para dispositivos que não são baseados no Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="06b41-102">Habilitando a QoS no Lync Server 2013 para dispositivos que não são baseados no Windows</span><span class="sxs-lookup"><span data-stu-id="06b41-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06b41-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="06b41-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="06b41-104">Quando você instala o Microsoft Lync Server 2013, a qualidade do serviço (QoS) não será habilitada para nenhum dispositivo usado em sua organização que use um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="06b41-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="06b41-105">Você pode verificar isso executando o seguinte comando no Shell de gerenciamento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="06b41-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="06b41-106">Presumindo que você não fez alterações nas configurações de sua configuração de mídia, você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="06b41-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="06b41-107">Se a propriedade EnableQoS estiver definida como false (como na saída anterior), isso significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="06b41-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="06b41-108">A QoS é habilitada por padrão para os dispositivos do Lync Phone Edition; no entanto, é possível desabilitar a qualidade do serviço para o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="06b41-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="06b41-109">Para habilitar a qualidade de serviço no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="06b41-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="06b41-110">O comando anterior permite QoS no escopo global; no entanto, é importante observar que as configurações de configuração de mídia também podem ser aplicadas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="06b41-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="06b41-111">Se você precisar habilitar a qualidade do serviço para um site, deve incluir a identidade das configurações ao chamar Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="06b41-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="06b41-112">Por exemplo, esse comando habilita a QoS para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="06b41-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="06b41-113">Você precisa habilitar a QoS no escopo do site?</span><span class="sxs-lookup"><span data-stu-id="06b41-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="06b41-114">Isso depende.</span><span class="sxs-lookup"><span data-stu-id="06b41-114">That depends.</span></span> <span data-ttu-id="06b41-115">As configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global.</span><span class="sxs-lookup"><span data-stu-id="06b41-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="06b41-116">Suponha que você tenha o QoS habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond.) Nesse caso, a qualidade do serviço será desabilitada para o site de Redmond; Isso porque as configurações do site têm precedência.</span><span class="sxs-lookup"><span data-stu-id="06b41-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="06b41-117">Para habilitar a QoS para o site Redmond, você precisará fazer isso usando as definições de configuração de mídia aplicadas a esse site.</span><span class="sxs-lookup"><span data-stu-id="06b41-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="06b41-118">Se você quiser habilitar simultaneamente a QoS para todas as suas configurações de mídia (independentemente do escopo), execute esse comando dentro do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="06b41-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="06b41-119">Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como false.</span><span class="sxs-lookup"><span data-stu-id="06b41-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="06b41-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="06b41-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="06b41-121">Isso oferece a capacidade de implementar a QoS em algumas partes da rede (por exemplo, no site Redmond), deixando a qualidade do serviço desabilitada em outras partes da sua rede.</span><span class="sxs-lookup"><span data-stu-id="06b41-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="06b41-122">A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell essas opções não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06b41-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

