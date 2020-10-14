---
title: Grupos do Microsoft 365 e o Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Saiba como os grupos do Microsoft 365 e as associações de grupo funcionam com o Microsoft Teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456075"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Grupos do Microsoft 365 e o Microsoft Teams

O Microsoft 365 groups é o serviço de associação entre aplicativos no Microsoft 365. Em um nível básico, um grupo do Microsoft 365 é um objeto do Azure Active Directory com uma lista de membros e um acoplamento para cargas de trabalho relacionadas, incluindo um site de equipe do SharePoint, uma caixa de correio do Exchange compartilhada, o Planner e o espaço de trabalho do Power BI. Você pode adicionar ou remover pessoas para o grupo da mesma forma que faria com qualquer outro objeto de segurança baseado em grupo no Active Directory.

![Diagrama mostrando os grupos do Microsoft 365 e os serviços relacionados](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Por padrão, os usuários do Microsoft 365 podem criar e gerenciar grupos. Para obter mais informações sobre os grupos do Microsoft 365, consulte [saiba mais sobre os grupos do microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) e os [grupos no Microsoft 365 para pôster de arquitetos de ti](teams-architecture-solutions-posters.md#groups-in-microsoft-365) .

## <a name="how-microsoft-365-groups-work-with-teams"></a>Como os grupos do Microsoft 365 funcionam com o Microsoft Teams

Quando você cria uma equipe, um grupo do Microsoft 365 é criado para gerenciar os membros da equipe. Os serviços relacionados do grupo, como um site do SharePoint, espaço de trabalho do Power BI, etc., são criados ao mesmo tempo.

As pessoas que criam equipes podem optar por usar um grupo existente do Microsoft 365 se forem proprietários desse grupo. Cada canal da equipe tem uma pasta separada na biblioteca de documentos. A criação de pastas diretamente na biblioteca de documentos não cria canais na equipe.

Ao criar um grupo do Microsoft 365 no Outlook ou no SharePoint, a caixa de correio do grupo fica visível no Outlook. Ao criar uma equipe no Microsoft Teams, a caixa de correio do grupo fica oculta por padrão. Você pode usar o cmdlet [set-unificado](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) com o parâmetro **HiddenFromExchangeClientsEnabled** para deixar uma caixa de correio visível.

## <a name="group-membership"></a>Associação a grupos

Se você remover um membro de uma equipe, ele será removido do grupo do Microsoft 365 também. A remoção do grupo remove imediatamente a equipe e os canais do cliente do teams. Se você remover uma pessoa de um grupo usando o centro de administração do Microsoft 365, ele não terá mais acesso aos outros aspectos de colaboração, como a biblioteca de documentos do SharePoint Online, o grupo do Yammer ou o OneNote compartilhado. No entanto, eles ainda terão acesso à funcionalidade de chat da equipe por aproximadamente duas horas.

Como prática recomendada para gerenciar os membros da equipe, adicione-os e remova-os do cliente do teams para garantir que as atualizações de permissões para outras cargas de trabalho conectadas a grupos ocorram rapidamente. Se você adicionar ou remover membros da equipe fora do cliente do Teams (usando o centro de administração do Microsoft 365, o Azure AD ou o Microsoft Exchange Online PowerShell), pode levar até 24 horas para que as alterações sejam refletidas no Microsoft Teams.

## <a name="deleting-groups-and-teams"></a>Excluindo grupos e equipes

Excluir um grupo do Microsoft 365 removerá o alias da caixa de correio para conversas persistentes do Outlook/OWA e convites de reunião do Teams e marcará o site do SharePoint para exclusão. Demora aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito no Outlook. A exclusão de uma equipe do cliente do teams a removerá imediatamente do modo de exibição para todos os membros da equipe. Se você remover membros de um grupo do Microsoft 365 com a funcionalidade de equipe habilitada nele, pode haver um atraso de aproximadamente duas horas antes de a equipe ser removida da exibição no cliente do teams para as pessoas afetadas que foram removidas.

Para obter detalhes sobre o fim das opções do ciclo de vida de grupos e equipes, consulte  [fim das opções do ciclo de vida para grupos, equipes e Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) e [arquivar ou excluir uma equipe no Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).

## <a name="related-topics"></a>Tópicos relacionados

[Fundamentos do Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar um grupo excluído](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)