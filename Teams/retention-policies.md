---
title: Políticas de retenção no Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Saiba mais sobre as políticas de retenção e como criá-las e gerenciá-las no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160745"
---
# <a name="retention-policies-in-microsoft-teams"></a>Políticas de retenção no Microsoft Teams

As políticas de retenção ajudam você a gerenciar com mais eficiência as informações em sua organização. Use as políticas de retenção para manter os dados necessários para cumprir as políticas internas, as normas do setor ou as necessidades legais da sua organização, e para excluir dados considerados passivos, que não são mais necessários ou que não têm valor legal ou comercial.

Por padrão, os dados de chat, canal e arquivos de equipe são mantidos para sempre. Como administrador, você pode configurar as políticas de retenção de equipes para mensagens de chat e de canal e decidir proativamente se deseja manter os dados, excluí-los ou mantê-los por um período específico de tempo e, em seguida, excluí-los.

Você cria e gerencia políticas de retenção para equipes e outras cargas de trabalho no [centro de conformidade do Office 365 security &](https://protection.office.com/) ou usando cmdlets do PowerShell do centro de conformidade do &. Você pode aplicar uma política de retenção de equipes a toda a sua organização ou a usuários e equipes específicas.

> [!NOTE]
> Ainda não damos suporte à configuração para a retenção de mensagens de canal privado. A retenção de arquivos compartilhados em canais privados tem suporte.

Para saber mais sobre as políticas de retenção do Office 365, consulte [visão geral de políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>O que são as políticas de retenção do teams?

Ao configurar uma política de retenção para equipes ou qualquer outra carga de trabalho, você pode configurá-la para:

- **Reter dados**: Use uma política de retenção para garantir que seus dados sejam retidos por um período de tempo especificado, independentemente do que acontece no aplicativo do usuário. Os dados são mantidos por motivos de conformidade e estão disponíveis para eDiscovery até o vencimento do período de retenção, após o qual a política indica se você quer fazer nada ou excluir os dados. Por exemplo, se você criar uma política de retenção do teams para reter mensagens de canal por 7 anos, as mensagens serão mantidas para descoberta eletrônica por 7 anos, mesmo que os usuários excluam suas mensagens no Teams.
- **Excluir dados**: Use uma política de retenção para excluir dados para garantir que não seja uma obrigação para a sua organização. Com uma política de retenção de equipes, quando você exclui dados, eles são excluídos permanentemente de todos os locais de armazenamento do serviço do teams.

Com as políticas de retenção do Teams, você pode:

- Guarde chats de equipe e/ou mensagens de canal por uma duração especificada e, em seguida, não faça nada.
- Manter chats de equipe e/ou mensagens de canal por uma duração especificada e excluir os dados.
- Excluir chats do Teams e/ou mensagens de canal após uma duração especificada.

> [!NOTE]
> Lembre-se de que, em equipes, os arquivos que os usuários compartilham em chats privados são armazenados na conta do OneDrive for Business do usuário que compartilhou o arquivo. E os arquivos que os membros da equipe carregam em uma conversa de canal são armazenados no site do SharePoint da equipe. Portanto, para reter ou excluir arquivos no Microsoft Teams, crie políticas de retenção que se aplicam ao OneDrive for Business e ao SharePoint Online.

Quando os dados estão sujeitos a uma política de retenção, os usuários podem continuar a trabalhar com ele porque os dados são mantidos no lugar, em seu local original. Se um usuário editar ou excluir dados que estão sujeitos à política, uma cópia será salva em um local seguro onde ele será mantido enquanto a política estiver em vigor.

O requisito mínimo de licenciamento para políticas de retenção é o Office 365 E3. Para saber mais sobre licenciamento, consulte [Licenciamento do Office 365 para Teams](Office-365-licensing.md).

## <a name="how-teams-retention-policies-work"></a>Como funcionam as políticas de retenção de equipe

Os chats de equipe são armazenados em uma pasta oculta do SubstrateHolds na caixa de correio de cada usuário no chat, e as mensagens de canal de equipe são armazenadas em uma pasta oculta SubstratesHolds na caixa de correio do grupo de uma equipe. O Microsoft Teams usa um serviço de chat do Azure que também armazena esses dados e, por padrão, esse serviço armazena os dados para sempre. Com uma política de retenção de equipes, quando você exclui dados, os dados são excluídos permanentemente das caixas de correio do Exchange e do serviço de chat subjacente.

Ao aplicar uma política de retenção a chats de equipe e mensagens de canal, veja o que acontece:

- Se uma mensagem de chat ou de canal for editada ou excluída por um usuário durante o período de retenção, a mensagem será copiada (se tiver sido editada) ou movida (se tiver sido excluída) para a pasta SubstrateHolds e armazenada até o período de retenção expirar. Se a política estiver configurada para excluir dados quando o período de retenção expirar, as mensagens serão excluídas permanentemente do dia em que o período de retenção expira.
- Se uma mensagem de chat ou de canal não for excluída por um usuário durante o período de retenção, a mensagem será movida para a pasta SubstrateHolds dentro de um dia após o vencimento do período de retenção. Se a política estiver configurada para excluir dados quando o período de retenção expirar, a mensagem será permanentemente excluída um dia após ser movida para a pasta.

> [!NOTE]
> O mesmo fluxo funciona para o Skype for Business Online e chats de interoperabilidade do teams. Quando um chat do Skype for Business online entra em equipe, ele se torna uma mensagem em um thread de chat do Teams e está incluído na caixa de correio apropriada. As políticas de retenção do teams excluirão essas mensagens do thread do teams. No entanto, se o histórico da conversa estiver ativado para o Skype for Business Online e do lado do cliente do Skype for Business Online, eles serão salvos em uma caixa de correio, e os dados de chat não são manipulados por uma política de retenção do teams.

As políticas de retenção no Teams são baseadas na data em que as mensagens de chat ou de canal foram criadas e são retroativas. Em outras palavras, se você criar uma política de retenção para excluir dados anteriores a 90 dias, os dados do teams criados há mais de 90 dias serão excluídos.

É possível que uma política de retenção aplicada ao SharePoint Online ou OneDrive for Business possa excluir um arquivo referenciado em uma mensagem de chat ou um canal de equipe antes que essas mensagens sejam excluídas. Nesse cenário, o arquivo ainda será exibido na mensagem do Teams, mas quando os usuários clicarem no arquivo, eles receberão o erro "arquivo não encontrado". Isso também pode acontecer na ausência de uma política, se alguém excluir manualmente um arquivo do SharePoint Online ou do OneDrive for Business.

### <a name="considerations-and-limitations"></a>Considerações e limitações

Veja algumas considerações e limitações a serem consideradas ao trabalhar com as políticas de retenção do teams:

- O Teams requer uma política de retenção separada de outras cargas de trabalho. Em outras palavras, você precisa criar políticas específicas de retenção para chats de equipe e/ou mensagens de canal. Por esse motivo, você não pode incluir equipes em políticas de retenção em toda a organização.

- Não há suporte para mensagens de canal privado. No momento, as políticas de retenção para Teams aplicam-se apenas às mensagens de canal padrão.

- O Microsoft Teams não oferece suporte a configurações avançadas de retenção, como a capacidade de aplicar uma política ao conteúdo que contém palavras-chave ou informações confidenciais. Atualmente, as políticas de retenção no Teams aplicam-se a todo o conteúdo de mensagens de chat e/ou canal.

- O Microsoft Teams pode levar até três dias para limpar mensagens expiradas. Uma política de retenção do teams excluirá mensagens de chat e de canal quando o período de retenção expirar. No entanto, pode levar até três dias para limpar essas mensagens e excluí-las permanentemente. Além disso, as mensagens de chat e de canal serão pesquisadas com ferramentas de descoberta eletrônica entre o tempo após o vencimento do período de retenção e quando as mensagens forem excluídas permanentemente.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Várias políticas de retenção e os princípios de retenção

Se você configurar várias políticas de retenção de equipes com durações variáveis, os [princípios das políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) se aplicam. Veja a seguir uma visão geral do que tem precedência:

- Preservação sempre ganha a exclusão
- Período de preservação mais longo sempre vence
- Inclusão explícita WINS em relação à inclusão implícita em termos de locais
- Período de exclusão mais curto vence

## <a name="when-to-use-retention-policies-for-teams"></a>Quando usar políticas de retenção para o Teams

Em muitos casos, as organizações consideram dados de chat privados como uma obrigação mais passiva do que as mensagens de canal, que normalmente são mais conversas relacionadas ao projeto.

Você pode configurar políticas de retenção separadas para chats privados (1:1 ou 1: muitos chats) e mensagens de canal. Você também pode configurar políticas exclusivas que se aplicam a usuários ou equipes específicas em sua organização. Para chats de equipe, você pode selecionar a quais usuários a política se aplica. Para mensagens de canal de equipe, você pode selecionar a quais equipes a política se aplica.

Por exemplo, para mensagens de canal, você pode aplicar uma política de exclusão de um ano a equipes específicas em sua organização e aplicar uma política de exclusão de três anos a todas as outras equipes.

## <a name="manage-retention-policies-for-teams"></a>Gerenciar políticas de retenção para equipes

### <a name="using-the-security--compliance-center"></a>Usar o centro de conformidade do & de segurança

#### <a name="create-a-retention-policy"></a>Criar uma política de retenção

Para criar uma política de retenção para chats e mensagens de canal do Teams, faça o seguinte:

1. Na navegação à esquerda do centro de conformidade do & de segurança, vá para**retenção**de **governança** > de informações.
2. Selecione **criar**.
3. Na página **nomear sua política** , insira um nome e uma descrição para a política e clique em **Avançar**.
4. Na página **configurações** , especifique se deseja manter os dados, excluí-los ou ambos, o período de retenção e clique em **Avançar**.
5. Na página **escolher locais** , faça o seguinte e clique em **Avançar**:

    - Para aplicar a política às mensagens de canal, ative **as mensagens de canal do teams**.  Se você quiser aplicar a política a equipes específicas em sua organização, selecione **escolher equipes**e, em seguida, selecione as equipes desejadas.
    - Para aplicar a política a chats, ative os **chats de equipe**. Se você quiser aplicar a política a usuários específicos em sua organização, selecione **escolher usuários**e, em seguida, selecione os usuários que você deseja.
      > [!NOTE]
      > Quando você ativa **as mensagens de canal de equipe** e/ou chats de **equipe**, todos os outros locais são desativados automaticamente. Uma política de retenção de equipes pode incluir apenas locais de equipes.

        ![Captura de tela das opções de mensagens de canal de equipe e chats de equipe na página escolher locais](media/retention-policies-create.png)

      > [!IMPORTANT]
      > As mensagens de chat e de canal não são afetadas pelas políticas de retenção aplicadas a caixas de correio de usuários ou grupos nos locais **email do Exchange** ou **grupos do Office 365** . Mesmo que os chats da equipe e as mensagens de canal sejam armazenados no Exchange, eles são afetados apenas pelas políticas de retenção aplicadas aos locais do teams.

6. Revise suas configurações e, quando estiver pronto, selecione **criar esta política**.

#### <a name="edit-a-retention-policy"></a>Editar uma política de retenção

Para editar uma política de retenção do Teams, faça o seguinte:

1. Na navegação à esquerda do centro de conformidade do & de segurança, vá para**retenção**de **governança** > de informações.
2. Na lista de políticas de retenção, marque a caixa de seleção ao lado da política de retenção que você deseja editar.
3. Selecione **Editar** ao lado do que você deseja editar, faça as alterações, clique em **salvar**e, em seguida, clique em **Fechar**.

    ![Captura de tela das opções de mensagens de canal de equipe e chats de equipe na página escolher locais](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>Excluir uma política de retenção

Para excluir uma política de retenção do Teams, faça o seguinte:

1. Na navegação à esquerda do centro de conformidade do & de segurança, vá para**retenção**de **governança** > de informações.
2. Na lista de políticas de retenção, marque a caixa de seleção ao lado da política de retenção que você deseja excluir.
3. Selecione **excluir política**.

### <a name="using-powershell"></a>Usando o PowerShell

Para criar e gerenciar as políticas de retenção de equipes usando o PowerShell, use os cmdlets a seguir.

|Regras|Das|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problemas conhecidos

Veja a seguir problemas conhecidos de políticas de retenção no Teams que estão sendo controladas e investigadas.

- Em **escolher equipes** na linha de localização de **mensagens de canal do teams** , você pode ver os grupos do Office 365 que não são equipes também. Isso será abordado no futuro.

- Em **escolher usuários** na linha de localização de **chats do teams** , você pode ver convidados e usuários que não são usuários da caixa de correio. As políticas de retenção não devem ser definidas para convidados e estamos trabalhando para removê-las da lista.

- O assistente de ciclo de vida do Exchange (ELC) é executado diariamente, mas tem um SLA de 7 dias. Como resultado, é possível que, se você tiver uma política de retenção do teams para excluir itens com mais de 60 dias, esses itens possam persistir por até 67 dias. Essa não é uma nova situação-ela segue o modelo do Exchange. É claro que, na maioria dos casos, não há atraso.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
