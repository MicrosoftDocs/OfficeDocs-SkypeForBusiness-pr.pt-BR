---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como habilitar a QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279407"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="5c38b-103">Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows</span><span class="sxs-lookup"><span data-stu-id="5c38b-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="5c38b-104">Quando você instala o Skype for Business Server, a qualidade do serviço (QoS) não será habilitada para nenhum dispositivo usado em sua organização que use um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="5c38b-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="5c38b-105">Você pode verificar isso executando o seguinte comando no Shell do Skype for Business ServerManagement:</span><span class="sxs-lookup"><span data-stu-id="5c38b-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="5c38b-106">Presumindo que você não fez alterações em suas configurações de configuração de mídia, você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="5c38b-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="5c38b-107">Se a propriedade EnableQoS estiver definida como false (como na saída anterior), isso significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="5c38b-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="5c38b-108">Para habilitar a qualidade de serviço no escopo global, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="5c38b-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="5c38b-109">O comando anterior permite QoS no escopo global; no entanto, é importante observar que as configurações de configuração de mídia também podem ser aplicadas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="5c38b-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="5c38b-110">Se precisar habilitar a qualidade do serviço para um site, você deve incluir a identidade das configurações ao chamar Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5c38b-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="5c38b-111">Por exemplo, esse comando habilita a QoS para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="5c38b-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="5c38b-112">Você precisa habilitar a QoS no escopo do site?</span><span class="sxs-lookup"><span data-stu-id="5c38b-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="5c38b-113">Isso depende.</span><span class="sxs-lookup"><span data-stu-id="5c38b-113">That depends.</span></span> <span data-ttu-id="5c38b-114">As configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global.</span><span class="sxs-lookup"><span data-stu-id="5c38b-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="5c38b-115">Suponha que você tenha o QoS habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="5c38b-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="5c38b-116">Nesse caso, a qualidade do serviço seria desabilitada para o site de Redmond; Isso porque as configurações do site têm precedência.</span><span class="sxs-lookup"><span data-stu-id="5c38b-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="5c38b-117">Para habilitar a QoS para o site Redmond, você precisaria fazê-lo usando as definições de configuração de mídia aplicadas a esse site.</span><span class="sxs-lookup"><span data-stu-id="5c38b-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="5c38b-118">Se você quiser habilitar simultaneamente a QoS para todas as suas configurações de mídia (independentemente do escopo), execute esse comando dentro do Shell de gerenciamento do LSkype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="5c38b-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="5c38b-119">Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como false.</span><span class="sxs-lookup"><span data-stu-id="5c38b-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="5c38b-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5c38b-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="5c38b-121">Isso oferece a capacidade de implementar a QoS em algumas partes da rede (por exemplo, no site Redmond), deixando a qualidade do serviço desabilitada em outras partes da sua rede.</span><span class="sxs-lookup"><span data-stu-id="5c38b-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="5c38b-122">A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c38b-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="5c38b-123">Essas opções não estão disponíveis no painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c38b-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


