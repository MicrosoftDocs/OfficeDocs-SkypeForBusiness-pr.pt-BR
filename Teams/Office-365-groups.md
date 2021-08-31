---
title: Microsoft 365 Grupos e Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Saiba mais sobre como Microsoft 365 grupos e associações de grupo funcionam com Microsoft Teams.
ms.openlocfilehash: 4e140d50bb16c9ed99f126662545fb026c3df60a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729730"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Grupos e Microsoft Teams

Microsoft 365 Grupos é o serviço de associação entre aplicativos Microsoft 365. Em um nível básico, um grupo Microsoft 365 é um objeto no Azure Active Directory com uma lista de membros e um acoplamento a cargas de trabalho relacionadas, incluindo um site de equipe do SharePoint, uma caixa de correio de Exchange compartilhada, o Planner e o Power BI de trabalho. Você pode adicionar ou remover pessoas ao grupo da mesma forma que faria com qualquer outro objeto de segurança baseado em grupo no Active Directory.

![Diagrama mostrando Microsoft 365 grupos e serviços relacionados.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Por padrão, os usuários Microsoft 365 podem criar e gerenciar grupos. Para obter mais informações sobre Microsoft 365 Grupos, consulte [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the Groups in Microsoft 365 for IT [Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Como Microsoft 365 grupos trabalham com Teams

Quando você cria uma equipe, um grupo Microsoft 365 é criado para gerenciar a associação à equipe. Os serviços relacionados do grupo, como um site SharePoint, Power BI de trabalho, etc. são criados ao mesmo tempo.

As pessoas que criam equipes podem optar por usar um grupo Microsoft 365 existente se eles são proprietários desse grupo. Cada canal na equipe tem uma pasta separada na biblioteca de documentos. A criação de pastas diretamente na biblioteca de documentos não cria canais na equipe.

Ao criar um grupo Microsoft 365 no Outlook ou SharePoint, a caixa de correio de grupo fica visível no Outlook. Ao criar uma equipe no Teams, a caixa de correio de grupo é oculta por padrão. Você pode usar o cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) com o **parâmetro HiddenFromExchangeClientsEnabled** para tornar uma caixa de correio visível.

## <a name="group-membership"></a>Associação a grupos

Se você remover um membro de uma equipe, eles também serão removidos Microsoft 365 grupo. A remoção do grupo remove imediatamente a equipe e os canais do Teams cliente. Se você remover uma pessoa de um grupo usando o Centro de administração do Microsoft 365, ela não terá mais acesso aos outros aspectos colaborativos, como biblioteca de documentos do SharePoint Online, grupo Yammer ou OneNote. No entanto, eles ainda terão acesso à funcionalidade de chat da equipe por aproximadamente duas horas.

Como prática prática de gerenciamento de membros da equipe, adicione e remova-os do cliente Teams para garantir que as atualizações de permissões para outras cargas de trabalho conectadas a grupos ocorram rapidamente. Se você adicionar ou remover membros da equipe fora do cliente Teams (usando o Centro de administração do Microsoft 365, o Azure AD ou o Exchange Online PowerShell), pode levar até 24 horas para que as alterações sejam refletidas no Teams.

## <a name="deleting-groups-and-teams"></a>Excluir grupos e equipes

Excluir um grupo Microsoft 365 removerá o alias de caixa de correio para conversas Outlook/OWA persistentes e convites de reunião Teams e marcará o site SharePoint para exclusão. Leva aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito Outlook. Excluir uma equipe do cliente Teams a removerá imediatamente da exibição para todos os membros da equipe. Se você remover membros de um grupo Microsoft 365 que teve uma funcionalidade Teams habilitada nele, pode haver um atraso de aproximadamente duas horas antes de a equipe ser removida do modo de exibição no cliente Teams para as pessoas afetadas que foram removidas.

Para obter detalhes sobre grupos e equipes de fim de ciclo de vida, consulte Opções de fim de ciclo de vida para [grupos,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) equipes e Yammer e [Arquivar](./archive-or-delete-a-team.md)ou excluir uma equipe no Microsoft Teams .

## <a name="related-topics"></a>Tópicos relacionados

[Fundamentos da Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar um grupo excluído](/microsoft-365/admin/create-groups/restore-deleted-group)