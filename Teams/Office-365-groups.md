---
title: Grupos do Microsoft 365 e Microsoft Teams
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
description: Saiba como os grupos e associações de grupo do Microsoft 365 funcionam com o Microsoft Teams.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105237"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Grupos do Microsoft 365 e Microsoft Teams

Grupos do Microsoft 365 é o serviço de associação entre aplicativos no Microsoft 365. Em um nível básico, um Grupo do Microsoft 365 é um objeto no Azure Active Directory com uma lista de membros e um acoplamento a cargas de trabalho relacionadas, incluindo um site de equipe do SharePoint, uma caixa de correio compartilhada do Exchange, o Planner e o espaço de trabalho do Power BI. Você pode adicionar ou remover pessoas ao grupo da mesma forma que faria com qualquer outro objeto de segurança baseado em grupo no Active Directory.

![Diagrama mostrando grupos do Microsoft 365 e serviços relacionados](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Por padrão, os usuários no Microsoft 365 podem criar e gerenciar grupos. Para obter mais informações sobre grupos do Microsoft 365, consulte Saiba mais sobre grupos do [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) e os grupos no [Microsoft 365 para arquitetos de](teams-architecture-solutions-posters.md#groups-in-microsoft-365) IT.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Como os grupos do Microsoft 365 funcionam com o Teams

Quando você cria uma equipe, um grupo do Microsoft 365 é criado para gerenciar a associação à equipe. Os serviços relacionados do grupo, como um site do SharePoint, espaço de trabalho do Power BI, etc. são criados ao mesmo tempo.

As pessoas que criam equipes podem optar por usar um grupo existente do Microsoft 365 se eles são proprietários desse grupo. Cada canal na equipe tem uma pasta separada na biblioteca de documentos. A criação de pastas diretamente na biblioteca de documentos não cria canais na equipe.

Ao criar um grupo do Microsoft 365 no Outlook ou no SharePoint, a caixa de correio de grupo fica visível no Outlook. Ao criar uma equipe no Teams, a caixa de correio de grupo é oculta por padrão. Você pode usar o cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) com o **parâmetro HiddenFromExchangeClientsEnabled** para tornar uma caixa de correio visível.

## <a name="group-membership"></a>Associação a grupos

Se você remover um membro de uma equipe, ele também será removido do grupo do Microsoft 365. A remoção do grupo remove imediatamente a equipe e os canais do cliente do Teams. Se você remover uma pessoa de um grupo usando o Centro de administração do Microsoft 365, ela não terá mais acesso aos outros aspectos colaborativos, como biblioteca de documentos do SharePoint Online, grupo do Yammer ou OneNote compartilhado. No entanto, eles ainda terão acesso à funcionalidade de chat da equipe por aproximadamente duas horas.

Como prática prática de gerenciamento de membros da equipe, adicione e remova-os do cliente do Teams para garantir que as atualizações de permissões para outras cargas de trabalho conectadas a grupos ocorram rapidamente. Se você adicionar ou remover membros da equipe fora do cliente do Teams (usando o centro de administração do Microsoft 365, o Azure AD ou o PowerShell do Exchange Online), pode levar até 24 horas para que as alterações sejam refletidas no Teams.

## <a name="deleting-groups-and-teams"></a>Excluir grupos e equipes

Excluir um grupo do Microsoft 365 removerá o alias da caixa de correio para conversas persistentes do Outlook/OWA e convites de reunião do Teams e marcará o site do SharePoint para exclusão. Leva aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito no Outlook. A exclusão de uma equipe do cliente do Teams a removerá imediatamente do ponto de vista para todos os membros da equipe. Se você remover membros de um Grupo do Microsoft 365 que teve a funcionalidade do Teams habilitada, pode haver um atraso de aproximadamente duas horas antes de a equipe ser removida do modo de exibição no cliente do Teams para as pessoas afetadas que foram removidas.

Para obter detalhes sobre grupos e equipes de fim de ciclo de vida, consulte Opções de fim de ciclo de vida para  [grupos, equipes](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) e Yammer e Archive ou excluir uma [equipe no Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Tópicos relacionados

[Fundamentos do Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar um grupo excluído](/microsoft-365/admin/create-groups/restore-deleted-group)