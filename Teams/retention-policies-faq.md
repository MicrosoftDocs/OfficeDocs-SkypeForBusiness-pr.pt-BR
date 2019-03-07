---
title: Perguntas frequentes sobre as políticas de retenção Teams da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Perguntas frequentes sobre políticas de retenção no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7597565afcd63872554e867d8f68929a3e214538
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461016"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Perguntas frequentes sobre as políticas de retenção Teams da Microsoft

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Quais tipos de políticas podem configurar o nas políticas de retenção e como elas funcionam?

No Centro de conformidade de segurança &, quando você configurar uma política de retenção, para equipes ou para qualquer outra carga de trabalho, você pode configurar dois tipos principais de políticas: 
- Preservação: Essas políticas garantir que seus dados seja preservados para um determinado período de tempo, não importa o que acontece nas ferramentas do usuário final. Eles garantem que dados são preservados por motivos de conformidade e expira disponíveis no eDiscovery até neste momento. Após o tempo de expiração, sua política pode indicar se deseja fazer nada ou excluir os dados. Em equipes, se você criar uma política de preservação para 7 anos, mesmo se os usuários finais excluir suas mensagens de equipes, essas mensagens são preservadas para descoberta eletrônica por 7 anos.
- Exclusão: Essas políticas garantem que os dados não são um risco para sua organização. Após o período especificado, os dados são excluídos do todo o armazenamento em equipes relevante. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Podemos incluir equipes em políticas de toda a organização? 

Não, não no momento. Você deve criar políticas específicas para mensagens de chat e canal de equipes usando a linha de local de equipes ou esses cmdlets equipes: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Esses cmdlets ter get e definir as versões também.

### <a name="are-these-retention-policies-retroactive"></a>Essas políticas de retenção são retroativas? 

Sim, eles são. Se você criar uma política de retenção para excluir os dados mais antigos do que 60 dias, ele excluirá dados de equipes criados há mais de 60 dias. 

### <a name="what-is-the-default-retention-policy"></a>Qual é a política de retenção padrão? 

Por padrão, o bate-papo equipes, de canal e dados de arquivos são mantidos indefinidamente. Um usuário pode excluir alguma coisa, mas na ausência de políticas de retenção, dados de equipes sempre serão arquivados no Exchange online mailboxes. (de usuário e de grupo) em permanecem lá para descoberta eletrônica. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Conjuntos de usuários ou equipes em uma política pode direcionar? 

Sim, você deve fazer. No Assistente de criação de política, na etapa locais, pode incluir ou excluir usuários (**chat equipes**) ou equipes (**mensagens de canal de equipes**) e criar políticas de destino para a sua organização. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>O que é a principal diferença entre usando a linha do local de caixa de correio de grupo e a linha de local de mensagens de canal de equipes em políticas de retenção? 

Se você usar a caixa de correio de grupo e linhas de local de caixa de correio do usuário para o Exchange Online, equipes de dados serão excluídas das caixas de correio especificadas. No entanto, isso só remove dados da caixa de correio. Ela não exclui os outros dados de equipes, como o serviço de bate-papos. É recomendável usar políticas de retenção de equipes para gerenciar todos os dados de equipes de forma adequada. Uma política de retenção de equipes remove dados de equipes de todos os armazenamento locais – caixas de correio, serviço de Chat, os clientes de equipes. 

Observação: O início do recurso de políticas de retenção para equipes certifica-se de que apenas as políticas de equipes excluir itens de equipes armazenados em locais de caixa de correio do Exchange (usuário ou grupo). A instalação de outras políticas em caixas de correio não pode afetar a itens de equipes. Isso era true no passado, mas foi corrigido com o lançamento do recurso de políticas de retenção. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>O que acontece com Skype para chats de interoperabilidade Business Online e equipes – eles são afetados pelas políticas de retenção?

Sim, Skype para Business Online e chats de interoperabilidade de equipes funciona da mesma maneira. Depois que o Skype para chat Business Online entra em equipes, ela se torna uma mensagem em um segmento de bate-papo de equipes e obtém incluída em uma caixa de correio apropriada. Para que o mesmo fluxo works – políticas de exclusão de equipes excluirá essas mensagens do thread equipes. No entanto, se o histórico da conversa está ativado para Skype para Business Online e do Skype para Business Online lado do cliente aqueles estão sendo salvos em uma caixa de correio, esses dados de chat não são tratados por uma política de retenção de equipes.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Posso fazer essas por meio de segurança & cmdlets do Centro de conformidade? O que devo usar? 

Absolutamente. Você pode criar políticas de retenção de equipes usando [cmdlets do Powershell do Centro de conformidade de & de segurança]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Lembre-se de que não estão cmdlets do Exchange Online. Aqui estão os cmdlets que criamos para equipes. Eles siga o estilo e a nomenclatura existente da retenção cmdlets disponíveis no Centro de conformidade de & de segurança.

|Política|Regra|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Se houver várias políticas de retenção para equipes variadas durações, qual delas wins?

Podemos seguem [princípios das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)e recomendamos que você faça muito. A resposta curta é: 
-   Preservação sempre supera exclusão
-   Maior período de preservação sempre wins
-   Inclusão explícita supera implícita inclusão em termos de locais
-   Mais curta wins período de exclusão
