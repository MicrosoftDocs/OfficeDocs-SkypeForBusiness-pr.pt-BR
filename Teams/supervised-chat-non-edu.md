---
title: Usar chats supervisionados para locatários não educacionais
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre chats supervisionados para locatários não educacionais em Microsoft Teams reuniões.
ms.openlocfilehash: d56a41e3c168aea1d5454fb38ae2aac0c033fe64
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745477"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chats supervisionados para locatários não educacionais

O chat supervisionado permite que supervisores designados iniciem bate-papos com qualquer pessoa em sua organização e impede que usuários restritos iniciem novos chats, a menos que um supervisor apropriado esteja presente. Quando a supervisão de chat está habilitada, os supervisores não têm permissão para sair dos chats e outros participantes não têm permissão para removê-los, garantindo que os chats envolvendo usuários restritos sejam supervisionados corretamente.

Essas limitações só são aplicadas a novos chats privados criados após o chat supervisionado ter sido totalmente habilitado. Eles não se aplicam a chats particulares, chats de reuniões ou canais existentes.

O chat supervisionado é personalizado para necessidades de instituições educacionais, mas também está disponível para locatários não educacionais.

> [!NOTE]
> O chat supervisionado protege os novos chats criados após a aplicação do recurso. Ele não protege chats existentes.

## <a name="enable-supervised-chat"></a>Habilitar o chat supervisionado

> [!NOTE]
> Certifique-se de configurar as funções de permissão de chat e as políticas de permissão de chat baseadas em função antes de habilinar o chat para sua instituição para evitar o acesso restrito indesejado do usuário a chats não supervisionados.

**Definir funções de permissão de chat para cada usuário em seu ambiente**

Para que o chat supervisionado funcione conforme esperado, cada usuário em seu ambiente precisa receber a função de permissão de chat correta. Há três funções que um usuário pode ter atribuído:

- Permissões completas: essa função deve ser atribuída aos supervisores de chat em seu ambiente. Eles podem iniciar chats com qualquer usuário em seu ambiente. Espera-se que os usuários com permissões completas supervisionem os chats em que participam. Eles não podem sair ou ser removidos de chats que iniciam ou chats que estão supervisionando em locatários federados.

- Permissões limitadas: essa função é ideal para membros da equipe que só devem ter acesso supervisionado a usuários restritos. Eles podem iniciar chats com usuários completos ou limitados, mas não podem iniciar chats com usuários restritos. Se um usuário com permissões completas iniciar um chat com um usuário restrito, usuários limitados poderão ser levados para a conversa. Esse acesso acontece porque um usuário com permissões completas está presente para supervisionar a colaboração entre usuários limitados e restritos.

- Permissões restritas: essa função é ideal para usuários que precisam ser supervisionados. Eles só podem iniciar chats com usuários que têm permissões completas. Eles podem participar de qualquer conversa que um usuário com permissões completas o convide. Em casos de chat federado, os usuários restritos só podem ser adicionados a chats por um usuário com permissões completas que são do locatário do usuário restrito.

Para definir a função de permissão de chat dos usuários, use a política de função de permissões de **chat** encontrada nas opções de política de mensagens no portal de Teams de administração. Você pode usar o PowerShell para definir funções usando a política ChatPermissionRole com os valores Full, Limited ou Restricted. Esta política está em [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).

As funções não podem ser atribuídas aos convidados em seu locatário. Os convidados são atribuídos à função limitada.

## <a name="allow-supervised-chat"></a>Permitir chat supervisionado

O chat supervisionado está desabilitado por padrão para seu locatário. Depois de definir funções de permissão de chat para seus usuários, você pode habilitar o chat supervisionado em seu locatário, indo para configurações em toda a organização Teams Configurações e definindo a política de permissões de  >   **chat baseadas** em função como **Ativado**. Você também pode usar o PowerShell para habilitar o Chat Supervisionado definindo AllowRoleBasedChatPermissions como True. Este cmdlet está em [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).

O chat supervisionado deve ser habilitado para todos os usuários no locatário e não pode ser habilitado apenas para uma parte de seus usuários.

**Habilitar o chat**

Habilita o chat para todos os usuários usando a política de Chat existente disponível no Teams de administração.

**Manter chats supervisionados**

Depois que o chat supervisionado for habilitado inicialmente, você precisará fazer algumas coisas para garantir que os chats em seu ambiente permaneçam supervisionados:

- Atribua funções apropriadas a todos os novos usuários que ingressarem em seu locatário. Por padrão, os usuários receberão uma função restrita.

- Se um usuário com permissões completas sair ou for removido de um locatário, os chats que estavam supervisionando serão deixados sem supervisão. Antes de remover o usuário original, certifique-se de que outro usuário com permissões completas seja adicionado a essas conversas para que o chat possa permanecer supervisionado. Depois que o supervisor original é removido, novos participantes não podem ser adicionados à conversa, mas os participantes atuais podem continuar a se comunicar.
