---
title: Configurar o recurso de mensagem de voz no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumo: saiba como configurar o recurso de mensagem de voz no Skype for Business Server usando o Shell de gerenciamento do Skype for Business Server.'
ms.openlocfilehash: 27f283f4bfb64aa950bd9e72a9d6fdc17df91ba0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001211"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar o recurso de mensagem de voz no Skype for Business

**Resumo:** Saiba como configurar o recurso de mensagem de voz no Skype for Business Server usando o Shell de gerenciamento do Skype for Business Server.

Quando um usuário configura o toque simultâneo para um celular, um chamador geralmente será roteado para a caixa postal pessoal do usuário se o celular estiver desligado, sem bateria ou estiver fora do alcance da energia. Com o Skype for Business Server, os usuários podem optar por fazer chamadas relacionadas a negócios roteadas para o sistema de caixa postal da empresa. Especificamente, um temporizador pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Skype for Business Server será desconectado do sistema de caixa postal da operadora (e da caixa postal pessoal do usuário), enquanto o botão do usuário os pontos de extremidade restantes no sistema corporativo continuam a tocar. Dessa forma, o chamador será encaminhado automaticamente para a caixa postal corporativa do usuário.

Essa configuração é realizada usando o cmdlet do Shell de gerenciamento do Skype for Business Server, **set-CsVoicePolicy**, no nível da política de voz, com os parâmetros a seguir.

### <a name="to-configure-voice-mail-escape"></a>Para configurar o escape da caixa postal

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape.

   - **PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.

## <a name="example"></a>Exemplo

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Confira também

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

