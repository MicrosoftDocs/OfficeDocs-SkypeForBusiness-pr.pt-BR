---
title: Gerenciar Políticas de Caixa Postal
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gerenciar políticas de caixa postal para seus usuários.
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370824"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

> [!WARNING]
> Para Skype for Business clientes, desabilitar a caixa postal por meio de uma política Microsoft Teams chamada também pode desabilitar o serviço de caixa postal para seus Skype for Business usuários.

Você pode usar políticas de caixa postal para controlar diferentes recursos relacionados ao Caixa postal na Nuvem.

## <a name="voicemail-organization-defaults-for-all-users"></a>O padrão da organização da caixa postal para todos os usuários
- A transcrição da caixa postal está habilitada.
- A tradução da transcrição da caixa postal está habilitada.
- O mascaramento de profanidade de transcrição de caixa postal está desabilitado.
- A duração máxima da gravação é definida como cinco minutos.
- A edição de regras de atendimento a chamadas está habilitada.
- Os idiomas de prompt do sistema primário e secundário são definidos como nulos e a configuração de idioma da caixa postal do usuário é usada.

Você pode usar a política global (padrão de toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

## <a name="create-a-custom-voicemail-policy"></a>Criar uma política de caixa postal personalizada

Siga estas etapas para criar uma política de caixa postal personalizada.

1. No painel de navegação à esquerda do Microsoft Teams de administração, vá para políticas **do VoiceVoicemail** > .
2. Selecione **Adicionar**.
3. Ative ou desative os recursos que você deseja usar em sua política de caixa postal.
4. Selecione **Salvar**.

## <a name="edit-a-voicemail-policy"></a>Editar uma política de caixa postal

Siga estas etapas para editar uma política de caixa postal existente.

1. No painel de navegação esquerdo do Microsoft Teams de administração, selecione **políticas** **do VoiceVoicemail** > .
2. Clique ao lado da política que você deseja modificar e selecione **Editar**.
3. Faça as alterações desejadas e clique em **Salvar**.

> [!IMPORTANT]
> Você não pode editar ou remover as instâncias de política pré-configuradas chamadas TranscriptionDisabled e TranscriptionProfanityMaskingEnabled.


## <a name="assign-a-custom-voicemail-policy-to-users"></a>Atribuir uma política de caixa postal personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>Configurações de política de caixa postal
  
### <a name="enable-transcription"></a>Habilitar transcrição

Essa configuração controla se o serviço Caixa postal na Nuvem gerará uma transcipação de texto da caixa postal gravada e a incluirá na mensagem de voz. A transcrição será feita com base no idioma detectado na caixa postal gravada.

### <a name="transcription-translation"></a>Tradução de transcrição

Essa configuração controla se o serviço Caixa postal na Nuvem traduzirá a transcrição da caixa postal gravada. A tradução será tentada no idioma preferencial do receptor da caixa postal.

### <a name="transcription-profanity-masking"></a>Mascaramento de profanidade de transcrição

Essa configuração controla se o serviço Caixa postal na Nuvem mascarará as profanidades encontradas na transcrição da caixa postal.

### <a name="maximum-recording-duration"></a>Duração máxima da gravação

O comprimento máximo da gravação controla o tempo máximo em que uma caixa postal pode ser registrada. O padrão é 5 minutos.

### <a name="call-answering-rules"></a>Regras de atendimento de chamadas

Essa configuração controla se o usuário tem permissão para configurar regras de atendimento de chamadas de caixa postal Microsoft Teams.

### <a name="dual-language-system-prompts"></a>Prompts do sistema de linguagem dupla

Por padrão, os prompts do sistema de caixa postal são apresentados aos chamadores no idioma selecionado pelo usuário ao configurar sua caixa postal. Se houver um requisito de negócios para que os prompts do sistema de caixa postal sejam apresentados em dois idiomas, um idioma primário e secundário poderá ser definido e eles poderão não ser os mesmos.

### <a name="share-data-for-service-improvements"></a>Compartilhar dados para melhorias de serviço

Especifica se os dados de caixa postal e transcrição são compartilhados com o serviço para treinamento e melhoria da precisão. Se definido como false, os dados da caixa postal não serão compartilhados, independentemente da escolha do usuário.


> [!IMPORTANT]
> O serviço de caixa postal Microsoft 365 e Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 6 horas. Portanto, as alterações de política feitas podem levar até 6 horas para serem aplicadas.

## <a name="related-articles"></a>Artigos relacionados

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
