---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Aprenda a habilitar o QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232710"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="3bb98-103">Habilitando QoS no Skype para Business Server para dispositivos que não são baseados no Windows</span><span class="sxs-lookup"><span data-stu-id="3bb98-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="3bb98-104">Quando você instala o Skype para Business Server, Quality of Service (QoS) não será habilitado para todos os dispositivos usados na sua organização que usam um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="3bb98-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="3bb98-105">Você pode verificar isso executando o seguinte comando dentro do Skype para negócios ServerManagement Shell:</span><span class="sxs-lookup"><span data-stu-id="3bb98-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="3bb98-106">Supondo que você não tenha feito qualquer alteração para suas definições de configuração de mídia, você deve obter informação semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="3bb98-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="3bb98-107">Se a propriedade EnableQoS estiver definida como False (como a saída anterior) significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="3bb98-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="3bb98-108">Para habilitar o Quality of Service no escopo global, execute o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="3bb98-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="3bb98-109">O comando anterior habilita o QoS no escopo global; No entanto, é importante observar que as definições de configuração de mídia também podem ser aplicadas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="3bb98-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="3bb98-110">Se você precisar habilitar o Quality of Service para um site, você deve incluir a identidade das definições de configuração ao chamar Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3bb98-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="3bb98-111">Por exemplo, este comando habilita o QoS para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="3bb98-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="3bb98-112">Você precisa habilitar o QoS no escopo do site?</span><span class="sxs-lookup"><span data-stu-id="3bb98-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="3bb98-113">Que depende.</span><span class="sxs-lookup"><span data-stu-id="3bb98-113">That depends.</span></span> <span data-ttu-id="3bb98-114">Configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global.</span><span class="sxs-lookup"><span data-stu-id="3bb98-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="3bb98-115">Suponha que você tenha QoS habilitado no escopo global, mas desativada no escopo do site (para o site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="3bb98-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="3bb98-116">Nesse caso, Quality of Service seria desativado para o site de Redmond; Isso ocorre porque as definições do site têm precedência.</span><span class="sxs-lookup"><span data-stu-id="3bb98-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="3bb98-117">Para habilitar o QoS para o site Redmond, você precisará fazê-lo usando as definições de configuração de mídia aplicada ao site.</span><span class="sxs-lookup"><span data-stu-id="3bb98-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="3bb98-118">Se você deseja habilitar simultaneamente o QoS para todas as suas definições de configuração de mídia (independente do escopo), execute este comando a partir do LSkype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="3bb98-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="3bb98-119">Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows, definindo o valor da propriedade EnableQoS como False.</span><span class="sxs-lookup"><span data-stu-id="3bb98-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="3bb98-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3bb98-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="3bb98-121">Isso oferece a capacidade para implementar o QoS em algumas partes da sua rede (por exemplo, no site de Redmond), deixando Quality of Service desabilitada em outras partes da sua rede.</span><span class="sxs-lookup"><span data-stu-id="3bb98-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="3bb98-122">QoS só possam ser habilitados e desabilitados pelo uso do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bb98-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="3bb98-123">Essas opções não estão disponíveis no Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3bb98-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


