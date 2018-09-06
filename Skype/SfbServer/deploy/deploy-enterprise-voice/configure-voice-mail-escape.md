---
title: Configurar escape da caixa postal no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumo: Saiba como configurar escape da caixa postal no Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios.'
ms.openlocfilehash: 4d93f188b137c3ecea014b8e407456e20195cbe1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261361"
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

## <a name="see-also"></a>Consulte também

[Configurando políticas de voz e registros de uso do PSTN para autorizar privilégios e recursos de chamada](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

