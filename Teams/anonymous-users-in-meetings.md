---
title: Gerenciar o acesso anônimo de participantes às reuniões do Teams (administradores de TI)
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Para profissionais de TI – saiba como funciona a participação anônima de reunião no Microsoft Teams.
ms.openlocfilehash: fe4dbec2bc606838bd5cafbaec5ef9d9ecdd8a88
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948680"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a>Gerenciar o acesso anônimo de participantes às reuniões do Teams (administradores de TI)

Os participantes anônimos em reuniões hospedadas pela sua organização são aqueles que não podem ser verificados. Isso pode incluir:

- Pessoas que não estão conectados ao Teams com uma conta corporativa ou de estudante 
- Pessoas de organizações não confiáveis (conforme configurado no [acesso externo](manage-external-access.md)) e de organizações em que você confia, mas que não confiam em sua organização.

A junção de reunião anônima é controlada por uma configuração de nível de organização e políticas de nível de usuário. Para que a junção de reunião anônima funcione:
- Os **usuários anônimos podem ingressar em uma** configuração de reunião do Teams (nível da organização) deve ser ativada.
- O organizador da reunião deve receber uma política de reunião do Teams em **que as pessoas anônimas que ingressarem em um** controle de reunião estão ativadas.

A junção anônima é ativada por padrão para a organização e na política de reunião global padrão.

Observe que, se a junção anônima estiver habilitada, as políticas de lobby afetarão a forma como os participantes anônimos se juntam às reuniões. Para obter detalhes, confira [Controle que pode ignorar o lobby da reunião no Microsoft Teams](who-can-bypass-meeting-lobby.md).

#### <a name="meetings-with-trusted-organizations"></a>Reuniões com organizações confiáveis

Quando você configura organizações confiáveis para reuniões externas e chat, os participantes da reunião dessas organizações podem ser considerados anônimos se as configurações de acesso externo não estiverem configuradas corretamente para ambas as organizações. Para obter detalhes, consulte [organizações confiáveis para reuniões externas e chat](manage-external-access.md).

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>Gerenciar a junção de reunião anônima para a organização

A configuração de junção de reunião anônima no nível da organização deve ser ativada para que qualquer pessoa na organização crie reuniões que permitam participantes anônimos.

> [!Important]
> Os **participantes anônimos podem ingressar em uma** configuração de organização de reunião será removido no futuro. Recomendamos deixar essa configuração **Ativar** e usar o **controle de política de reunião permitir que pessoas anônimas ingressem em um** controle de política de reunião no nível do usuário da reunião para permitir ou impedir a junção anônima da reunião.

Para configurar a junção de reunião anônima para a organização
1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).

1. Na navegação à esquerda, vá para **Encontros** > **Configurações de reunião**.

1. Em **Participantes**, defina **Os participantes anônimos podem participar de uma reunião** para **Ativar** (recomendado) ou **Desativar**.

    ![Captura de tela das configurações dos participantes para reuniões no centro de administração.](media/meeting-settings-participants.png "Captura de tela das configurações dos participantes das reuniões do Teams no centro de administração do Microsoft Teams")

1. Selecione **Salvar**.

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>Gerenciar quais organizadores de reunião podem permitir a junção anônima da reunião

Você pode controlar quais usuários ou grupos podem hospedar reuniões que incluem participantes anônimos. Para fazer isso, atribua uma política de reunião com a junção anônima de reunião ativada a cada organizador da reunião que precisa sediar reuniões com participantes anônimos.

Para configurar a junção de reunião anônima para organizadores de reunião específicos
1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).

1. Na navegação à esquerda, acesse **Políticas** de **Reunião de Reuniões** > .

1. Selecione a política que você deseja modificar.

1. Definir **Permitir que pessoas anônimas participem de uma reunião** para **On**.

1. Selecione **Salvar**.

As alterações nas políticas de reunião podem levar até 24 horas para entrar em vigor.

## <a name="configure-anonymous-meeting-join-using-powershell"></a>Configurar a junção de reunião anônima usando o PowerShell

Você pode controlar se os participantes anônimos podem participar de reuniões usando:

- O `-DisableAnonymousJoin` parâmetro em [Set-CsTeamsMeetingConfiguration](/powershell/module/skype/set-csteamsmeetingconfiguration) para configurar a configuração do nível da organização. (Recomendamos deixar esse conjunto como False e usar Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting para controlar a junção anônima no nível de usuário ou grupo.)
- O `-AllowAnonymousUsersToJoinMeeting` parâmetro em [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para configurar uma política de reunião no nível do usuário

Para permitir que participantes anônimos participem de reuniões, você deve configurar ambos para permitir a junção anônima definindo os seguintes valores:

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin` definido como **$false**
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting` definido como **$true** para os organizadores da reunião relevantes

## <a name="block-anonymous-join-for-specific-client-types"></a>Bloquear a junção anônima para tipos de cliente específicos

Quando os participantes anônimos podem participar de reuniões, eles podem usar o cliente do Teams ou um cliente personalizado criado usando [Serviços de Comunicação do Azure](/azure/communication-services/). 

Os administradores podem bloquear qualquer um desses tipos de cliente usando o `-BlockedAnonymousJoinClientTypes` parâmetro em [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes).

## <a name="anonymous-participants-meeting-experience"></a>Experiência de reunião de participantes anônimos

Os participantes anônimos não têm todos os mesmos recursos que outros participantes da reunião. Por exemplo, participantes anônimos:

- Não tenha acesso ao chat da reunião antes e depois da reunião
- Não tenha acesso a cartões de perfil (cartões de perfil no Microsoft 365 - Suporte da Microsoft)

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>Como os participantes anônimos interagem com aplicativos em reuniões

Por padrão, a configuração para permitir que participantes anônimos interajam com aplicativos em reuniões está habilitada.

Para configurar o acesso ao aplicativo para participantes anônimos da reunião

1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).

1. Na navegação à esquerda, vá para **Encontros** > **Configurações de reunião**.

1. Em **Participantes**, definir  **participantes anônimos pode interagir com aplicativos em reuniões** como **Ativado** ou **Desativado**.

Você também pode controlar isso com o PowerShell usando `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers`.

Os participantes anônimos herdam a política de permissão de aplicativos do Teams global (padrão em toda a organização). Os participantes anônimos podem interagir com aplicativos em reuniões do Teams desde que o aplicativo esteja habilitado nessa política e **os participantes anônimos possam interagir com aplicativos em reuniões** está **Ativado**.

Observe que os participantes anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos.

## <a name="related-topics"></a>Tópicos relacionados

[Ingressar em uma reunião sem uma conta do Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Usando o Centro de administração do Microsoft Teams para configurar a política em toda a organização](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[Os participantes externos recebem "Entre no Teams para ingressar ou entre em contato com o organizador da reunião"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[Atribuir políticas no Teams – introdução](policy-assignment-overview.md)