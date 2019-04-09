---
title: Presença do usuário no Microsoft Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Os administradores de informações precisam entender sobre a presença em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cffa4e5eef3b5b120e38b103d04adbca08bef0e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517083"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Microsoft Teams

Presença faz parte de um perfil de usuário no Microsoft Teams (e ao longo do Office 365) – e indica a disponibilidade atual do usuário e o status para outros usuários na organização. Por padrão, qualquer pessoa na sua organização usando equipes pode ver ou não a outros usuários estão disponíveis online.

## <a name="presence-states-in-teams"></a>Estados de presença em equipes

Os estados de presença do usuário disponíveis em equipes são:

|Configurado pelo usuário|App configurada|
|:--- |:---|
| ![Presença disponíveis](media/Presence_Available.png) Disponível|![Presença disponíveis](media/Presence_Available.png) Disponível|
|| ![oof disponível](media/Presence_Available_OOF.png) Disponível, ausência temporária |
|  ![Ocupado](media/Presence_Busy.png) Ocupado |  ![Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Ocupado](media/Presence_Busy.png) Em uma chamada|
|| ![Ocupado](media/Presence_Busy.png) Em uma reunião |
|| ![oof ocupado](media/Presence_Busy_OOF.png) Em uma chamada, ausência temporária|
|  ![Não incomodar](media/Presence_DND.png) Não incomodar ||
|| ![Não incomodar](media/Presence_DND.png) Apresentando|
| ![ausente](media/Presence_Away.png) Ausente| ![ausente](media/Presence_Away.png) Ausente|
|| ![ausente](media/Presence_Away.png) vistas ausente última *hora*|
|![ausente](media/Presence_Away.png) Volto logo| |
|| ![ausente](media/Presence_Away.png)  Ausente do trabalho|
|| ![Offline](media/Presence_Offline.png) Offline |
|| ![desconhecido](media/Presence_Unknown.png) Status desconhecido|
||![bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Ausência temporária](media/Presence_OOF.png) Ausência temporária|
|||
 
Os usuários podem definir manualmente seu estado de presença atual para algumas opções e seu estado obtém refletido para todos os outros usuários. Detalhes de presença do usuário adicionais são atualizados também automaticamente com base nos Estados do aplicativo de equipes, Outlook calendário estados (como em uma reunião) ou atividade do usuário (por exemplo, disponível ou ausente) (em uma chamada, apresentando), Estados recuados na lista.

Há um limite de inatividade de 15 minutos, após o qual o estado de presença atual dos usuários será redefinido para ausente.

Os usuários podem especificar que podem ser acessadas pelo (contatá-los substituindo uma configuração não incomodar). Essas configurações estão disponíveis no aplicativo.

## <a name="teams-is-not-skype-for-business"></a>As equipes não for Skype para negócios

As seguintes configurações de administração no Skype para negócios são diferentes em equipes:
- Compartilhamento de presença sempre está habilitada em equipes para usuários na organização. Configuração de privacidade (decidir quem pode ver a presença) não está disponível em equipes.
- Presença compartilhamento com todos (inclusive serviços federados) está sempre habilitada para usuários de equipes. Sua lista de contatos (se eles tinham um SfB) é visível em **gt _ contatos de Chat** ou em **chamadas gt _ contatos**.
- Recursos de cliente não incomodar e inovadora sempre estão habilitados para usuários de equipes.
- Calendário (inclui OOF & outras informações de calendário) integração está sempre habilitada para usuários em equipes se integrado com o Outlook.
- O indicador *ausente desde* (se estiver em um ambiente de duplo com Skype for Business) ou *visto pela última vez* está sempre habilitada para usuários de equipes.

> [!NOTE]
> A capacidade de um administrador de equipes de personalizar essas configurações não é suportada no momento.


## <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Consulte a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença de equipes funciona quando coexistindo com o Skype para negócios. 
