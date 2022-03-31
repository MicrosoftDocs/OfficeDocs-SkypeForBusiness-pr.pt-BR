---
title: Usar chats supervisionados
author: SerdarSoysal
ms.author: serdars
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
description: Saiba mais sobre chats supervisionados em Microsoft Teams reuniões.
ms.openlocfilehash: 5027e214de2ee85c2898676b15f4fa04352e1566
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556482"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Chats supervisionados em Microsoft Teams

As instituições de ensino fornecem um espaço digital seguro e saudável para os alunos. O espaço digital inclui emails, reuniões online e chamadas e mensagens em Teams. Para evitar comportamentos de mensagens inadequados, muitas escolas desabilitam o chat privado Teams. Infelizmente, desabilitar o chat também bloqueia a oportunidade para que os professores entre em contato com os alunos em particular para aprendizado personalizado. Com o chat desabilitado, os alunos não podem entrar em contato com os professores quando preferem não postar as mensagens publicamente em equipes de classe.

O chat supervisionado permite que educadores designados iniciem conversas com alunos e impedem que os alunos iniciem novos chats, a menos que um educador apropriado esteja presente. Quando a supervisão de chat está habilitada, os supervisores não têm permissão para sair dos chats e outros participantes não têm permissão para removê-los, garantindo que os chats envolvendo alunos sejam supervisionados corretamente.

Essas limitações só são aplicadas a novos chats privados criados após o chat supervisionado ter sido totalmente habilitado. Eles não se aplicam a chats particulares, chats de reuniões ou canais existentes. Para saber mais sobre as práticas recomendadas para bate-papo de reunião, segurança de canal e manter os alunos seguros, consulte Mantendo os alunos seguros ao [usar](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators) Teams.

> [!Note]
> O chat supervisionado protege os novos chats criados após a aplicação do recurso.  Ele não protege chats existentes.

## <a name="review-use-cases-for-supervised-chats"></a>Revisar casos de uso para chats supervisionados

Os exemplos a seguir são descrições de quando um chat supervisionado é necessário.

- Um acompanhamento 1.1 com um educador quando os alunos não estão confortáveis em compartilhar ou fazer perguntas publicamente.

- Educadores que alcançam 1,1 para um aluno sobre uma atribuição, interação de classe recente (ou falta de) ou outro tópico.

- Discussões de grupo de alunos monitoradas por um educador.

- Permitir que funcionários não docentes conversem com alunos em um ambiente supervisionado.

## <a name="enable-supervised-chat"></a>Habilitar o chat supervisionado

> [!Note]
> Certifique-se de configurar as funções de permissão de chat e as políticas de permissão de chat baseadas em função antes de habilinar o chat para sua instituição para evitar o acesso indesejado de alunos a chats não supervisionados.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definir funções de permissão de chat para cada usuário em seu ambiente

Para que o chat supervisionado funcione conforme esperado, cada usuário em seu ambiente precisa receber a função de permissão de chat correta. Há três funções que um usuário pode ter atribuído:

- *Permissões completas* – Essa função é ideal para educadores que devem ter acesso total a alunos e outros membros da equipe. Eles podem iniciar chats com qualquer usuário em seu ambiente. Espera-se que os usuários com permissões completas supervisionem os chats em que participam. Eles não podem sair ou ser removidos de chats que iniciam ou chats que estão supervisionando em locatários federados.

- *Permissões limitadas* – Essa função é ideal para membros da equipe que só devem ter acesso supervisionado aos alunos e ter acesso total a outros funcionários e educadores. Eles podem iniciar chats com usuários completos ou limitados, mas não podem iniciar chats com usuários restritos. Se um usuário com permissões completas iniciar um chat com um usuário restrito, usuários limitados poderão ser levados para a conversa. Esse acesso acontece porque um usuário com permissões completas está presente para supervisionar a colaboração entre usuários limitados e restritos.

- *Permissões restritas* – Essa função é ideal para alunos que precisam ser supervisionados. Eles só podem iniciar chats com usuários que têm permissões completas. Eles podem participar de qualquer conversa que um usuário com permissões completas iniciar e, em seguida, convidá-lo. Em casos de chat federado, os usuários restritos só podem ser adicionados a chats por um usuário com permissões completas que são do locatário do usuário restrito.

Para definir a função de permissão de chat dos usuários, use a política de função de permissões de **chat**  encontrada nas opções de política de mensagens no portal de Teams de administração. Você pode usar o PowerShell para definir funções usando a política ChatPermissionRole com os valores Full, Limited ou Restricted. Esta política está em CsTeamsMessagingPolicy.

Para saber mais sobre configuração. Teams políticas consulte Teams políticas e pacotes de política para Educação e Atribuir políticas a grandes conjuntos de guias de usuários.

As funções não podem ser atribuídas aos convidados em seu locatário. Os convidados são atribuídos à função limitada.

### <a name="allow-supervised-chat"></a>Permitir chat supervisionado

O chat supervisionado está desabilitado por padrão para seu locatário. Depois de definir funções de permissão de chat para seus usuários, você pode habilitar o chat  &gt; supervisionado em seu locatário, indo para Teams Teams configurações e definindo **a** política de permissões de **chat baseadas** em função como *Ativado.* Você também pode usar o PowerShell para habilitar o Chat Supervisionado definindo AllowRoleBasedChatPermissions como True. Este cmdlet está em CsTeamsClientConfiguration.

O chat supervisionado deve ser habilitado para todos os usuários no locatário e não pode ser habilitado apenas para uma parte de seus usuários.

### <a name="enable-chat"></a>Habilitar o chat

Habilita o chat para todos os usuários usando a política de Chat existente disponível no Teams de administração.

## <a name="maintain-supervised-chats"></a>Manter chats supervisionados

Depois que o chat supervisionado for habilitado inicialmente, você precisará fazer algumas coisas para garantir que os chats em seu ambiente permaneçam supervisionados:

- Atribua funções apropriadas a todos os novos usuários que ingressarem em seu locatário. Por padrão, os usuários receberão uma função restrita.

- Se um usuário com permissões completas sair ou for removido de um locatário, os chats que estavam supervisionando serão deixados sem supervisão. Antes de remover o usuário original, certifique-se de que outro usuário com permissões completas seja adicionado a essas conversas para que o chat possa permanecer supervisionado. Depois que o supervisor original é removido, novos participantes não podem ser adicionados à conversa, mas os participantes atuais podem continuar a se comunicar.

## <a name="related-topics"></a>Tópicos relacionados

[Chats supervisionados para Teams na educação](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
