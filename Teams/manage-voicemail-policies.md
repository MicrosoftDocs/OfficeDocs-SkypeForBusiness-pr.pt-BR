---
title: Gerenciar políticas de caixa postal
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
ms.openlocfilehash: 02df2f235512ce0aca658031fae000edc99b5ea9
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851812"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>Gerenciar políticas de Caixa postal na Nuvem para seus usuários

> [!WARNING]
> Para clientes Skype for Business, desabilitar a caixa postal por meio de uma política de chamada do Microsoft Teams também pode desabilitar o serviço de caixa postal para seus usuários Skype for Business.

As políticas de caixa postal permitem configurar e atribuir políticas de caixa postal existentes ou novas a grupos de usuários para recursos como regras de resposta de chamada, transcrição de caixa postal, mascaramento de palavrões de transcrição, tradução de transcrição e linguagem prompt do sistema.

Antes de especificar políticas, você deve ler [Configurar Caixa postal na Nuvem](set-up-phone-system-voicemail.md). Para obter informações sobre como gerenciar configurações para usuários individuais, consulte [Gerenciar setltings do Voicemail](manage-voicemail-settings.md).

Para gerenciar políticas de caixa postal, você pode usar o centro de administração do Teams ou o cmdlet New-CsOnlineVoicemailPolicy PowerShell. 

As polícias padrão para usuários são:

- A transcrição de caixa postal está habilitada.
- A tradução de transcrição de caixa postal está habilitada.
- O mascaramento de palavrões de transcrição de caixa postal está desabilitado.
- A duração máxima da gravação é definida como cinco minutos.
- A edição de regras de resposta de chamada está habilitada.
- Os idiomas de prompt do sistema primário e secundário são definidos como nulos e a configuração de linguagem de caixa postal do usuário é usada.
- Nenhum pré ou postamble configurado.

Você pode usar a política global (padrão em toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

> [!IMPORTANT]
> O serviço de caixa postal no Microsoft 365 armazena em cache políticas de caixa postal e atualiza o cache a cada 6 horas. Portanto, as alterações de política que você faz podem levar até 6 horas para serem aplicadas.

## <a name="use-teams-admin-center"></a>Usar o centro de administração do Teams

### <a name="create-a-custom-voicemail-policy"></a>Criar uma política de caixa postal personalizada

Siga estas etapas para criar uma política de caixa postal personalizada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **políticas** do **VoiceMail** > .

2. Selecione **Adicionar**.

3. Ative ou desative os recursos que você deseja usar em sua política de caixa postal.

4. Selecione **Salvar**.

### <a name="edit-a-voicemail-policy"></a>Editar uma política de caixa postal

Siga estas etapas para editar uma política de caixa postal existente.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Políticas** do **Voicemail** > .

2. Clique ao lado da política que você deseja modificar e selecione **Editar**.

3. Faça as alterações desejadas e clique em **Salvar**.

> [!IMPORTANT]
> Você não pode editar ou remover as instâncias de política pré-configuradas chamadas TranscriptionDisabled e TranscriptionProfanityMaskingEnabled.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>Atribuir uma política de caixa postal personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>Usar o PowerShell

Você também pode usar o PowerShell para configurar e atribuir políticas de caixa postal existentes ou novas. Para gerenciar políticas usando o PowerShell, use os seguintes cmdlets:

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>Configurações de política de caixa postal
  
- **Habilitar a transcrição** – essa configuração controla se o serviço Caixa postal na Nuvem gerará uma transcipção de texto da caixa postal gravada e a incluirá na mensagem de caixa postal. A transcrição será feita com base na linguagem detectada na caixa postal gravada.

- **Tradução de transcrição** – Essa configuração controla se o serviço Caixa postal na Nuvem traduzirá a transcrição da caixa postal gravada. A tradução será tentada no idioma preferencial do receptor de caixa postal.

- **Mascaramento de palavrões de transcrição** – essa configuração controla se o serviço de Caixa postal na Nuvem mascarará a profanação encontrada na transcrição da caixa postal.

- **Duração máxima da gravação** – o comprimento máximo da gravação controla o tempo máximo em que uma caixa postal pode ser gravada. O padrão é 5 minutos.

- **Regras de resposta de** chamada – essa configuração controla se o usuário tem permissão para configurar regras de resposta de chamada de caixa postal no Microsoft Teams.

- **Prompts de sistema de idioma duplo** – por padrão, os prompts do sistema de caixa postal são apresentados aos chamadores no idioma selecionado pelo usuário ao configurar sua caixa postal. Se houver um requisito comercial para que os prompts do sistema de caixa postal sejam apresentados em dois idiomas, um idioma primário e secundário poderá ser definido e eles podem não ser os mesmos.

- **PreambleAudioFile** – atualmente disponível apenas por meio do PowerShell. O arquivo de áudio a ser reproduzido para o chamador antes que a saudação da caixa postal do usuário seja reproduzida.

- **PostambleAudioFile** – Atualmente disponível apenas por meio do PowerShell. O arquivo de áudio a ser reproduzido para o chamador depois que a saudação da caixa postal do usuário tiver sido reproduzida e antes que o chamador possa deixar uma mensagem de caixa postal.

- **PreamblePostambleMandatory** – atualmente disponível apenas por meio do PowerShell. Está tocando o Pré ou Postamble obrigatório antes que o chamador possa deixar uma mensagem.

### <a name="share-data-for-service-improvements"></a>Compartilhar dados para melhorias de serviço

Especifica se os dados de caixa postal e transcrição são compartilhados com o serviço para treinamento e melhoria da precisão. Se definido como false, os dados de caixa postal não serão compartilhados, independentemente da escolha do usuário.


## <a name="related-articles"></a>Artigos relacionados


