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
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824921"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurar escape de caixa postal no Skype for Business

**Resumo:** Saiba como configurar o escape de caixa postal no Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server.

Quando um usuário configura toque simultâneo para um telefone celular, um chamador normalmente é roteado para a caixa postal pessoal do usuário se o telefone celular estiver desligado, sem bateria ou fora de alcance. Com o Skype for Business Server, os usuários podem optar por ter chamadas relacionadas aos negócios roteados para seu sistema de caixa postal corporativa. Especificamente, um temporizador pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Skype for Business Server se desconecta do sistema de caixa postal da operadora (e da caixa postal pessoal do usuário), enquanto os pontos de extremidade restantes do usuário no sistema corporativo continuam a tocar. Dessa forma, o chamador é automaticamente roteado para a caixa postal corporativa do usuário.

Essa configuração é realizada usando-se o cmdlet Do Shell de Gerenciamento do Skype for Business Server, **Set-CsVoicePolicy**, no nível da política de voz, com os parâmetros a seguir.

### <a name="to-configure-voice-mail-escape"></a>Para configurar o escape da caixa postal

1. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape

   - **PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.

## <a name="example"></a>Exemplo

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Confira também

[Configurando políticas de voz e registros de uso PSTN para autorizar privilégios e recursos de chamada](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

