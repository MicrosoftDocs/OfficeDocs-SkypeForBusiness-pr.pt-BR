---
title: Configurar escape da caixa postal no Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumo: Saiba como configurar escape da caixa postal no Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios.'
ms.openlocfilehash: 29d8f03a23ba562cdb6636cd2aa7f3166e17404c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893039"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar escape da caixa postal no Skype para negócios

**Resumo:** Saiba como configurar escape da caixa postal no Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios.

Quando um usuário configura o toque simultâneo para um celular, um chamador geralmente será roteado para caixa postal do usuário pessoal se o telefone celular está desativado, sem bateria ou fora do intervalo. Com o Skype para Business Server, os usuários podem optar por ter relacionado aos negócios as chamadas roteadas para seu sistema de correio de voz corporativa. Especificamente, um temporizador pode ser configurado e se a chamada é atendida por postal da operadora dentro do intervalo de tempo definido, o Skype para Business Server será desconectada do sistema de caixa postal da operadora (e caixa postal do usuário pessoal), enquanto o usuário pontos de extremidade restantes no sistema corporativo continuam a tocar. Dessa forma, o chamador é roteado automaticamente para postal corporativo do usuário.

Essa configuração é realizada usando o Skype para o cmdlet do Shell de gerenciamento do servidor de negócios, **Set-CsVoicePolicy**, no nível de política de voz, com os seguintes parâmetros.

### <a name="to-configure-voice-mail-escape"></a>Para configurar o escape da caixa postal

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape.

   - **PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.

## <a name="example"></a>Exemplo

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Confira também

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

