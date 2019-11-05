---
title: 'Perguntas frequentes sobre diretivas de retenção do Teams '
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Perguntas frequentes sobre políticas de retenção no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b3d2ed05459c6866c73b0f49b128eea3980605f
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968302"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Perguntas frequentes sobre diretivas de retenção do Teams 

> [!NOTE]
> Ainda não damos suporte à configuração para a retenção de mensagens de canal privado. A retenção de arquivos compartilhados em canais privados tem suporte.

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Que tipos de diretivas eu posso configurar nas políticas de retenção e como elas funcionam?

No centro de conformidade do & de segurança, ao configurar uma política de retenção, para equipes ou para qualquer outra carga de trabalho, você pode configurar dois tipos principais de políticas: 
- Preservação: essas políticas garantem que seus dados sejam preservados por um determinado período de tempo, não importa o que aconteça nas ferramentas de usuário final. Elas garantem que os dados sejam preservados por motivos de conformidade e disponíveis na descoberta eletrônica até que este período expire. Após o vencimento do tempo, a política pode indicar se deseja fazer nada ou excluir os dados. No Teams, se você criar uma política de preservação por 7 anos, mesmo se os usuários finais excluirem suas mensagens de equipe, essas mensagens ainda serão preservadas para a descoberta eletrônica por 7 anos.
- Exclusão: essas políticas garantem que os dados não sejam um passivo para a sua organização. Após a duração especificada, os dados são excluídos de todo o armazenamento relevante no Microsoft Teams. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Podemos incluir equipes em políticas de toda a organização? 

Não, não no momento. Você deve criar políticas específicas para mensagens de chat e de canal de equipe usando a linha de local do teams ou os seguintes cmdlets do teams: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Esses cmdlets também têm versões Get e Set.

### <a name="are-these-retention-policies-retroactive"></a>Estas são as políticas de retenção retroativas? 

Sim, eles estão. Se você criar uma política de retenção para excluir dados com mais de 60 dias, ele excluirá os dados de equipe criados há mais de 60 dias. 

### <a name="what-is-the-default-retention-policy"></a>O que é a política de retenção padrão? 

Por padrão, os dados de chat, canal e arquivos de equipe são mantidos para sempre.

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Posso direcionar conjuntos de usuários ou equipes em uma política? 

Sim, você faz. No Assistente para criação de política, na etapa locais, você pode incluir ou excluir equipes (**mensagens de canal de equipe**) ou usuários (**chat de equipe**) e criar políticas direcionadas para sua organização. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Qual é a principal diferença entre usar a linha de local da caixa de correio de grupo e o local das mensagens de canal de equipe nas políticas de retenção? 

Se você usar a caixa de correio do grupo e as linhas de local da caixa de correio do usuário para o Exchange Online, os dados do teams serão excluídos das caixas de correio especificadas. No entanto, isso remove apenas os dados da caixa de correio. Ele não exclui outros dados do Teams, como o serviço de chats. Recomendamos que você use as políticas de retenção de equipe para gerenciar corretamente todos os dados do teams. Uma política de retenção do teams remove dados do teams de todos os locais de armazenamento – caixas de correio, serviço de chat, clientes do teams. 

Observação: o lançamento do recurso de políticas de retenção para o Teams garante que apenas as políticas de equipe excluam itens de equipes armazenados dentro dos locais da caixa de correio do Exchange (usuário ou grupo). A configuração de outras políticas nas caixas de correio não pode afetar itens do teams. Isso era verdade no passado, mas foi corrigido com o recurso inicialização do recurso de políticas de retenção. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>O que acontece com os chats do Skype for Business Online e do Team Interop – eles são afetados pelas políticas de retenção?

Sim, os chats do Skype for Business Online e do Team Interop funcionam da mesma maneira. Depois que o chat do Skype for Business online chega ao Teams, ele se torna uma mensagem em um thread de chat do Teams e fica ingerido na caixa de correio apropriada. Portanto, o mesmo fluxo funciona – as políticas de exclusão das equipes excluirão essas mensagens do thread do teams. No entanto, se o histórico da conversa estiver ativado para o Skype for Business Online e do lado do cliente do Skype for Business Online, eles serão salvos em uma caixa de correio, esses dados de chat não são manipulados por uma política de retenção de equipe.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Posso fazer isso por meio de cmdlets de segurança & centro de conformidade? O que devo usar? 

Totalmente. Você pode criar políticas de retenção de equipes usando [cmdlets do PowerShell do centro de conformidade do & central de segurança]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Lembre-se de que não são cmdlets do Exchange Online. Estes são os cmdlets que criamos para o Teams. Eles seguem Nomenclature e estilos existentes dos cmdlets de retenção disponíveis hoje em centro de conformidade & segurança.

|Regras|Das|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Se houver várias políticas de retenção para equipes com durações variáveis, um WINS?

Seguimos [princípios de políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)e recomendamos que você também o faça. A resposta curta é: 
-   Preservação sempre ganha a exclusão
-   Período de preservação mais longo sempre vence
-   Inclusão explícita WINS em relação à inclusão implícita em termos de locais
-   Período de exclusão mais curto vence
