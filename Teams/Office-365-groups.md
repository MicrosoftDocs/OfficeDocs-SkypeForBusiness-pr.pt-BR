---
title: Grupos do Office 365 e Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Saiba como os grupos do Office 365 e as assinaturas de grupo trabalham com o Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a>Grupos do Office 365 e Microsoft Teams
=====================================

Os grupos do Office 365 são o serviço de assinatura cruzada de aplicativos do Office 365. Basicamente falando, um grupo do Office 365 é um objeto no diretório ativo do Azure com uma lista de membros e um acoplamento fraco para cargas de trabalho relacionadas, incluindo um site de equipes no SharePoint, Yammer Group, recursos de caixa de correio compartilhada no Exchange, Planner, PowerBI e OneNote. Você pode adicionar ou remover pessoas ao grupo, da mesma forma como faria com qualquer outro objeto de segurança baseado em grupo no Diretório Ativo.

Um administrador do Office 365 pode definir um grupo do Office 365, adicionar membros e aproveitar recursos como caixa de correio compartilhada do Exchange, biblioteca de documentos do SharePoint,Yammer Group, etc. para obter mais informações sobre grupos, acesse: [Saber sobre os grupos do Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Como funcionam os grupos do Office 365
--------------------------

Quando você cria um Microsoft Teams no back-end, você está criando um Grupo do Office 365, juntamente com a biblioteca de documentos associada do SharePoint, o notebook do OneNote, além dos relacionamentos em outros aplicativos em nuvem do Office 365. Se a pessoa que cria a Equipe é proprietária de um Grupo Público ou Privado existente do Office 365, ela pode adicionar ao Grupo a funcionalidade do Teams. Isso cria um canal padrão “Geral”, onde ficarão as mensagens de bate-papo, os documentos, o OneNote e outros objetos. A exibição da biblioteca de documentos do canal mostrará a pasta “Geral” que representa o canal no Teams. O mais importante é que, se você criar sua própria estrutura de pastas dentro de uma biblioteca de documentos, **ela não se propaga** para o Teams como um canal; por enquanto, ela só flui do Teams para o SharePoint.




> [!NOTE]
> A exclusão de um Grupo do Office 365 removerá o alias de caixa de correio de conversas persistentes do Outlook/OWA e os convidados da reunião do Teams, e marcará o site do SharePoint para exclusão. A remoção de uma Equipe e o seu efeito no Outlook leva cerca de 20 minutos. A exclusão de uma Equipe do cliente Teams a removerá imediatamente da visualização de todos os membros da equipe. Se você remover um membro de um Grupo do Office 365 que tenha a funcionalidade do Teams habilitada, poderá haver um atraso de aproximadamente uma hora até que o Teams seja removido da visualização do cliente Teams para as pessoas que foram efetivamente removidas.

<a name="group-membership"></a>Associação a grupos
----------------

Recursos de grupo e capacidades para seus usuários depende em que a unidade de participação no grupo. Por exemplo, se você remover um membro de uma equipe, eles são removidos do grupo Office 365 também. A remoção do Grupo remove imediatamente a Equipe e os canais do cliente Teams. Se você remover uma pessoa de um Grupo usando o portal de administrador do Office 365, ela não terá mais acesso aos outros aspectos colaborativos, como a biblioteca de documentos do SharePoint Online, o Yammer Group ou o OneNote compartilhado. No entanto, ela ainda terá acesso à funcionalidade de bate-papo do Teams por aproximadamente uma hora.

Práticas recomendadas de gerenciamento de membros de equipes: adicionar e remover membros do cliente equipes para garantir o controle de acesso correto em cascata para outros aplicativos de nuvem dependentes seja aplicado. Além disso, você evitará uma experiência não contígua, deixando as pessoas com a impressão de que ainda têm acesso aos recursos que costumavam ter (até o próximo ciclo de sincronização adicionar ou revogar acesso a um componente específico do serviço). Se você adicionar ou remover membros de equipe fora do cliente de equipes (usando o Centro de administração do Office 365, Windows Azure AD, ou Exchange Online PowerShell), às vezes, leva até uma hora para que as alterações sejam refletidas em equipes.
