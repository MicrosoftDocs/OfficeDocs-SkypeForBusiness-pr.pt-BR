---
title: Presença do usuário no Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informações para administradores sobre a presença no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: be40c98a66e5f3023ce375d0a00515832280c7c0
ms.sourcegitcommit: d2bee305a3588f8487bba3396b1825be7a52f6d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38714487"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Teams

A presença faz parte do perfil de um usuário no Microsoft Teams (e durante todo o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários. Por padrão, qualquer pessoa em sua organização que use o Microsoft Teams poderá ver (em pouco tempo) se outros usuários estiverem disponíveis online.

> [!IMPORTANT]
> Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office. A presença funciona bem no Microsoft Teams. Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve estar instalado, mesmo se você estiver executando o Microsoft Teams no modo **somente Teams** . A Microsoft está ciente desse problema e trabalhando para corrigi-lo.

A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.

## <a name="presence-states-in-teams"></a>Estados de presença no Teams

Os Estados de presença do usuário disponíveis no Teams são:

|Configurado pelo usuário|Aplicativo configurado|
|:--- |:---|
| ![Marca de seleção verde estável, indica presença disponível](media/Presence_Available.png) Disponível|![Marca de seleção verde estável, indica presença disponível](media/Presence_Available.png) Disponível|
|| ![Abrir a marca de seleção verde, indica OOF disponível](media/Presence_Available_OOF.png) Disponível, fora do escritório |
|  ![Círculo vermelho sólido, indica ocupado](media/Presence_Busy.png) Executando |  ![Círculo vermelho sólido, indica ocupado](media/Presence_Busy.png) Executando  |
|| ![Círculo vermelho sólido, indica ocupado em uma chamada](media/Presence_Busy.png) Em uma chamada|
|| ![Círculo vermelho sólido, indica ocupado em uma reunião](media/Presence_Busy.png) Em uma reunião |
|| ![Abrir círculo vermelho, indica ocupado](media/Presence_Busy_OOF.png) Em uma chamada, fora do escritório|
|  ![Círculo vermelho com linha branca, indica que não incomodar](media/Presence_DND.png) Não incomodar ||
|| ![Círculo vermelho com linha branca, indica a apresentação](media/Presence_DND.png) Fazendo|
|| ![Círculo vermelho com linha branca, indica foco](media/Presence_DND.png) Foco|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Aparece| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Aparece|
|| ![Ícone de relógio amarelo, indica](media/Presence_Away.png) o último *período* de vista ausente|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) Volto logo| |
|| ![Ícone de relógio amarelo, indica ausente, fora do trabalho](media/Presence_Away.png)  Longe do trabalho|
|| ![Círculo cinza com x, indica offline](media/Presence_Offline.png) Modo |
|| ![Abrir círculo cinza, indica o status desconhecido](media/Presence_Unknown.png) Status desconhecido|
||![Abrir círculo vermelho com linha diagonal, indica bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Círculo roxo com seta, indica ausência temporária](media/Presence_OOF.png) Fora do escritório|
|||
 
Os usuários podem definir manualmente o estado de presença atual para algumas opções, e seu estado é refletido para todos os outros usuários. Mais detalhes de presença do usuário também são atualizados automaticamente. As alterações são baseadas na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação), para os Estados que são recuados na lista. Há um tempo limite de inatividade de 15 minutos, após o qual um estado de presença atual é redefinido para ausente.

Os usuários recebem todas as mensagens de chat enviadas para eles no Teams independentemente do estado de presença deles. Se um usuário estiver offline quando alguém enviar uma mensagem, a mensagem de chat será exibida no Microsoft Teams na próxima vez que o usuário estiver online. Se um usuário estiver em um estado de não incomodar, o usuário ainda receberá mensagens de chat, mas uma notificação de banner não será exibida.

Os usuários recebem chamadas em todos os Estados de presença, exceto para os Estados não incomodar, nos quais as chamadas recebidas são entregues ao correio de voz. Se o destinatário bloqueou o chamador, a chamada não será entregue e o chamador verá a presença do destinatário como offline.

Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando a**privacidade** de **configurações** > no Teams. As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o usuário estiver em um estado não incomodar.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configurações de administrador no Teams em comparação com o Skype for Business

As seguintes configurações de administração do Skype for Business são diferentes no Teams:

- No Teams, o compartilhamento de presença sempre é habilitado para os usuários da organização. Privacidade (onde você define quem pode ver a presença) não está disponível no Microsoft Teams.
- O compartilhamento de presença com todos (incluindo serviços federados) sempre está habilitado para usuários do teams. Sua lista de contatos (se ela já tinha uma no Skype for Business) fica visível em **contatos de Chat >** ou em **chamadas > contatos**.
- Cliente não incomodar e recursos revolucionários sempre são habilitados para usuários do teams.
- Calendário (inclui ausência temporária e outras informações do calendário) a integração sempre é habilitada para os usuários quando o Microsoft Teams está integrado ao Outlook.
- O indicador mais *recente* ou *ausente já* está habilitado para usuários do teams se a organização também usa o Skype for Business.

> [!NOTE]
> Não há suporte para a capacidade de um administrador de equipe personalizar essas configurações no momento.

## <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Veja a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como as funções de presença do teams quando sua organização também usam o Skype for Business.
