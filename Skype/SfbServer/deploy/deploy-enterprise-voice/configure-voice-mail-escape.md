---
title: Configurar escape de caixa postal no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumo: saiba como configurar o escape de caixa postal no Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106367"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar escape de caixa postal no Skype for Business

**Resumo:** Saiba como configurar o escape de caixa postal no Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server.

Quando um usuário configura o toque simultâneo para um telefone celular, um chamador normalmente será roteado para a caixa postal pessoal do usuário se o telefone celular estiver desligado, sem bateria ou fora do intervalo. Com o Skype for Business Server, os usuários podem optar por ter chamadas relacionadas aos negócios roteados para seu sistema de caixa postal corporativo. Especificamente, um temporizador pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Skype for Business Server se desconecta do sistema de caixa postal da operadora (e da caixa postal pessoal do usuário), enquanto os pontos de extremidade restantes do usuário no sistema corporativo continuam a tocar. Dessa forma, o chamador é automaticamente roteado para a caixa postal corporativa do usuário.

Essa configuração é executada usando o cmdlet Shell de Gerenciamento do Skype for Business Server, **Set-CsVoicePolicy**, no nível da política de voz, com os seguintes parâmetros.

### <a name="to-configure-voice-mail-escape"></a>Para configurar a escape de caixa postal

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**

2. Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape

   - **PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.

## <a name="example"></a>Exemplo

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Confira também

[Configurando políticas de voz e registros de uso PSTN para autorizar privilégios e recursos de chamada](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)