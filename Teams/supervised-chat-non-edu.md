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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre chats supervisionados para locatários não educacionais em reuniões do Microsoft Teams.
ms.openlocfilehash: a06aa7b9ae24e29a70b3c1a4fc74fae134616b6b
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564179"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chats supervisionados para locatários não educacionais

O chat supervisionado permite que os supervisores designados iniciem chats com qualquer pessoa em sua organização e impede que usuários restritos iniciem novos chats, a menos que um supervisor apropriado esteja presente. Quando a supervisão de chat está habilitada, os supervisores não têm permissão para sair dos chats e outros participantes não têm permissão para removê-los, garantindo que os chats que envolvem usuários restritos sejam supervisionados corretamente.

Essas limitações só são aplicadas a novos chats privados criados após a habilitação total do chat supervisionado. Eles não se aplicam a chats privados, chats de reuniões ou canais existentes.

O chat supervisionado é adaptado para as necessidades da instituição de ensino, mas também está disponível para locatários não educacionais.

> [!NOTE]
> O chat supervisionado protege os novos chats criados depois que o recurso é imposto. Ele não protege os chats existentes.

## <a name="enable-supervised-chat"></a>Habilitar chat supervisionado

> [!NOTE]
> Configure as funções de permissão de chat e as políticas de permissão de chat baseadas em função antes de habilitar o chat para sua instituição para evitar o acesso restrito indesejado do usuário a chats não supervisionados.

**Defina funções de permissão de chat para cada usuário em seu ambiente**:

Para que o chat supervisionado funcione conforme o esperado, cada usuário em seu ambiente precisa receber a função de permissão de chat correta. Há três funções que um usuário pode ter atribuído:

- Permissões completas: essa função deve ser atribuída aos supervisores de chat em seu ambiente. Eles podem iniciar chats com qualquer usuário em seu ambiente. Espera-se que os usuários com permissões completas supervisionem os chats dos quais participam. Eles não podem sair ou ser removidos de chats que iniciam ou chats que estão supervisionando em locatários federados.

- Permissões limitadas: essa função é ideal para membros da equipe que só devem ter acesso supervisionado a usuários restritos. Eles podem iniciar chats com usuários completos ou limitados, mas não podem iniciar chats com usuários restritos. Se um usuário com permissões completas iniciar um chat com um usuário restrito, usuários limitados poderão ser trazidos para a conversa. Esse acesso ocorre porque um usuário com permissões completas está presente para supervisionar a colaboração entre usuários limitados e restritos.

- Permissões restritas: essa função é ideal para usuários que precisam ser supervisionados. Eles só podem iniciar chats com usuários que têm permissões completas. Ele pode participar de qualquer conversa para a qual um usuário com permissões completas o convide. Em casos de chat federados, os usuários restritos só podem ser adicionados a chats por um usuário com permissões completas que são do locatário restrito do usuário.

Para definir a função de permissão de chat dos usuários, use a política de função de permissões de **chat** encontrada nas opções de política de mensagens no portal de administração do Teams. Você pode usar o PowerShell para definir funções usando a política ChatPermissionRole com os valores Completo, Limitado ou Restrito. Essa política está em [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).

As funções não podem ser atribuídas a convidados em seu locatário. Os convidados recebem a função limitada.

## <a name="allow-supervised-chat"></a>Permitir chat supervisionado

O chat supervisionado é desabilitado por padrão para seu locatário. Depois de definir as funções de permissão de chat para seus usuários, você pode habilitar o chat  \> supervisionado em seu locatário acessando as Configurações do **Teams** em toda a organização e definindo a política de permissões de **chat baseadas** em função como **Ativado**. Você também pode usar o PowerShell para habilitar o Chat Supervisionado definindo AllowRoleBasedChatPermissions como True. Esse cmdlet está em [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration).

O chat supervisionado deve ser habilitado para todos os usuários no locatário e não pode ser habilitado para apenas uma parte dos usuários.

**Habilitar chat**:

Habilite o chat para todos os usuários usando a política de Chat existente disponível no Centro de administração do Teams.

**Manter chats supervisionados**:

Depois que o chat supervisionado for habilitado inicialmente, você precisará fazer algumas coisas para garantir que os chats em seu ambiente permaneçam supervisionados:

- Atribua funções apropriadas a novos usuários que ingressem em seu locatário. Por padrão, os usuários receberão uma função restrita.

- Se um usuário com permissões completas sair ou for removido de um locatário, os chats que ele estava supervisionando serão deixados autônomos. Antes de remover o usuário original, certifique-se de que outro usuário com permissões completas seja adicionado a essas conversas para que o chat possa permanecer supervisionado. Depois que o supervisor original é removido, novos participantes não podem ser adicionados à conversa, mas os participantes atuais podem continuar se comunicando.
