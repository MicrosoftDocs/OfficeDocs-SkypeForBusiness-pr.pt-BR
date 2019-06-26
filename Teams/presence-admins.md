---
title: Presença do usuário no Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Os administradores de informações precisam compreender a presença no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222089"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Teams

A presença faz parte do perfil de um usuário no Microsoft Teams (e durante todo o Office 365) – e indica a disponibilidade e o status atuais do usuário para outros usuários da organização. Por padrão, qualquer pessoa em sua organização que use o Microsoft Teams pode ver, em quase tempo, se outros usuários estão ou não disponíveis online.

## <a name="presence-states-in-teams"></a>Estados de presença no Teams

Os Estados de presença do usuário disponíveis no Teams são:

|Configurado pelo usuário|Aplicativo configurado|
|:--- |:---|
| ![Marca de Chek verde estável, indicando presença disponível](media/Presence_Available.png) Disponível|![Marca de Chek verde estável, indicando presença disponível](media/Presence_Available.png) Disponível|
|| ![Abrir marca Chek verde, indicando OOF disponível](media/Presence_Available_OOF.png) Disponível, fora do escritório |
|  ![Círculo vermelho sólido, indicando ocupado](media/Presence_Busy.png) Executando |  ![Círculo vermelho sólido, indicando ocupado](media/Presence_Busy.png) Executando  |
|| ![Círculo vermelho sólido, que indica ocupado em uma chamada](media/Presence_Busy.png) Em uma chamada|
|| ![Círculo vermelho sólido, que indica ocupado em uma reunião](media/Presence_Busy.png) Em uma reunião |
|| ![Abrir círculo vermelho, indicando OOF indisponível](media/Presence_Busy_OOF.png) Em uma chamada, fora do escritório|
|  ![Círculo vermelho com linha branca, indicando não incomodar](media/Presence_DND.png) Não incomodar ||
|| ![Círculo vermelho com linha branca, indicando a apresentação](media/Presence_DND.png) Fazendo|
| ![Ícone de relógio amarelo, indicando ausente](media/Presence_Away.png) Aparece| ![Ícone de relógio amarelo, indicando ausente](media/Presence_Away.png) Aparece|
|| ![Ícone de relógio amarelo, que](media/Presence_Away.png) indica o último *horário* visto ausente|
|![Ícone de relógio amarelo, indicando ausente, volto logo](media/Presence_Away.png) Volto logo| |
|| ![Ícone de relógio amarelo, indicando ausente, fora do trabalho](media/Presence_Away.png)  Longe do trabalho|
|| ![Círculo cinza com x, indicando offline](media/Presence_Offline.png) Modo |
|| ![Abrir círculo cinza, indicando o status desconhecido](media/Presence_Unknown.png) Status desconhecido|
||![Abrir círculo vermelho com linha diagonal, indicando bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Círculo roxo com seta, indicando ausência temporária](media/Presence_OOF.png) Fora do escritório|
|||
 
Os usuários podem definir manualmente o estado de presença atual para algumas opções, e seu estado é refletido para todos os outros usuários. Detalhes adicionais de presença do usuário também são atualizados automaticamente com base na atividade do usuário (como disponível ou ausente), os Estados do calendário do Outlook (como em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação), para os Estados que são recuados na lista.

Há um tempo limite de inatividade de 15 minutos, após o qual o estado de presença atual dos seus usuários será redefinido para ausente.

Os usuários podem especificar quem pode interromper (entre em contato com eles substituindo uma configuração não incomodar). Essas configurações estão disponíveis no aplicativo.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configurações de administrador no Teams em comparação com o Skype for Business

As seguintes configurações de administração do Skype for Business são diferentes no Teams:

- No Teams, o compartilhamento de presença sempre é habilitado para os usuários da organização. Privacidade (decidindo quem pode ver a presença) a configuração não está disponível no Microsoft Teams.
- O compartilhamento de presença com todos (incluindo serviços federados) sempre está habilitado para usuários do teams. Sua lista de contatos (se ela já tinha uma no Skype for Business) fica visível em **contatos de Chat >** ou em **chamadas > contatos**.
- Cliente não incomodar e recursos revolucionários sempre são habilitados para usuários do teams.
- Calendário (inclui ausência temporária e outras informações do calendário) a integração sempre é habilitada para usuários do Teams, se integradas ao Outlook.
- A *última vista* ou *ausente desde* (se em um ambiente duplo com o Skype for Business) indicador sempre é habilitado para usuários do teams.

> [!NOTE]
> Não há suporte para a capacidade de um administrador de equipe personalizar essas configurações no momento.

## <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Veja a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como as funções de presença de equipes são coexistentes com o Skype for Business. 
