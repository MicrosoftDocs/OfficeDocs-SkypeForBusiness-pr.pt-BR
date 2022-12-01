---
title: Usar chats supervisionados para locatários não educacionais
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre chats supervisionados para locatários não educacionais em reuniões do Microsoft Teams.
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc7ddf23b600ec2a7f4d4f02c2328587627572fc
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198283"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chats supervisionados para locatários não educacionais

O chat supervisionado permite que supervisores designados iniciem chats com qualquer pessoa em sua organização e impede que usuários restritos iniciem novos chats, a menos que um supervisor apropriado esteja presente. Quando a supervisão de chat está habilitada, os supervisores não podem deixar chats e outros participantes não podem removê-los, garantindo que chats envolvendo usuários restritos sejam devidamente supervisionados.

Essas limitações só são aplicadas a novos chats privados que são criados após o chat supervisionado ter sido totalmente habilitado. Eles não se aplicam a chats privados existentes, chats de reuniões ou canais.

O chat supervisionado é adaptado para as necessidades da instituição de ensino, mas também está disponível para locatários não educacionais.

> [!NOTE]
> O chat supervisionado protege novos chats criados após a imposição do recurso. Ele não protege chats existentes.

## <a name="enable-supervised-chat"></a>Habilitar o chat supervisionado

> [!NOTE]
> Verifique se você configurou funções de permissão de chat e as políticas de permissão de chat baseadas em função antes de habilitar o chat para sua instituição para evitar o acesso restrito indesejado do usuário a chats não supervisionados.

**Definir funções de permissão de chat para cada usuário em seu ambiente**:

Para que o chat supervisionado funcione conforme o esperado, cada usuário em seu ambiente precisa receber a função de permissão de chat correta. Há três funções que um usuário pode ter atribuído:

- Permissões completas: essa função deve ser atribuída aos supervisores de chat em seu ambiente. Eles podem iniciar chats com qualquer usuário em seu ambiente. Espera-se que os usuários com permissões completas supervisionem os chats em que participam. Eles não podem sair ou ser removidos dos chats que iniciam ou conversam que estão supervisionando em locatários federados.

- Permissões limitadas: essa função é ideal para membros da equipe que só devem ter acesso supervisionado a usuários restritos. Eles podem iniciar chats com usuários completos ou limitados, mas não podem iniciar chats com usuários restritos. Se um usuário com permissões completas iniciar um chat com um usuário restrito, usuários limitados poderão ser trazidos para a conversa. Esse acesso ocorre porque um usuário com permissões completas está presente para supervisionar a colaboração entre usuários limitados e restritos.

- Permissões restritas: essa função é ideal para usuários que precisam ser supervisionados. Eles só podem iniciar chats com usuários que têm permissões completas. Eles podem participar de qualquer conversa para a qual um usuário com permissões completas os convida. Em casos de chat federados, usuários restritos só podem ser adicionados a chats por um usuário com permissões completas que é do locatário do usuário restrito.

Para definir a função de permissão de chat dos usuários, use a política de **função de permissões do Chat** encontrada em suas opções de política de mensagens no portal de administração do Teams. Você pode usar o PowerShell para definir funções usando a política ChatPermissionRole com os valores Full, Limited ou Restricted. Essa política está em [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).

Funções não podem ser atribuídas a convidados em seu locatário. Os convidados recebem a função limitada.

## <a name="allow-supervised-chat"></a>Permitir chat supervisionado

O chat supervisionado é desabilitado por padrão para seu locatário. Depois de definir funções de permissão de chat para seus usuários, você pode habilitar o chat supervisionado em seu locatário acessando **Configurações do Teams** do **Teams** \> e definindo a política **de permissões de chat baseadas em função** para **Ativar**. Você também pode usar o PowerShell para habilitar o Chat Supervisionado definindo AllowRoleBasedChatPermissions como True. Esse cmdlet está em [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration).

O chat supervisionado deve ser habilitado para todos os usuários no locatário e não pode ser habilitado para apenas uma parte de seus usuários.

**Habilitar o chat**:

Habilite o chat para todos os usuários usando a política de Chat existente disponível no centro de administração do Teams.

**Manter chats supervisionados**:

Depois que o chat supervisionado estiver inicialmente habilitado, você precisará fazer algumas coisas para garantir que os chats em seu ambiente permaneçam supervisionados:

- Atribua funções apropriadas a novos usuários que ingressarem no locatário. Por padrão, os usuários receberão uma função restrita.

- Se um usuário com permissões completas sair ou for removido de um locatário, os chats que eles estavam supervisionando ficarão autônomos. Antes de remover o usuário original, verifique se outro usuário com permissões completas é adicionado a essas conversas para que o chat possa permanecer supervisionado. Depois que o supervisor original for removido, novos participantes não poderão ser adicionados à conversa, mas os participantes atuais podem continuar a se comunicar.
