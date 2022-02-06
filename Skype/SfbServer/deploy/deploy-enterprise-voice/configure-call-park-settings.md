---
title: Configurar configurações de Estacionamento de Chamada Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificar as configurações do Estacionamento de Chamada Skype for Business Server Enterprise Voice.
---

# <a name="configure-call-park-settings-in-skype-for-business"></a>Configurar configurações de Estacionamento de Chamada Skype for Business

Modificar as configurações do Estacionamento de Chamada Skype for Business Server Enterprise Voice.

Se você não quiser usar as configurações padrão do Estacionamento de Chamada, você pode personalizá-las. Quando você instala o aplicativo Estacionamento de Chamada, as configurações globais são configuradas por padrão. É possível modificar as configurações globais e também especificar configurações específicas do site. Use o cmdlet **New-CsCpsConfiguration** para criar configurações específicas do site. Use o cmdlet **Set-CsCpsConfiguration** para modificar as configurações existentes.

> [!NOTE]
> No mínimo, recomendamos configurar a opção **OnTimeoutURI** para o destino de fallback a ser usado quando uma chamada estacionada excede o tempo limite e o retorno de toque falha.

Use os cmdets **New-CsCpsConfiguration** ou **Set-CsCpsConfiguration** para definir qualquer uma das seguintes configurações:


| **Esta opção:**                     | **Especifica:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | A quantidade de tempo que passa após uma chamada ser estacionada antes que ela toque de volta no telefone no qual foi atendida.  <br/> O valor deve ser inserido no formato hh:mm:ss para especificar horas, minutos e segundos. O valor mínimo é 10 segundos e o valor máximo é 10 minutos. O padrão é 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Se a música é reproduzida para um chamador enquanto uma chamada está estacionada.  <br/> Os valores são True ou False. O padrão é True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | O número de vezes que uma chamada estacionada retorna o toque para o telefone de resposta antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback que é especificado para **OnTimeoutURI**. O padrão é 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | O endereço SIP do usuário ou grupo de resposta para o qual uma chamada estacionada não atendida é roteada quando **MaxCallPickupAttempts** é excedido. <br/> O valor deve ser um URI do SIP que começa com a cadeia de caracteres sip:. Por exemplo, sip:bob@contoso.com. O padrão é nenhum endereço de encaminhamento.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Para configurar as configurações do Estacionamento de Chamada

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

2. Executar:

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Use o cmdlet **Get-CsSite** para identificar o site. Para obter detalhes, consulte Skype for Business Server documentação do Shell de Gerenciamento.

    Por exemplo:

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Confira também

[Personalizar música do Estacionamento de Chamada em espera noSkype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)