---
title: Grupos do Microsoft 365 e o Microsoft Teams
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: Neste artigo, você aprenderá como os grupos do Microsoft 365 e as associações de grupo funcionarão com o Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82b8de29d8f73f439f158e96d1c61767a3bd019
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940688"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Grupos do Microsoft 365 e o Microsoft Teams
=====================================

> [!Tip]
> Assista à sessão a seguir para saber como as equipes interagem com o Azure Active Directory (Azure AD), o Microsoft 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [bases do Microsoft Teams](https://aka.ms/teams-foundations)

O Microsoft 365 groups é o serviço de associação entre aplicativos no Office 365. No nível básico, um grupo do Office 365 é um objeto no Azure Active Directory com uma lista de membros e um acoplamento flexível a cargas de trabalho relacionadas, incluindo um site de equipe do SharePoint, grupo do Yammer, recursos compartilhados de caixa de correio do Exchange, Planner, Power BI e OneNote. Você pode adicionar ou remover pessoas para o grupo da mesma forma que faria com qualquer outro objeto de segurança baseado em grupo no Active Directory.

Um administrador do Office 365 pode definir um grupo do Office 365, adicionar membros e beneficiar-se de recursos como uma caixa de correio compartilhada do Exchange, uma biblioteca de documentos do SharePoint, um grupo do Yammer e assim por diante. Para obter mais informações sobre os grupos do Microsoft 365, consulte [saiba mais sobre os grupos do microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Não perca os grupos de pôsteres [no Microsoft 365 para arquitetos de ti](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-microsoft-365-groups-work"></a>Como funcionam os grupos do Microsoft 365
--------------------------

Quando você cria uma equipe, no back-end, está criando um grupo do Office 365 e a biblioteca de documentos do SharePoint associada e o bloco de anotações do OneNote, juntamente com os associados a outros aplicativos em nuvem do Office 365. Se a pessoa que cria a equipe for um proprietário de um grupo público ou particular existente do Office 365, ele poderá adicionar funcionalidades de equipe ao grupo se ele tiver menos de 5000 pessoas e nunca tiver sido adicionado ao Teams. Isso cria um canal **geral** padrão no qual mensagens de chat, documentos, OneNote e outros objetos residem. A exibição da biblioteca de documentos para o canal revelará a pasta **geral** que representa o canal na equipe. O mais importante é que, se você criar sua própria estrutura de pastas dentro de uma biblioteca de documentos, **ela não se propaga** para o Teams como um canal; por enquanto, ela só flui do Teams para o SharePoint.

> [!NOTE]
> Com base nos comentários dos clientes, os novos grupos do Microsoft 365 gerados como resultado da criação de uma equipe no Microsoft Teams não serão mais exibidos no Outlook por padrão. Para os clientes que desejam continuar com o comportamento existente para mostrar esses grupos no Outlook, será fornecido um cmdlet do PowerShell do Exchange Online que pode habilitar o grupo para a experiência do Outlook. Os grupos criados por meio do Outlook e, em seguida, habilitados para Teams continuarão a ser exibidos no Outlook e nas equipes. Esta atualização se implementará gradualmente no Outlook e nas equipes nos próximos meses.

> [!NOTE]
> A exclusão de um Grupo do Office 365 removerá o alias de caixa de correio de conversas persistentes do Outlook/OWA e os convidados da reunião do Teams, e marcará o site do SharePoint para exclusão. Demora aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito no Outlook. A exclusão de uma equipe do cliente do teams a removerá imediatamente do modo de exibição para todos os membros da equipe. Se você remover membros de um grupo do Office 365 com a funcionalidade de equipe habilitada nele, pode haver um atraso de aproximadamente duas horas antes de a equipe ser removida da exibição no cliente do teams para as pessoas afetadas que foram removidas.
>
>Leia [isto](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) para obter informações sobre como restaurar um grupo do Office 365 que você excluiu.

<a name="group-membership"></a>Associação a grupos
----------------

Os recursos e as funcionalidades do grupo para seus usuários dependem de onde você conduz os membros do grupo. Por exemplo, se você remover um membro de uma equipe, ele será removido do grupo do Office 365 também. A remoção do grupo remove imediatamente a equipe e os canais do cliente do teams. Se você remover uma pessoa de um grupo usando o centro de administração do Microsoft 365, ele não terá mais acesso aos outros aspectos de colaboração, como a biblioteca de documentos do SharePoint Online, o grupo do Yammer ou o OneNote compartilhado. No entanto, eles ainda terão acesso à funcionalidade de chat da equipe por aproximadamente duas horas.

Como prática recomendada para gerenciar membros do Teams, adicione e remova membros do cliente do teams para garantir que o controle de acesso em cascata correto para outros aplicativos de nuvem dependentes seja aplicado. Além disso, você evitará uma experiência não contígua, deixando as pessoas com a impressão de que ainda têm acesso aos recursos que costumavam ter (até o próximo ciclo de sincronização adicionar ou revogar acesso a um componente específico do serviço). Se você adicionar ou remover membros da equipe fora do cliente do Teams (usando o centro de administração do Microsoft 365, o Azure AD ou o PowerShell do Exchange Online), poderá levar até 24 horas (mais em alguns casos) para que as alterações sejam refletidas no Microsoft Teams.
