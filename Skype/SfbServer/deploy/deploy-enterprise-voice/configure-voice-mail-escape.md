---
title: Configurar a saída de caixa postal no Skype for Business
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
description: 'Resumo: saiba como configurar o escape de caixa postal Skype for Business Server usando o Shell de Gerenciamento Skype for Business Server Desembolso.'
ms.openlocfilehash: f94a9e78d5f1b88644691d43b7c24169e6122e6188f7ee45c095521230b6be3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279419"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar a saída de caixa postal no Skype for Business

**Resumo:** Saiba como configurar o escape de caixa postal Skype for Business Server usando o Shell de Gerenciamento Skype for Business Server Desembolso.

Quando um usuário configura o toque simultâneo para um telefone celular, um chamador normalmente será roteado para a caixa postal pessoal do usuário se o telefone celular estiver desligado, sem bateria ou fora do intervalo. Com Skype for Business Server , os usuários podem optar por ter chamadas relacionadas aos negócios roteados para seu sistema de caixa postal corporativo. Especificamente, um temporizador pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Skype for Business Server se desconecta do sistema de caixa postal da operadora (e da caixa postal pessoal do usuário), enquanto os pontos de extremidade restantes do usuário no sistema corporativo continuam a tocar. Dessa forma, o chamador é automaticamente roteado para a caixa postal corporativa do usuário.

Essa configuração é executada usando o cmdlet Skype for Business Server Shell de Gerenciamento, **Set-CsVoicePolicy**, no nível da política de voz, com os seguintes parâmetros.

### <a name="to-configure-voice-mail-escape"></a>Para configurar a escape de caixa postal

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

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