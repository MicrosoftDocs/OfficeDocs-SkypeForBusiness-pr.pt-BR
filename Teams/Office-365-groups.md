---
title: Microsoft 365 Groups e Microsoft Teams
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
description: Saiba mais sobre como os grupos e associações de grupo do Microsoft 365 funcionam com o Microsoft Teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456075"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Groups e Microsoft Teams

O Microsoft 365 Groups é o serviço de associação entre aplicativos no Microsoft 365. Em um nível básico, um Grupo do Microsoft 365 é um objeto no Azure Active Directory com uma lista de membros e um problema com cargas de trabalho relacionadas, incluindo um site de equipe do SharePoint, uma caixa de correio compartilhada do Exchange, o Planner e o espaço de trabalho do Power BI. Você pode adicionar ou remover pessoas ao grupo da mesma forma que faria com qualquer outro objeto de segurança baseado em grupo no Active Directory.

![Diagrama mostrando grupos do Microsoft 365 e serviços relacionados](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Por padrão, os usuários no Microsoft 365 podem criar e gerenciar grupos. Para obter mais informações sobre os Grupos do Microsoft 365, consulte Saiba mais sobre os Grupos do [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) e os Grupos no pôster do [Microsoft 365 for IT Architects.](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

## <a name="how-microsoft-365-groups-work-with-teams"></a>Como os Grupos do Microsoft 365 funcionam com o Teams

Quando você cria uma equipe, um grupo do Microsoft 365 é criado para gerenciar a associação à equipe. Os serviços relacionados do grupo, como um site do SharePoint, espaço de trabalho do Power BI etc. são criados ao mesmo tempo.

As pessoas que criam equipes podem optar por usar um grupo existente do Microsoft 365 se eles são proprietários desse grupo. Cada canal da equipe tem uma pasta separada na biblioteca de documentos. Criar pastas diretamente na biblioteca de documentos não cria canais na equipe.

Ao criar um grupo do Microsoft 365 no Outlook ou no SharePoint, a caixa de correio do grupo fica visível no Outlook. Ao criar uma equipe no Teams, a caixa de correio do grupo fica oculta por padrão. Você pode usar o cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) com o parâmetro **HiddenFromExchangeClientsEnabled** para tornar uma caixa de correio visível.

## <a name="group-membership"></a>Associação a grupos

Se você remover um membro de uma equipe, ele também será removido do grupo do Microsoft 365. A remoção do grupo remove imediatamente a equipe e os canais do cliente do Teams. Se você remover uma pessoa de um grupo usando o Centro de administração do Microsoft 365, ela não terá mais acesso a outros aspectos colaborativos, como biblioteca de documentos do SharePoint Online, grupo do Yammer ou OneNote compartilhado. No entanto, eles ainda terão acesso à funcionalidade de chat da equipe por aproximadamente duas horas.

Como prática prática de gerenciamento de membros da equipe, adicione-os e remova-os do cliente do Teams para garantir que as atualizações de permissões para outras cargas de trabalho conectadas a grupos ocorram rapidamente. Se você adicionar ou remover membros da equipe fora do cliente teams (usando o Centro de administração do Microsoft 365, o Azure AD ou o PowerShell do Exchange Online), poderá levar até 24 horas para que as alterações sejam refletidas no Teams.

## <a name="deleting-groups-and-teams"></a>Excluindo grupos e equipes

Excluir um grupo do Microsoft 365 removerá o alias de caixa de correio para conversas persistentes do Outlook/OWA e convites de reunião do Teams e marcará o site do SharePoint para exclusão. Leva aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito no Outlook. Excluir uma equipe do cliente do Teams a removerá imediatamente da exibição para todos os membros da equipe. Se você remover membros de um Grupo do Microsoft 365 que tinha a funcionalidade do Teams habilitada, pode haver um atraso de aproximadamente duas horas antes de a equipe ser removida do modo de exibição no cliente do Teams para as pessoas afetadas que foram removidas.

Para obter detalhes sobre o fim das opções de ciclo de vida de grupos e equipes, confira as opções de fim do ciclo de vida para [grupos,](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) equipes e Yammer e Arquivar ou excluir uma equipe [no Microsoft Teams.](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)

## <a name="related-topics"></a>Tópicos relacionados

[Fundações do Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar um grupo excluído](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)