---
title: Políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Saiba como as políticas de retenção e como gerenciá-las no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f2f3cc0c74b85d0b243dd8fefcd6bce1f2451fae
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018807"
---
# <a name="retention-policies-in-microsoft-teams"></a>Políticas de retenção no Microsoft Teams

As conversas de equipes são persistentes e mantidas para sempre por padrão. Com a introdução de políticas de retenção, os administradores podem configurar as políticas de retenção (preservação e exclusão) no centro de conformidade do & de segurança para mensagens de chat e de canal de equipe. Isso ajuda as organizações a reter dados para conformidade (especificamente, política de preservação) para um período específico ou livrar-se de dados (ou seja, política de exclusão) se for considerado um passivo após um período específico. As políticas de retenção de equipe garantem que, quando você exclui dados, ele é removido de todos os locais de armazenamento de dados permanentes do serviço Teams. 

Para gerenciar as políticas de retenção do Teams, use as configurações e cmdlets no centro de conformidade do Office 365 Security & em**retenção**de **governança** > de dados.

As políticas de retenção de equipes oferecem suporte: 
    
- Preservação: manter os dados do teams por uma duração especificada e, em seguida, não fazer nada
- Preservação e excluir: manter os dados do teams por uma duração especificada e excluir
- Exclusão: excluir dados de equipes após uma duração especificada

As políticas de retenção do teams ainda não dão suporte:

- Políticas avançadas de retenção não se aplicam a locais de mensagens de canal de chat e equipe do teams
- Duração de menos de 30 dias

Os administradores podem configurar políticas de retenção separadas para chats privados do Teams (1:1 ou 1: muitos chats) e mensagens de canal de equipe. Em muitos casos, as organizações consideram dados de chat privados como uma obrigação mais passiva do que as mensagens de canal, que normalmente são mais conversas relacionadas ao projeto. Configure essas políticas no centro de conformidade & segurança,**retenção**de **governança** > de dados. Ative mensagens de canal e **chats de equipe** do **Teams** e, em seguida, defina as políticas de retenção para esses locais (também mostrado no diagrama abaixo). 

Ao ativar **as mensagens de canal do teams**, você pode especificar as equipes às quais essa política será aplicada. Por exemplo, para Teams X, Y e Z, o administrador pode definir as políticas de exclusão para 1 ano (selecionando essas equipes individualmente) e aplicar uma política de exclusão de 3 anos ao restante das equipes. 

Você pode fazer o mesmo para **chats de equipe** selecionando usuários específicos e aplicando políticas exclusivas de retenção. 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Os locais de mensagens de canal de equipe e os chats de equipe só abordam as conversas de equipe armazenadas nas caixas de correio do Exchange Online (caixas de correio de grupo e de usuário). As mensagens são excluídas de todos os locais de armazenamento pertinentes, ou seja, as caixas de correio, substrato e serviço de chat. 
> 
> Para gerenciar políticas de retenção para arquivos do Teams, que são armazenados no OneDrive for Business e no SharePoint, use as políticas de retenção.

Por design, as políticas de exclusão para arquivos do teams são configuradas por locais do SharePoint Online e do OneDrive for Business. Como resultado, é possível que uma política possa excluir um arquivo referenciado em uma mensagem de chat ou um canal de equipe antes de as mensagens serem excluídas. Nesse caso, o arquivo ainda será exibido na mensagem do Teams, mas, se você clicar no arquivo, receberá um erro "arquivo não encontrado" (isso também pode acontecer na ausência de uma política, se alguém excluir manualmente um arquivo do SharePoint Online ou do OneDrive for Business).

Para obter informações detalhadas sobre a configuração de políticas de retenção do Office 365, leia [visão geral das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
