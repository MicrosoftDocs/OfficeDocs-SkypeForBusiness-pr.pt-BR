---
title: Configurar as definições do parque de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifique as configurações do parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: e9410d3b088e5978588de991aeaa9da73327f50a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768124"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="719d6-103">Configurar as definições do parque de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="719d6-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="719d6-104">Modifique as configurações do parque de chamadas no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="719d6-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="719d6-105">Se não quiser usar as configurações padrão de estacionamento de chamadas, você poderá personalizá-las.</span><span class="sxs-lookup"><span data-stu-id="719d6-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="719d6-106">Quando você instala o aplicativo de estacionamento de chamada, as configurações globais são configuradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="719d6-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="719d6-107">É possível modificar as configurações globais e também especificar configurações específicas do site.</span><span class="sxs-lookup"><span data-stu-id="719d6-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="719d6-108">Use o cmdlet **New-CsCpsConfiguration** para criar configurações específicas do site.</span><span class="sxs-lookup"><span data-stu-id="719d6-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="719d6-109">Use o cmdlet **Set-CsCpsConfiguration** para modificar as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="719d6-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="719d6-110">No mínimo, recomendamos configurar a opção **OnTimeoutURI** para o destino de fallback a ser usado quando uma chamada estacionada excede o tempo limite e o retorno de toque falha.</span><span class="sxs-lookup"><span data-stu-id="719d6-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="719d6-111">Use os cmdets **New-CsCpsConfiguration** ou **Set-CsCpsConfiguration** para definir qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="719d6-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="719d6-112">**Esta opção:**</span><span class="sxs-lookup"><span data-stu-id="719d6-112">**This option:**</span></span>                     | <span data-ttu-id="719d6-113">**Especifica:**</span><span class="sxs-lookup"><span data-stu-id="719d6-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="719d6-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="719d6-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="719d6-115">A quantidade de tempo que passa após uma chamada ser estacionada antes que ela toque de volta no telefone no qual foi atendida.</span><span class="sxs-lookup"><span data-stu-id="719d6-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="719d6-p102">O valor deve ser inserido no formato hh:mm:ss para especificar horas, minutos e segundos. O valor mínimo é 10 segundos e o valor máximo é 10 minutos. O padrão é 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="719d6-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="719d6-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="719d6-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="719d6-120">Se a música é reproduzida para um chamador enquanto uma chamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="719d6-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="719d6-p103">Os valores são True ou False. O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="719d6-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="719d6-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="719d6-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="719d6-p104">O número de vezes que uma chamada estacionada retorna o toque para o telefone de resposta antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback que é especificado para **OnTimeoutURI**. O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="719d6-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="719d6-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="719d6-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="719d6-127">O endereço SIP do usuário ou grupo de resposta para o qual uma chamada estacionada não atendida é roteada quando **MaxCallPickupAttempts** é excedido.</span><span class="sxs-lookup"><span data-stu-id="719d6-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="719d6-p105">O valor deve ser um URI do SIP que começa com a cadeia de caracteres sip:. Por exemplo, sip:bob@contoso.com. O padrão é nenhum endereço de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="719d6-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="719d6-131">Para configurar as configurações do estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="719d6-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="719d6-132">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="719d6-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="719d6-133">Execute:</span><span class="sxs-lookup"><span data-stu-id="719d6-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="719d6-134">Use o cmdlet **Get-CsSite** para identificar o site.</span><span class="sxs-lookup"><span data-stu-id="719d6-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="719d6-135">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="719d6-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="719d6-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="719d6-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="719d6-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="719d6-137">See also</span></span>

[<span data-ttu-id="719d6-138">Personalizar a música de espera do estacionamento de chamadas no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="719d6-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="719d6-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="719d6-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="719d6-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="719d6-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="719d6-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="719d6-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
