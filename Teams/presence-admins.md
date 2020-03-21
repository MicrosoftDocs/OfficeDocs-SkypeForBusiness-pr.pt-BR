---
title: Presença do usuário no Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informações para administradores sobre a Presença no Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863192"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Teams

A presença faz parte do perfil de usuário do Microsoft Teams (e em todo o Office 365) que indica a disponibilidade atual do usuário e o status para outros usuários. Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online.

> [!IMPORTANT]
> Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office. A presença funciona bem no Microsoft Teams. Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve ser instalado, mesmo que você esteja executando o Teams no modo **Somente Teams**. A Microsoft está ciente desse problema e trabalhando para corrigi-lo.

A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.

## <a name="presence-states-in-teams"></a>Estados de presença no Teams

Os estados de presença de usuário disponíveis no Teams são:

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
 
Os usuários podem definir manualmente seu estado de presença atual para algumas opções e seu estado é refletido para todos os outros usuários. Mais detalhes de presença do usuário também são atualizados automaticamente. As alterações se baseiam na atividade do usuário (Disponível, Ausente), estados de calendário do Outlook (Em uma reunião) ou estados do aplicativo Teams (Em uma chamada, Em apresentação) para estados que estão recuados na lista. Há um limite de tempo de inatividade de 15 minutos, após o qual um estado de presença atual é redefinido para Ausente.

Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença. Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online. Se um usuário estiver no estado Não Incomodar, o usuário ainda receberá mensagens de chat, mas as notificações por faixa não serão exibidas.

Os usuários recebem chamadas em todos os estados de presença, exceto nos estados Não Incomodar, nos quais as chamadas recebidas são encaminhadas para a caixa postal. Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.

Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams. As pessoas com acesso prioritário podem contatar o usuário mesmo quando ele estiver em um estado Não Incomodar.

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
