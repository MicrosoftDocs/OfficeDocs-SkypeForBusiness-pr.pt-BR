---
title: Presença do usuário no Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Conheça os estados de Presença no Microsoft Teams e as configurações administrativas para o recurso de Presença.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e1c436e6bcd204eb383228a73a115a70ae29e08
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563759"
---
# <a name="user-presence-in-teams"></a>Presença do usuário no Teams

A presença faz parte do perfil de um usuário do Microsoft Teams (e por todo o Microsoft 365 ou o Office 365). A presença indica a disponibilidade e o status atual do usuário para outros usuários. Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online. A presença é atualizada em tempo real nas versões web e desktop quando você atualizar a página no celular. 

 > [!NOTE]
 > Para saber mais sobre os perfis de usuário do Microsoft Teams em diferentes plataformas, confira [recursos do Microsoft Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

 > [!NOTE]
 > O Teams respeita sua configuração de privacidade, portanto, se você habilitou o modo de privacidade, sua presença não estará visível para usuários externos.

## <a name="presence-states-in-teams"></a>Estados de presença no Microsoft Teams


|Usuário configurado|Aplicativo configurado|
|:--- |:---|
| ![Marca de seleção verde sólida, indica Presença Disponível.](media/Presence_Available.png) Disponível|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) Disponível|
|| ![Marca de seleção verde aberta, indica disponível.](media/Presence_Available_OOF.png) Disponível, Ausência Temporária. Observação: a Ausência Temporária é definida automaticamente para os períodos nos quais os usuários configuram as “respostas automáticas”. Se o usuário estiver usando o aplicativo durante esses períodos, uma presença dupla pode ser mostrada, como “Ausência temporária, disponível”. |
|  ![Círculo vermelho sólido, indica Ocupado.](media/Presence_Busy.png) Ocupado |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo vermelho sólido, indica Ocupado em uma chamada.](media/Presence_Busy.png) Em uma chamada|
|| ![Círculo vermelho sólido, indica Ocupado em uma reunião.](media/Presence_Busy.png) Em reunião |
|| ![Círculo vermelho aberto, indica Ocupado.](media/Presence_Busy_OOF.png) Em uma chamada, ausência temporária|
|  ![Círculo vermelho com linha branca, indica Não Incomodar.](media/Presence_DND.png) Não incomodar ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação.](media/Presence_DND.png) Em Apresentação|
|| ![Círculo vermelho com linha branca, indica Focado.](media/Presence_DND.png) Focado. O foco acontece quando os usuários agendam o tempo de foco no MyAnalytics/Insights em seus calendários.|
| ![Ícone de relógio amarelo, indica ausente.](media/Presence_Away.png) Ausente| ![Ícone de relógio amarelo, indica ausente.](media/Presence_Away.png) Ausente|
|| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*|
|![Ícone de relógio amarelo, indica ausente, volto logo.](media/Presence_Away.png) Volto logo| |
|![Círculo cinza com x, indica Offline.](media/Presence_Offline.png) Invisível|![Círculo cinza com x, indica Offline](media/Presence_Offline.png) Desligada. Quando os usuários não estão conectados em nenhum dos seus dispositivos por alguns minutos, eles aparecem invisíveis. |
|| ![Círculo cinza aberto, indica status desconhecido.](media/Presence_Unknown.png) Status desconhecido|
|| ![Círculo púrpura com seta, indica Ausência Temporária.](media/Presence_OOF.png) Ausência Temporária. A Ausência Temporária é usada quando uma resposta automática é definida. |

 > [!NOTE]
 > Para usuários que têm sua caixa de correio hospedada no local, são esperados atrasos de presença de uma hora (máximo).

Estados de presença configurados no aplicativo se baseiam na atividade do usuário (Disponível, Ausente), estados de calendário do Outlook (Em uma reunião) ou estados do aplicativo do Microsoft Teams (Em uma chamada, Em apresentação). Quando você está no modo de Foco baseado em seu calendário, **Foco** será o estado que as pessoas verão no Microsoft Teams. O modo de foco será exibido como **Não incomodar** em outros produtos.

Seu estado de presença atual é alterado para Ausente ao bloquear o seu computador ou quando ele entra no modo de espera ou hibernação. No celular, seu status de presença é alterado para Ausente quando o aplicativo do Microsoft Teams está em segundo plano.

Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença. Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online. Se o estado de um usuário for definido para Não incomodar, o usuário continuará a receber mensagens de chat, mas as notificações em banner não são exibidas.

Os usuários recebem chamadas em todos os estados de presença, exceto no estado Não Incomodar, no qual as chamadas recebidas são encaminhadas para a caixa postal. Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.

Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams. As pessoas com acesso prioritário podem contatar o usuário mesmo quando ele estiver em um estado Não Incomodar.

### <a name="dual-presence"></a>Presença dupla

  A maneira como a presença funciona para a maioria dos usuários é motivada pelos eventos no calendário ou dispositivo, como uma chamada. O usuário pode substituir esse status na IU definindo os estados manualmente, que têm um prazo de expiração.

## <a name="user-configured-states-expiration"></a>Expiração dos estados configurados pelo usuário

Quando um usuário seleciona um estado de presença específico, ele tem precedência sobre qualquer atualização de atividade do aplicativo. Por exemplo, se um usuário se definir como Não incomodar, sua presença permanecerá como Não incomodar mesmo que participe de uma reunião ou atende a uma chamada.

Os estados configurados pelo usuário têm configurações de expiração padrão no Microsoft Teams para impedir que os usuários exibam um status que pode não ser relevante depois de um tempo.

|Estado configurado pelo usuário|Expiração padrão|
|:--- |:---|
| Ocupado|1 dia|
| Não incomodar|1 dia|
| Outros|7 dias|

> [!NOTE]
> Um usuário também pode configurar manualmente uma duração para sua presença. Por exemplo, um usuário pode se definir como Invisível até amanhã pela manhã.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configurações de administrador no Teams em comparação com o Skype for Business

As seguintes configurações de administrador do Skype for Business são diferentes no Teams:

- No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização. A configuração de privacidade (onde você define quem pode ver a presença) não está disponível no Microsoft Teams.
- O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams. Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.
- Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.
- A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.
- Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.

> [!NOTE]
> Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Configurações de administrador no Microsoft Teams em comparação com o Microsoft Outlook

A presença do Microsoft Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior para contatos na mesma organização.

Se a política de modo de atualização da conta do usuário for definida para TeamsOnly, o Outlook conversará com o Microsoft Teams para obter a presença. Se a conta do usuário não estiver definida para TeamsOnly, então o Outlook conversará com o Skype for Business.

## <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Confira [Coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença no Microsoft Teams funciona quando sua organização também usa o Skype for Business.
