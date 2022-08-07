---
title: Gerenciar Políticas de Caixa Postal
author: crowe
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
ms.openlocfilehash: da5909a1d460373be60bf26de08e414ca6470c8a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267746"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>Gerenciar Caixa postal na Nuvem para seus usuários

> [!WARNING]
> Para Skype for Business clientes, desabilitar a caixa postal por meio de uma política de chamada do Microsoft Teams também pode desabilitar o serviço de caixa postal para Skype for Business usuários.

As políticas de caixa postal permitem que você configure e atribua políticas de caixa postal novas ou existentes a grupos de usuários para recursos como regras de atendimento de chamadas, transcrição de caixa postal, mascaramento de profanidade de transcrição, tradução de transcrição e idioma de prompt do sistema.

Antes de especificar políticas, você deve ler [Configurar Caixa postal na Nuvem](set-up-phone-system-voicemail.md). Para obter informações sobre como gerenciar configurações para usuários [individuais, consulte Gerenciar definições de caixa postal](manage-voicemail-settings.md).

Para gerenciar políticas de caixa postal, você pode usar o centro de administração do Teams ou o cmdlet New-CsOnlineVoicemailPolicy PowerShell. 

As políticas padrão para os usuários são:

- A transcrição da caixa postal está habilitada.
- A tradução da transcrição da caixa postal está habilitada.
- O mascaramento de profanidade de transcrição de caixa postal está desabilitado.
- A duração máxima da gravação é definida como cinco minutos.
- A edição de regras de atendimento a chamadas está habilitada.
- Os idiomas de prompt do sistema primário e secundário são definidos como nulos e a configuração de idioma da caixa postal do usuário é usada.

Você pode usar a política global (padrão de toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

> [!IMPORTANT]
> O serviço de caixa postal no Microsoft 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 6 horas. Portanto, as alterações de política feitas podem levar até 6 horas para serem aplicadas.

## <a name="use-teams-admin-center"></a>Usar o Centro de administração do Teams

### <a name="create-a-custom-voicemail-policy"></a>Criar uma política de caixa postal personalizada

Siga estas etapas para criar uma política de caixa postal personalizada.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para políticas **de Caixa Postal** > **de Voz**.

2. Selecione **Adicionar**.

3. Ative ou desative os recursos que você deseja usar em sua política de caixa postal.

4. Selecione **Salvar**.

### <a name="edit-a-voicemail-policy"></a>Editar uma política de caixa postal

Siga estas etapas para editar uma política de caixa postal existente.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, selecione políticas **de Caixa Postal** > **de Voz**.

2. Clique ao lado da política que você deseja modificar e selecione **Editar**.

3. Faça as alterações desejadas e clique em **Salvar**.

> [!IMPORTANT]
> Você não pode editar ou remover as instâncias de política pré-configuradas chamadas TranscriptionDisabled e TranscriptionProfanityMaskingEnabled.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>Atribuir uma política de caixa postal personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>Usar o PowerShell

Você também pode usar o PowerShell para configurar e atribuir políticas de caixa postal novas ou existentes. Para gerenciar políticas usando o PowerShell, use os seguintes cmdlets:

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>Configurações de política de caixa postal
  
- **Habilitar** transcrição – essa configuração controla se o serviço Caixa postal na Nuvem gerará uma transcipação de texto da caixa postal gravada e a incluirá na mensagem de voz. A transcrição será feita com base no idioma detectado na caixa postal gravada.

- **Tradução de transcrição** – essa configuração controla se o serviço Caixa postal na Nuvem traduzirá a transcrição da caixa postal gravada. A tradução será tentada no idioma preferencial do receptor da caixa postal.

- **Mascaramento de profanidade de** transcrição – Essa configuração controla se o serviço Caixa postal na Nuvem mascarará o profanidade encontrado na transcrição da caixa postal.

- **Duração máxima da gravação** - O comprimento máximo de gravação controla o tempo máximo que uma caixa postal pode ser registrada. O padrão é 5 minutos.

- **Regras de atendimento de chamadas** – essa configuração controla se o usuário tem permissão para configurar regras de atendimento de chamadas de caixa postal no Microsoft Teams.

- **Prompts do sistema de idiomas duplos** – por padrão, os prompts do sistema de caixa postal são apresentados aos chamadores no idioma selecionado pelo usuário ao configurar sua caixa postal. Se houver um requisito de negócios para que os prompts do sistema de caixa postal sejam apresentados em dois idiomas, um idioma primário e secundário poderá ser definido e eles poderão não ser os mesmos.

### <a name="share-data-for-service-improvements"></a>Compartilhar dados para melhorias de serviço

Especifica se os dados de caixa postal e transcrição são compartilhados com o serviço para treinamento e melhoria da precisão. Se definido como false, os dados da caixa postal não serão compartilhados, independentemente da escolha do usuário.


## <a name="related-articles"></a>Artigos relacionados


