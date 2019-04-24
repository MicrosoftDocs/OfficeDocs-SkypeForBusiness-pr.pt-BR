---
title: Grupos do Office 365 e equipes da Microsoft
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: msteams
description: Saiba como os grupos do Office 365 e as assinaturas de grupo trabalham com o Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77c8125425bf7aaaf6f619edc9463b17967e4133
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32180260"
---
<a name="office-365-groups-and-microsoft-teams"></a>Grupos do Office 365 e equipes da Microsoft
=====================================

> [!Tip]
> Assista a sessão a seguir para saber como equipes interage com o Azure Active Directory (AD Azure), grupos do Office 365, Exchange, SharePoint e OneDrive for Business: [Fundamentos das equipes da Microsoft](https://aka.ms/teams-foundations)

Os grupos do Office 365 são o serviço de assinatura cruzada de aplicativos do Office 365. No nível básico, um grupo do Office 365 é um objeto no Windows Azure Active Directory com uma lista de membros e um acoplamento para cargas de trabalho relacionados, incluindo um site de equipe do SharePoint, grupo do Yammer, shared recursos de caixa de correio do Exchange, planejador, Power BI e o OneNote. É possível adicionar ou remover pessoas ao grupo, assim como faria com qualquer outro objeto de segurança baseada em grupo no Active Directory.

Um administrador do Office 365 pode definir um grupo do Office 365, adicionar membros e se beneficiar dos recursos, como uma troca shared da caixa de correio, biblioteca de documentos do SharePoint, grupo do Yammer e assim por diante. Para obter mais informações sobre grupos do Office 365, consulte [Saiba mais sobre os grupos do Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Não perca o cartaz e exibir [grupos no Microsoft 365 para arquitetos de TI](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-office-365-groups-work"></a>Como funcionam os grupos do Office 365
--------------------------

Quando você cria uma equipe, no back-end, você está criando um grupo do Office 365 e a biblioteca de documentos do SharePoint associada e o bloco de anotações do OneNote, juntamente com integra-se ao outros aplicativos de nuvem do Office 365. Se a pessoa que está criando a equipe é um proprietário de um existente do Office 365 público ou grupo privado, eles podem adicionar a funcionalidade de equipes ao grupo se ele tiver menos de 5.000 pessoas e nunca foi adicionado às equipes. Isso cria um canal **Geral** padrão no qual o bate-papo mensagens, documentos, OneNote e outros objetos residem. Exibindo a biblioteca de documentos para o canal revelará a pasta **gerais** que representam o canal na equipe de. O mais importante é que, se você criar sua própria estrutura de pastas dentro de uma biblioteca de documentos, **ela não se propaga** para o Teams como um canal; por enquanto, ela só flui do Teams para o SharePoint.

> [!NOTE]
> Com base nos comentários do cliente, novos grupos de Office 365 gerado como resultado de criação de uma equipe no Microsoft Teams não mais aparecerá no Outlook por padrão. Para clientes que deseja continuar com o comportamento existente do mostrando esses grupos no Outlook, um cmdlet do PowerShell do Exchange Online será fornecido que pode permitir que o grupo para a experiência do Outlook. Grupos criados pelo Outlook e habilitado mais tarde para equipes continuará Mostrar no Outlook e equipes. Essa atualização será gradualmente roll a saída entre o Outlook e as equipes nos próximos meses.

> [!NOTE]
> A exclusão de um Grupo do Office 365 removerá o alias de caixa de correio de conversas persistentes do Outlook/OWA e os convidados da reunião do Teams, e marcará o site do SharePoint para exclusão. Leva aproximadamente 20 minutos entre a remoção de uma equipe e seu efeito no Outlook. Excluir uma equipe do cliente equipes removerá imediatamente de modo a todos os membros da equipe. Se você remover membros de um grupo do Office 365 que teve a funcionalidade de equipes ativada contidas nela, pode haver um atraso de aproximadamente duas horas antes que a equipe é removida do modo de exibição no cliente do equipes para as pessoas afetados que foram removidos.
>
>Leia [Este](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) para obter informações sobre como restaurar um grupo do Office 365 que você excluiu.

<a name="group-membership"></a>Associação a grupos
----------------

Recursos de grupo e capacidades para seus usuários dependem em que a unidade de participação no grupo. Por exemplo, se você remover um membro de uma equipe, eles são removidos do grupo Office 365 também. A remoção do grupo imediatamente remove a equipe e canais do cliente equipes. Se você remover uma pessoa de um grupo usando o Centro de administração do Office 365, eles não terá mais acesso a outros aspectos de colaboração, como a biblioteca de documentos do SharePoint Online, no grupo ou compartilhado do OneNote Yammer. No entanto, eles terão ainda acesso à funcionalidade de bate-papo da equipe por aproximadamente duas horas.

Como prática recomendada para o gerenciamento de membros de equipes, adicionar e remover membros do cliente equipes para garantir que o controle de acesso correto em cascata para outros aplicativos de nuvem dependentes seja aplicado. Além disso, você evitará uma experiência não contígua, deixando as pessoas com a impressão de que ainda têm acesso aos recursos que costumavam ter (até o próximo ciclo de sincronização adicionar ou revogar acesso a um componente específico do serviço). Se você adicionar ou remover membros de equipe fora do cliente de equipes (usando o Centro de administração do Office 365, Windows Azure AD, ou Exchange Online PowerShell), pode demorar até duas horas para que as alterações sejam refletidas em equipes.
