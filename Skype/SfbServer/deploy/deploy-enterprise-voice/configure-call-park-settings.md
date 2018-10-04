---
title: Definir configurações de estacionamento de chamada no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificar configurações de estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 4a80b9e60085c3091aacbbf619f0dbe672b64251
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373674"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Definir configurações de estacionamento de chamada no Skype para negócios

Modificar configurações de estacionamento de chamada no Skype para Business Server Enterprise Voice.

Se você não quiser usar configurações de estacionamento de chamada padrão, você pode personalizá-los. Quando você instala o aplicativo de estacionamento de chamadas, configurações globais são configuradas por padrão. É possível modificar as configurações globais e também especificar configurações específicas do site. Use o cmdlet **New-CsCpsConfiguration** para criar novas configurações específicas do site. Use o cmdlet **Set-CsCpsConfiguration** para modificar as configurações existentes.

> [!NOTE]
> No mínimo, recomendamos configurar a opção **OnTimeoutURI** para o destino de fallback a ser usado quando uma chamada estacionada excede o tempo limite e o retorno de toque falha.

Use o cmdlet **New-CsCpsConfiguration** ou o cmdlet **Set-CsCpsConfiguration** para definir qualquer uma das seguintes configurações:


| **Esta opção:**                     | **Especifica:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | A quantidade de tempo que passa após uma chamada ser estacionada antes que ela toque de volta no telefone no qual foi atendida.  <br/> O valor deve ser inserido no formato hh:mm:ss para especificar horas, minutos e segundos. O valor mínimo é 10 segundos e o valor máximo é 10 minutos. O padrão é 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Se a música é reproduzida para um chamador enquanto uma chamada está estacionada.  <br/> Os valores são True ou False. O padrão é True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | O número de vezes que uma chamada estacionada retorna o toque para o telefone de resposta antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback que é especificado para **OnTimeoutURI**. O padrão é 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | O endereço SIP do usuário ou grupo de resposta para o qual uma chamada estacionada não atendida é roteada quando **MaxCallPickupAttempts** é excedido. <br/> O valor deve ser um URI do SIP que começa com a cadeia de caracteres sip:. Por exemplo, sip:bob@contoso.com. O padrão é nenhum endereço de encaminhamento.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Para definir as configurações de estacionamento de chamada

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Execute:

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Use o cmdlet **Get-CsSite** para identificar o site. Para obter detalhes, consulte Skype para documentação Business Server Management Shell.

    Por exemplo:

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Consulte também

[Personalizar a música de espera do estacionamento de chamadas no Skype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)