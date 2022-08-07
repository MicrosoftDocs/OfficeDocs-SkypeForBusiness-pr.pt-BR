---
title: Gerenciar Caixa postal na Nuvem configurações
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
description: Gerencie as configurações de Caixa Postal para seus usuários.
ms.openlocfilehash: 7aa2fdf84f38cb9977b3a4156b28a96b98bbd9d7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269596"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>Gerenciar Caixa postal na Nuvem configurações para usuários

As configurações de caixa postal permitem definir configurações de caixa postal para usuários individuais.

Antes de definir as configurações de caixa postal para seus usuários, você deve ler [Configurar Caixa postal na Nuvem](set-up-phone-system-voicemail.md). Para obter informações sobre como definir políticas para grupos de usuários, consulte [Gerenciar políticas de caixa postal](manage-voicemail-policies.md).

As configurações padrão para Caixa postal na Nuvem são:

- A caixa postal está habilitada.
- O idioma do prompt é definido como o idioma preferencial do usuário.
- A saudação de ausência temporária está desabilitada.
- A saudação de ausência temporária, quando as respostas automáticas são definidas no Outlook, é desabilitada.
- A saudação de ausência temporária, quando o calendário no Outlook mostra ausência temporária, está desabilitada.
- O compartilhamento de dados de caixa postal e transcrição com o serviço para treinamento e aprimoramento de finalidades de precisão está desabilitado.
- A regra de atendimento de chamadas é definida como Caixa Postal Regular.
- A substituição do prompt de saudação padrão não está definida.
- A substituição padrão do prompt de saudação de ausência temporária não está definida.
- O destino de transferência não está definido.


Para gerenciar Caixa postal na Nuvem recursos para seus usuários, você pode usar o Centro de administração do Teams ou o PowerShell. Observe que os usuários finais também podem definir essas configurações no cliente do Teams acessando Configurações **-> Chamadas -> Caixa Postal.**

## <a name="use-teams-admin-center"></a>Usar o Centro de administração do Teams

No centro de administração do Teams:

1.  No painel de navegação esquerdo, vá para **Usuários > Gerenciar usuários** e selecione o usuário.

2.  Na página de detalhes do usuário, vá para a guia Caixa **Postal** .

3.  Altere as configurações.

4.  Selecione **Salvar**.


## <a name="use-powershell"></a>Usar o PowerShell

Você também pode usar o PowerShell para gerenciar as configurações de caixa postal da seguinte maneira:

- Para gerenciar Caixa postal na Nuvem configurações para usuários individuais, use o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). 

- Para exibir as configurações, use o cmdlet [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) .

- Você pode desabilitar Caixa postal na Nuvem para um usuário usando o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) e definindo o parâmetro VoicemailEnabled como $false. 

## <a name="voicemail-settings"></a>Configurações de caixa postal

- **Caixa postal habilitada** – essa configuração controla se Caixa postal na Nuvem está habilitado para o usuário. Se as configurações forem falsas, Caixa postal na Nuvem serviço não estará disponível para o usuário e não gravará uma caixa postal para o usuário.

- **Idioma do** prompt – essa configuração especifica o idioma usado para os prompts no Caixa postal na Nuvem. Para obter mais informações, [consulte Alterar o idioma padrão para saudações e emails](change-the-default-language-for-greetings-and-emails.md).

- **Configurações de** saudação - Caixa postal na Nuvem é capaz de reproduzir uma saudação específica para quando o usuário está no escritório e para quando o usuário está fora do escritório. Ambas as saudações podem ser gravadas pelo usuário ou uma saudação de conversão de texto em fala pode ser usada.

  - **Substituição de Prompt de** Saudação Padrão – especifica a saudação de conversão de texto em fala que será reproduzida caso o usuário não tenha registrado uma saudação.

  - **Saudação OOF Habilitada** – especifica se a saudação de ausência temporária é tocada no cenário de depósito de caixa postal, independentemente das configurações do Outlook.

  - **Saudação Oof Siga** Respostas Automáticas Habilitadas – especifica se a saudação de ausência temporária deve ser executada no cenário de depósito de caixa postal quando o usuário define respostas automáticas no Outlook.

  - **Oof Greeting Follow Calendar Enabled** - especifica se a saudação de ausência temporária deve ser executada no cenário de depósito de caixa postal quando o usuário definir ausência temporária no calendário.

  - Substituição padrão do prompt de saudação de **Oof** – especifica a saudação de conversão de texto em fala que será reproduzida caso o usuário esteja fora do escritório e não tenha registrado uma saudação de ausência temporária.

- **Regra de atendimento de chamadas** – essa configuração especifica a regra de atendimento de chamadas. A regra pode ser:
  - O serviço recusa a chamada sem nenhuma mensagem.
  - Somente a saudação relevante (normal ou ausência temporária) é tocada.
  - A saudação relevante (normal ou ausência temporária) é tocada e o chamador é transferido para o usuário ou número de telefone especificado.
  -  A saudação relevante (normal ou ausência temporária) é tocada e o chamador pode deixar uma caixa postal.
  - A saudação relevante (normal ou ausência temporária) é executada, o chamador pode deixar uma caixa postal e tem permissão para pressionar 0 para ser transferido para o usuário ou número de telefone especificado.

- **Compartilhar dados para melhorias de** serviço – Especifica se os dados de caixa postal e transcrição são compartilhados com o serviço para treinamento e melhoria da precisão. Se definido como false, os dados da caixa postal não serão compartilhados, independentemente da escolha do usuário.

- **Transferência de** chamada - Especifica o usuário ou número de telefone para o qual o chamador é transferido.


