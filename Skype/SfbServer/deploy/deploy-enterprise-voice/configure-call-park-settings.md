---
title: Definir as configurações de estacionamento de chamadas no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificar configurações de estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 8f4aa5025cbe364a44a45632ebcdf852ad6a65bc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a><span data-ttu-id="d1f8c-103">Definir as configurações de estacionamento de chamadas no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="d1f8c-103">Configure Call Park settings in Skype for Business 2015</span></span>
 
<span data-ttu-id="d1f8c-104">Modificar configurações de estacionamento de chamada no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d1f8c-105">Se você não quiser usar configurações de estacionamento de chamada padrão, você pode personalizá-los.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="d1f8c-106">Quando você instala o aplicativo de estacionamento de chamadas, configurações globais são configuradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="d1f8c-107">É possível modificar as configurações globais e também especificar configurações específicas do site.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="d1f8c-108">Use o cmdlet **New-CsCpsConfiguration** para criar novas configurações específicas do site.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="d1f8c-109">Use o cmdlet **Set-CsCpsConfiguration** para modificar as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1f8c-110">No mínimo, recomendamos configurar a opção **OnTimeoutURI** para o destino de fallback a ser usado quando uma chamada estacionada excede o tempo limite e o retorno de toque falha.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>
  
<span data-ttu-id="d1f8c-111">Use o cmdlet **New-CsCpsConfiguration** ou o cmdlet **Set-CsCpsConfiguration** para definir qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d1f8c-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>
  
|<span data-ttu-id="d1f8c-112">**Esta opção:**</span><span class="sxs-lookup"><span data-stu-id="d1f8c-112">**This option:**</span></span>|<span data-ttu-id="d1f8c-113">**Especifica a isso:**</span><span class="sxs-lookup"><span data-stu-id="d1f8c-113">**Specifies this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1f8c-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="d1f8c-114">**CallPickupTimeoutThreshold**</span></span> <br/> |<span data-ttu-id="d1f8c-115">A quantidade de tempo que passa após uma chamada ser estacionada antes que ela toque de volta no telefone no qual foi atendida.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="d1f8c-p102">O valor deve ser inserido no formato hh:mm:ss para especificar horas, minutos e segundos. O valor mínimo é 10 segundos e o valor máximo é 10 minutos. O padrão é 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
|<span data-ttu-id="d1f8c-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="d1f8c-119">**EnableMusicOnHold**</span></span> <br/> |<span data-ttu-id="d1f8c-120">Se a música é reproduzida para um chamador enquanto uma chamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="d1f8c-p103">Os valores são True ou False. O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-p103">Values are True or False. The default is True.</span></span>  <br/> |
|<span data-ttu-id="d1f8c-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="d1f8c-123">**MaxCallPickupAttempts**</span></span> <br/> |<span data-ttu-id="d1f8c-p104">O número de vezes que uma chamada estacionada retorna o toque para o telefone de resposta antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback que é especificado para **OnTimeoutURI**. O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/> |
|<span data-ttu-id="d1f8c-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="d1f8c-126">**OnTimeoutURI**</span></span> <br/> |<span data-ttu-id="d1f8c-127">O endereço SIP do usuário ou grupo de resposta para o qual uma chamada estacionada não atendida é roteada quando **MaxCallPickupAttempts** é excedido.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="d1f8c-p105">O valor deve ser um URI do SIP que começa com a cadeia de caracteres sip:. Por exemplo, sip:bob@contoso.com. O padrão é nenhum endereço de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/> |
   
### <a name="to-configure-call-park-settings"></a><span data-ttu-id="d1f8c-130">Para definir as configurações de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="d1f8c-130">To configure Call Park settings</span></span>

1. <span data-ttu-id="d1f8c-131">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-131">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d1f8c-132">Execute:</span><span class="sxs-lookup"><span data-stu-id="d1f8c-132">Run:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="d1f8c-133">Use o cmdlet **Get-CsSite** para identificar o site.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-133">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="d1f8c-134">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1f8c-134">For details, see Lync Server Management Shell documentation.</span></span>
  
    <span data-ttu-id="d1f8c-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1f8c-135">For example:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="d1f8c-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d1f8c-136">See also</span></span>

#### 

[<span data-ttu-id="d1f8c-137">Personalizar a música de estacionamento de chamada em espera inSkype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="d1f8c-137">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)
#### 

[<span data-ttu-id="d1f8c-138">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1f8c-138">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="d1f8c-139">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1f8c-139">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="d1f8c-140">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="d1f8c-140">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

