---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como habilitar a QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814171"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="4ddb5-103">Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows</span><span class="sxs-lookup"><span data-stu-id="4ddb5-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="4ddb5-104">Quando você instala o Skype for Business Server, a QoS (Qualidade de Serviço) não será habilitada para dispositivos usados em sua organização que usem um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="4ddb5-105">Você pode verificar isso executando o seguinte comando no Shell do Skype for Business ServerManagement:</span><span class="sxs-lookup"><span data-stu-id="4ddb5-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="4ddb5-106">Supondo que você não tenha feito alterações em suas definições de configuração de mídia, você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="4ddb5-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="4ddb5-107">Se a propriedade EnableQoS estiver definida como False (como na saída anterior), isso significa que a Qualidade de Serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="4ddb5-108">Para habilitar a Qualidade de Serviço no escopo global, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="4ddb5-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="4ddb5-109">O comando anterior habilita o QoS no escopo global; no entanto, é importante observar que as definições de configuração de mídia também podem ser aplicadas ao escopo local.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="4ddb5-110">Se for necessário habilitar a Qualidade de Serviço para um site, inclua a Identidade das definições de configuração ao chamar Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="4ddb5-111">Por exemplo, este comando habilita o QoS para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="4ddb5-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="4ddb5-112">Você precisa habilitar a QoS no escopo do site?</span><span class="sxs-lookup"><span data-stu-id="4ddb5-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="4ddb5-113">Isso depende.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-113">That depends.</span></span> <span data-ttu-id="4ddb5-114">As configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="4ddb5-115">Suponha que você tenha a QoS habilitada no escopo global, mas desabilitada no escopo do site (para o site Redmond).</span><span class="sxs-lookup"><span data-stu-id="4ddb5-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="4ddb5-116">Nesse caso, a Qualidade de Serviço seria desabilitada para o site Redmond; isso porque as configurações do site têm precedência.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="4ddb5-117">Para habilitar a QoS para o site redmond, você teria que fazer isso usando as definições de configuração de mídia aplicadas a esse site.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="4ddb5-118">Se você quiser habilitar simultaneamente a QoS para todas as definições de configuração de mídia (independentemente do escopo), execute este comando no Shell de Gerenciamento do LSkype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="4ddb5-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="4ddb5-119">Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como False.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="4ddb5-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4ddb5-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="4ddb5-121">Isto oferece a habilidade de implementar o QoS em algumas partes da sua rede (por exemplo, no local Redmond) enquanto deixa a Qualidade do Serviço desabilitada em outras partes da sua rede.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="4ddb5-122">A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="4ddb5-123">Essas opções não estão disponíveis no Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="4ddb5-124">Os clientes do Skype for Business para iOS versão 6.17 e posterior agora são suportados para QoS.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="4ddb5-125">Esse recurso de QoS só é aplicável aos clientes do Skype for Business e dispositivos de telefone IP que são registrados diretamente em um Skype for Business interno ou servidor de pool do Lync em redes gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="4ddb5-126">A QoS não é aplicável ao tráfego roteado pela Internet.</span><span class="sxs-lookup"><span data-stu-id="4ddb5-126">QoS is not applicable for traffic routed over the Internet.</span></span>



