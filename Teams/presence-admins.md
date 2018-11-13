---
title: Presença do usuário em equipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: Os administradores de informações precisam entender sobre a presença em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7f6ef1e7c20e4cc08d021d30a7b52062f08a2ac
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296331"
---
# <a name="user-presence-in-teams"></a>Presença do usuário em equipes

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
- Presença compartilhamento com todos (inclusive serviços federados) está sempre habilitada para usuários de equipes. Sua lista de contatos (se eles tinham um SfB) está visível em **Chat > Contatos** ou em **chamadas > Contatos**.
- Recursos de cliente não incomodar e inovadora sempre estão habilitados para usuários de equipes.
- Calendário (inclui OOF & outras informações de calendário) integração está sempre habilitada para usuários em equipes se integrado com o Outlook.
- O indicador *ausente desde* (se estiver em um ambiente de duplo com Skype for Business) ou *visto pela última vez* está sempre habilitada para usuários de equipes.
- A definição de um status de presença personalizados não está habilitada para usuários em equipes.

> [!NOTE]
> A capacidade de um administrador de equipes de personalizar essas configurações não é suportada no momento.