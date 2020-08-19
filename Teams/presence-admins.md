---
title: Presença do usuário no Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Conheça os Estados de presença no Teams, bem como as configurações administrativas do recurso de presença.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00ca1a2d7a00b4aa827cfb5a989e31b54b83fbeb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803903"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Teams

A presença faz parte do perfil de um usuário no Microsoft Teams (e em todo o Microsoft 365 ou o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários. Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online.

A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.

## <a name="presence-states-in-teams"></a>Estados de presença no Teams

|Usuário configurado|Aplicativo configurado|
|:--- |:---|
| ![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) Disponível|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) Disponível|
|| ![Marca de seleção verde aberta, indica at disponível](media/Presence_Available_OOF.png) Disponível, Ausência Temporária |
|  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo vermelho, indica Ocupado em uma chamada](media/Presence_Busy.png) Em uma chamada|
|| ![Círculo vermelho, indica Ocupado em uma reunião](media/Presence_Busy.png) Em uma reunião |
|| ![Círculo vermelho aberto, indica ocupado](media/Presence_Busy_OOF.png) Em uma chamada, ausência temporária|
|  ![Círculo vermelho com linha branca, indica Não Incomodar](media/Presence_DND.png) Não incomodar ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação](media/Presence_DND.png) Em Apresentação|
|| ![Círculo vermelho com linha branca, indica Focado](media/Presence_DND.png) Focado|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente|
|| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) Volto Logo| |
|| ![Ícone de relógio amarelo, indica ausente do trabalho](media/Presence_Away.png)  Ausente do Trabalho|
|| ![Círculo cinza com x, indica Offline](media/Presence_Offline.png) Offline |
|| ![Círculo cinza aberta, indica status desconhecido](media/Presence_Unknown.png) Status desconhecido|
||![Círculo vermelho aberto com linha diagonal, indica bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Círculo roxo com seta, indica Ausência temporária](media/Presence_OOF.png) Ausência Temporária|
|||

Os Estados de presença configurados pelo aplicativo são baseados na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação). Observe que, quando você estiver no modo de foco com base em seu calendário, o foco será o estado que as pessoas veem no Teams, mas mostrarão como não incomodar em outros produtos.

Seu estado de presença atual muda para ausente quando você bloqueia seu computador ou quando ele entra no modo ocioso ou adormecido. No celular, seu status de presença muda para ausente sempre que o aplicativo Teams está em segundo plano.

Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença. Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online. Se um usuário estiver em não incomodar, o usuário ainda receberá mensagens de chat, mas as notificações de cabeçalho não serão exibidas.

Os usuários recebem chamadas em todos os Estados de presença, exceto para não incomodar, no qual as chamadas recebidas vão para o correio de voz. Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.

Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams. As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o usuário estiver em não incomodar.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configurações de administrador no Teams em comparação com o Skype for Business

As seguintes configurações de administrador do Skype for Business são diferentes no Teams:

- No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização. A configuração de privacidade (onde você define quem pode ver a presença) não está disponível no Teams.
- O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams. Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.
- Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.
- A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.
- Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.

> [!NOTE]
> Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.

## <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Confira [Coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença no Teams funciona quando sua organização também usa o Skype for Business.
