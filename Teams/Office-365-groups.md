---
title: Grupos do Microsoft 365 e Microsoft Teams
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
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125426"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Grupos do Microsoft 365 e Microsoft Teams

Grupos do Microsoft 365 é o serviço de associação entre aplicativos no Microsoft 365. Em um nível básico, um grupo Microsoft 365 é um objeto no Azure Active Directory com uma lista de membros e um acoplamento para cargas de trabalho relacionadas, incluindo um site de equipe do SharePoint, uma caixa de correio Exchange compartilhada, o Planner e um notebook OneNote. Você pode adicionar ou remover pessoas ao grupo da mesma forma que faria com qualquer outro objeto de segurança baseado em grupo no Active Directory.

![Diagrama mostrando Grupos do Microsoft 365 e serviços relacionados.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Por padrão, os usuários no Microsoft 365 podem criar e gerenciar grupos. Para obter mais informações sobre Grupos do Microsoft 365, consulte Learn [about Grupos do Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Como Grupos do Microsoft 365 trabalhar com Teams

Quando você cria uma equipe, um grupo Microsoft 365 é criado para gerenciar a associação à equipe. Os serviços relacionados do grupo, como um site SharePoint, caixa de correio etc. são criados ao mesmo tempo.

As pessoas que criam equipes podem optar por usar um grupo Microsoft 365 existente se forem proprietários desse grupo. Cada canal da equipe tem uma pasta separada na biblioteca de documentos. A criação de pastas diretamente na biblioteca de documentos não cria canais na equipe.

Ao criar um grupo Microsoft 365 no Outlook ou SharePoint, a caixa de correio do grupo fica visível Outlook. Ao criar uma equipe no Teams, a caixa de correio do grupo fica oculta por padrão. Você pode usar o cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) com o **parâmetro HiddenFromExchangeClientsEnabled** para tornar uma caixa de correio visível.

## <a name="group-membership"></a>Associação a grupos

Se você remover um membro de uma equipe, eles também serão removidos Microsoft 365 grupo. A remoção do grupo remove imediatamente a equipe e os canais do Teams cliente. Se você remover uma pessoa de um grupo usando o Centro de administração do Microsoft 365, ela não terá mais acesso aos outros aspectos colaborativos, como biblioteca de documentos do SharePoint Online, grupo Yammer ou OneNote. No entanto, eles ainda terão acesso à funcionalidade de chat da equipe por aproximadamente duas horas.

Como prática recomendada para gerenciar membros da equipe, adicione e remova-os do cliente Teams para garantir que as atualizações de permissões para outras cargas de trabalho conectadas ao grupo ocorram rapidamente. Se você adicionar ou remover membros da equipe fora do cliente Teams (usando o Centro de administração do Microsoft 365, o Azure AD ou o Exchange Online PowerShell), poderá levar até 24 horas para que as alterações sejam refletidas no Teams.

## <a name="deleting-groups-and-teams"></a>Excluindo grupos e equipes

Excluir um grupo Microsoft 365 removerá o alias da caixa de correio para conversas Outlook/OWA persistentes e convites de reunião do Teams e marcará o site SharePoint para exclusão. Leva aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito Outlook. Excluir uma equipe do Teams o removerá imediatamente da exibição para todos os membros da equipe. Se você remover membros de um grupo do Microsoft 365 que teve a funcionalidade Teams habilitada, poderá haver um atraso de aproximadamente duas horas antes que a equipe seja removida da exibição no cliente do Teams para as pessoas afetadas que foram removidas.

Para obter detalhes sobre os grupos e as opções de fim do ciclo de vida das equipes, confira as opções de fim do ciclo de vida para grupos, equipes e [Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) e Arquivar ou excluir uma equipe no [Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Tópicos relacionados

[Fundamentos do Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar um grupo excluído](/microsoft-365/admin/create-groups/restore-deleted-group)
