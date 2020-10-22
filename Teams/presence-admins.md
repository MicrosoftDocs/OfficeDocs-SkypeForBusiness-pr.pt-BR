---
title: Presença do usuário no Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Conheça os Estados de presença no Teams e as configurações administrativas do recurso de presença.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fd066fe06126043475a7264b3b2c4501c7ac3ae
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650944"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Teams

A presença faz parte do perfil de um usuário no Microsoft Teams (e em todo o Microsoft 365 ou o Office 365). A presença indica a disponibilidade e o status atuais do usuário para outros usuários. Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online. A presença é atualizada em tempo real nas versões da Web e da área de trabalho quando você atualiza a página no celular.

 > [!Note]
 > Para obter detalhes sobre os perfis de usuário do Team em diferentes plataformas, consulte [recursos do teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="presence-states-in-teams"></a>Estados de presença no Teams

|Usuário configurado|Aplicativo configurado|
|:--- |:---|
| ![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) Disponível|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) Disponível|
|| ![Marca de seleção verde aberta, indica at disponível](media/Presence_Available_OOF.png) Disponível, fora do escritório. Observação: a ausência temporária é definida automaticamente nos períodos de tempo em que o usuário define "respostas automáticas". Se o usuário estiver usando o aplicativo durante esses períodos de tempo, uma dupla presença pode ser mostrada, como "ausência temporária, disponível". |
|  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo vermelho, indica Ocupado em uma chamada](media/Presence_Busy.png) Em uma chamada|
|| ![Círculo vermelho, indica Ocupado em uma reunião](media/Presence_Busy.png) Em uma reunião |
|| ![Círculo vermelho aberto, indica ocupado](media/Presence_Busy_OOF.png) Em uma chamada, ausência temporária|
|  ![Círculo vermelho com linha branca, indica Não Incomodar](media/Presence_DND.png) Não incomodar ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação](media/Presence_DND.png) Em Apresentação|
|| ![Círculo vermelho com linha branca, indica Focado](media/Presence_DND.png) Foco. O foco acontece quando os usuários agendam o tempo de foco em myAnalytics/ideias em seus calendários.|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente|
|| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) Volto Logo| |
|![Círculo cinza com x, indica Offline](media/Presence_Offline.png) Aparecer offline. Em breve no Teams.|![Círculo cinza com x, indica Offline](media/Presence_Offline.png) Modo.  Quando os usuários não se conectarem em nenhum dos seus dispositivos por alguns minutos, eles aparecerão offline. | |
|| ![Círculo cinza aberta, indica status desconhecido](media/Presence_Unknown.png) Status desconhecido|
|| ![Círculo roxo com seta, indica Ausência temporária](media/Presence_OOF.png) Fora do escritório. Fora do escritório é usado quando uma resposta automática é definida. (Disponível somente no Outlook.) |
|||

Os Estados de presença configurados pelo aplicativo são baseados na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação). Quando você estiver no modo de foco com base em seu calendário, o **foco** será o estado que as pessoas veem no Teams. O modo de foco será exibido como **não incomodar** em outros produtos.

Seu estado de presença atual muda para ausente quando você bloqueia seu computador ou quando o computador entra no modo ocioso ou adormecido. Em um dispositivo móvel, seu status de presença muda para ausente sempre que o aplicativo Teams está em segundo plano.

Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença. Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online. Se um estado do usuário estiver definido como não incomodar, o usuário ainda receberá mensagens de chat, mas as notificações de cabeçalho não serão exibidas.

Os usuários recebem chamadas em todos os Estados de presença, exceto para não incomodar, no qual as chamadas recebidas vão para o correio de voz. Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.

Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams. As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o status do usuário estiver definido como não incomodar.

### <a name="dual-presence"></a>Presença dupla

  A maneira como a presença funciona para a maioria dos usuários é motivada pelos eventos no calendário ou eventos do dispositivo, como uma chamada. O usuário pode substituir esse status na interface do usuário, definindo manualmente os Estados, que têm um período de expiração.

## <a name="user-configured-states-expiration"></a>Expiração de Estados configurados pelo usuário

Quando um usuário seleciona um estado de presença específico, ele tem precedência sobre qualquer atualização de atividade do aplicativo. Por exemplo, se um usuário define-se como não incomodar, sua presença permanecerá como não incomodar, mesmo que ela participe de uma reunião ou responda a uma chamada.

Os Estados configurados pelo usuário têm configurações de expiração padrão no Teams, para impedir que os usuários exibam um status que podem não ser relevantes após um período de tempo.

|Estado configurado pelo usuário|Expiração padrão|
|:--- |:---|
| Ocupado|1 dia|
| Não incomodar|1 dia|
| Computadores|7 dias|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configurações de administrador no Teams em comparação com o Skype for Business

As seguintes configurações de administrador do Skype for Business são diferentes no Teams:

- No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização. Privacidade (onde define quem pode ver a presença) a configuração não está disponível no Teams.
- O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams. Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.
- Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.
- A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.
- Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.

> [!NOTE]
> Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Configurações de administrador no Teams em comparação com o Microsoft Outlook

A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.

Se a política do modo de atualização da conta de usuário estiver definida como TeamsOnly, o Outlook conversará com o Microsoft Teams para obter presença. Se a conta de usuário não estiver definida como TeamsOnly, o Outlook conversará com o Skype for Business.

## <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Veja a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como as funções de presença do teams quando sua organização também usam o Skype for Business.
