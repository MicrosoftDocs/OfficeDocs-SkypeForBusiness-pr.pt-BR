---
title: Controlar quem pode ignorar o lobby da reunião no Microsoft Teams
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
description: Aprenda a usar o lobby da reunião no Microsoft Teams para permitir que apenas determinados participantes da reunião participem diretamente da reunião.
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392694"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>Controlar quem pode ignorar o lobby da reunião no Microsoft Teams

O lobby da reunião do Teams é uma maneira de impedir que determinados tipos de participantes da reunião participem de uma reunião até que um organizador, co-organizador ou apresentador os admita. Quando um participante vai ao lobby, organizadores, co-organizadores e apresentadores são notificados e podem optar por admiti-los na reunião ou não.

Usando as configurações de lobby no centro de administração do Teams, você pode criar padrões para quais tipos de participantes da reunião são capazes de ignorar o lobby e quais participantes devem esperar lá até serem admitidos na reunião. Você pode controlar como os seguintes tipos de participantes interagem com o lobby:

- Organizadores e co-organizadores da reunião
- Pessoas em sua organização
- Convidados
- Pessoas em organizações confiáveis
- Participantes anônimos

As identidades das pessoas que participam de reuniões são verificadas pelo Microsoft 365, a menos que o participante seja anônimo. Os participantes anônimos não podem ser verificados.

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>Pré-requisitos para reunião com pessoas fora de sua organização

Há várias configurações no Teams que controlam se pessoas fora da organização podem interagir com o Teams. As seguintes configurações devem ser habilitadas para pessoas fora da organização ingressarem em reuniões:

- [O acesso de convidado no Teams](guest-access.md) deve ser habilitado para que os convidados possam participar de reuniões.
- [O acesso externo](manage-external-access.md) deve ser habilitado para que pessoas em organizações confiáveis participem de reuniões. Uma confiança mútua entre sua organização e a organização externa deve ser configurada e o organizador da reunião em sua organização, bem como qualquer participante da organização externa, deve ser habilitado para acesso externo.
- Os **usuários Anônimos podem ingressar em uma** configuração de reunião (nível da organização) e a política de reunião (para o organizador que está criando a reunião) devem estar **ativados** para que os participantes anônimos participem de reuniões.

Se alguma dessas configurações estiver desativada, esse tipo de participante externo não poderá participar de reuniões independentemente das configurações de lobby.

## <a name="overview-of-lobby-settings-and-policies"></a>Visão geral das configurações e políticas de lobby

A tabela a seguir mostra as políticas de reunião do Teams que afetam a forma como os participantes da reunião interagem com o lobby.

|Configuração|Descrição|
|:------|:----------|
|**Usuários anônimos e chamadores discadas podem iniciar uma reunião**|Essa é uma política por organizador que permite reuniões sem líder. Essa configuração controla se participantes anônimos e usuários discados podem participar da reunião sem um participante verificado presente. Essa configuração só se aplica quando **Quem pode ignorar o lobby** é definido como **Todos**. Se os **usuários Anônimos puderem ingressar em uma** organização de reunião ou a configuração da reunião estiver **desativada**, essa configuração só se aplicará aos chamadores discados. Por padrão, essa configuração é desativada para evitar possíveis abusos de seus links de reunião por usuários anônimos. <br><br> Enquanto **Estiverem desativados**, participantes anônimos e usuários discados aguardarão no lobby até que um participante verificado (incluindo um organizador discado) participe da reunião, momento em que eles serão automaticamente admitidos. Depois que a reunião for iniciada, participantes anônimos e usuários discados ingressarão na chamada automaticamente, mesmo que o organizador saia. <br><br> Se essa configuração for **Ativada**, os participantes anônimos e discados poderão iniciar e ingressar na reunião sem um participante verificado presente.|
|**Pessoas discagem pode ignorar o lobby**|Esta é uma política por organizador. Essa configuração controla se as pessoas que discam por telefone participam da reunião diretamente ou esperam no lobby. Quando essa configuração estiver **Desligada**, os usuários discados esperarão no lobby até que um organizador, co-organizador ou apresentador participe da reunião e os admita. Quando essa configuração estiver **Ativada**, os usuários discados ingressarão automaticamente na reunião sem passar pelo lobby. (Se **usuários anônimos e chamadores discadas puderem iniciar uma reunião** estiver **desativado**, eles esperarão no lobby até que a reunião comece.)|
|**Quem pode ignorar o lobby**|Esta é uma política por organizador. Essa configuração controla quais tipos de participantes (exceto aqueles que discam por telefone) participam diretamente de uma reunião e quais tipos de participantes esperam no lobby até serem admitidos por um organizador, co-organizador ou apresentador.|

A tabela a seguir mostra como cada opção para **quem pode ignorar a política de lobby** afeta cada *tipo de participante da reunião*.

|Valor da política:|Todos|Pessoas da minha organização e organizações confiáveis|Pessoas na minha organização e convidados|Pessoas da minha organização|Somente pessoas que foram convidadas|Apenas organizadores e co-organizadores|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*Organizadores e co-organizadores*|Ignorar|Ignorar|Ignorar|Ignorar|Ignorar|Ignorar|
|*Pessoas na organização*|Ignorar|Ignorar|Ignorar|Ignorar|Pessoas que foram enviados ou encaminhados um convite ignorarão; outros esperam no lobby|Lobby|
|*Convidados*|Ignorar|Ignorar|Ignorar|Lobby|Pessoas que foram enviados ou encaminhados um convite ignorarão; outros esperam no lobby|Lobby|
|*Pessoas em organizações confiáveis*|Ignorar|Ignorar|Lobby|Lobby|Pessoas que foram enviados ou encaminhados um convite ignorarão; outros esperam no lobby|Lobby|
|*Participantes anônimos*|Ignorar|Lobby|Lobby|Lobby|Lobby|Lobby|

**Somente as pessoas que foram convidadas** se aplicam apenas aos participantes verificados que receberam um convite ou para quem um convite foi encaminhado. Os usuários adicionados como parte de um grupo de distribuição aguardarão no lobby.

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>Escolha quem pode ignorar o lobby em reuniões hospedadas pela sua organização

Você pode configurar as configurações e as políticas descritas acima no centro de administração do Teams. Confira as seções abaixo para obter diretrizes sobre qual configuração escolher para diferentes circunstâncias. Para obter informações sobre como funcionam as políticas de reunião, consulte [Gerenciar políticas de reunião no Microsoft Teams](/microsoftteams/meeting-policies-overview).

> [!Important]
> Os organizadores da reunião podem alterar os valores padrão escolhidos para o **Pessoas discagem podem ignorar o lobby** e **Quem pode ignorar as configurações do lobby**. Se você precisar impor essas configurações a um valor específico, poderá usar um modelo de reunião ou um rótulo de confidencialidade (Teams Premium necessário).  Para obter mais informações, consulte [Configurar o lobby de reunião do Microsoft Teams para reuniões confidenciais](configure-lobby-sensitive-meetings.md).

Para definir políticas de junção de reunião e lobby
1. No centro de administração do Teams, expanda **Reuniões** e selecione **Políticas de reunião**.
1. Selecione a política que você deseja atualizar.
1. Nas seções **Participante & convidados** , atualize as configurações que você deseja alterar:
   - **Permitir que pessoas anônimas participem de uma reunião**
   - **Permitir que pessoas anônimas iniciem uma reunião**
   - **Admitir automaticamente pessoas** (quem pode ignorar o lobby)
   - **Os usuários de discagem podem ignorar o lobby**

    ![Captura de tela mostrando a política de ingresso e lobby da reunião no centro de administração do Teams.](media/meeting-join-and-lobby-tac-settings.png)
1. Selecione **Salvar**.

Observe que as alterações podem levar até 24 horas para entrar em vigor.

Se você quiser permitir o acesso anônimo à reunião, certifique-se de que os **usuários anônimos possam ingressar em uma** configuração de reunião também está ativada.

Para definir a configuração de reunião em toda a organização para junção de reunião anônima
1. No centro de administração do Teams, expanda **Reuniões** e selecione **Configurações de reunião**.
1. Na seção **Participantes** , defina **Usuários anônimos podem participar de uma reunião** para **Ativar** ou **Desativar**.
    ![Captura de tela mostrando as configurações de junção e lobby da reunião no centro de administração do Teams.](media/anonymous-users-can-join-meetings-org-setting.png)
1. Selecione **Salvar**.

## <a name="control-access-to-meetings-by-anonymous-participants"></a>Controlar o acesso a reuniões por participantes anônimos

Os participantes anônimos são anônimos porque não estão conectados a uma conta que pode ser verificada pelo Microsoft 365. Isso pode incluir:

- Pessoas que não estão conectados ao Microsoft 365 com uma conta corporativa ou escolar 
- Pessoas de organizações não confiáveis (conforme configurado no [acesso externo](manage-external-access.md)).
- Pessoas de organizações em que você confia, mas que não confiam em sua organização

Se você quiser impedir que os participantes anônimos participem completamente da reunião, você pode desativar os **usuários anônimos que podem ingressar em uma** configuração de reunião em toda a organização da reunião. Você também pode desabilitar a junção anônima para organizadores de reunião específicos usando os **usuários Anônimos pode ingressar em uma política de reunião** .

Se você quiser que as pessoas que se juntam anonimamente aguardem no lobby, você pode definir **quem pode ignorar a política de reunião do lobby** para qualquer configuração, exceto **Todos**. (Essa configuração não afeta as pessoas discando por telefone.)

Por padrão, os **usuários anônimos e os chamadores de discagem podem iniciar uma** política de reunião **desativada**. Isso significa que participantes anônimos e pessoas que ligam por telefone sempre esperarão no lobby se um participante verificado ainda não tiver iniciado a reunião. Embora você possa ativar essa configuração se houver circunstâncias em que você deseja permitir que participantes anônimos e pessoas que ligam por telefone iniciem reuniões, recomendamos que você a deixe de fora.  Quando a configuração está ativada, pessoas com contas não verificadas podem iniciar reuniões, inclusive usando o link de reunião para ter reuniões em horários não agendados.

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>Controlar o acesso a reuniões por pessoas discando por telefone

Por padrão, o **Pessoas discagem pode ignorar a política de lobby** está **Desativado**, mas os organizadores da reunião podem alterar isso quando configurarem a reunião. Você pode alterar o padrão atualizando o **Pessoas discagem em pode ignorar a política de lobby** ou você pode impor um valor específico usando um modelo de reunião.

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>Controlar o acesso a reuniões por convidados e pessoas de organizações confiáveis

Há dois tipos de pessoas fora de sua organização que podem participar de reuniões como participantes verificados:

- Convidados – pessoas que têm uma [conta de colaboração B2B do Azure Active Directory (Azure AD)](/azure/active-directory/external-identities/what-is-b2b) em sua organização
- Usuários de acesso externo – pessoas que têm contas Azure AD em uma organização confiável definida no [acesso externo do](manage-external-access.md) Teams

Se você quiser que todos os participantes da reunião verificados de fora de sua organização aguardem no lobby, você pode definir quem pode ignorar a política de lobby para **Pessoas na minha organização** ou **somente organizadores e co-organizadores** (desde que um convidado não seja o organizador ou co-organizador). Se você quiser que apenas pessoas de organizações confiáveis (usuários de acesso externo) aguardem no lobby, você pode escolher **Pessoas na minha organização e convidados**.

## <a name="control-access-to-meetings-by-people-without-invitations"></a>Controlar o acesso a reuniões por pessoas sem convites

Se você quiser permitir apenas pessoas que têm convites para participar de reuniões diretamente e fazer com que todos os outros participantes aguardem no lobby, defina **Quem pode ignorar o lobby** **para somente pessoas que foram convidadas**. (Pessoas convidados por meio da lista de distribuição não estão incluídos.)

As **únicas pessoas que foram convidadas** incluem participantes verificados para os quais o convite foi encaminhado, não apenas aqueles convidados diretamente pelo organizador. Ele não inclui pessoas que têm o link de junção da reunião, mas não o convite em si e participantes não verificados (anônimos). Eles devem esperar no saguão.

Observe que os organizadores da reunião podem desabilitar o encaminhamento do convite da reunião se desejarem apenas que as pessoas diretamente convidadas por eles participem da reunião.

## <a name="control-access-to-meetings-by-non-organizers"></a>Controlar o acesso a reuniões por não organizadores

Se você tiver reuniões em que informações confidenciais sejam compartilhadas ou que estejam sujeitas a requisitos regulatórios, talvez você queira que todos os participantes aguardem no lobby até que sejam admitidos por um organizador ou co-organizadores da reunião. Nesse caso, você pode definir **Quem pode ignorar o lobby** apenas para **organizadores e co-organizadores**.

Como **Quem pode ignorar o lobby** apenas define um padrão que os organizadores da reunião podem alterar, considere impor o valor com um rótulo de confidencialidade ou um modelo de reunião se você tiver requisitos de conformidade nessa área. Para obter mais informações, consulte [Configurar o lobby de reunião do Microsoft Teams para reuniões confidenciais](configure-lobby-sensitive-meetings.md).

## <a name="set-meeting-policies-by-using-powershell"></a>Definir políticas de reunião usando o PowerShell

Você pode definir as políticas de reunião descritas neste artigo usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) PowerShell com os seguintes parâmetros:

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) para controlar se usuários anônimos podem participar de reuniões
- [-Permitir quePSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) controle se as pessoas discando por telefone podem ignorar o lobby
- [-AutoAdmitidoUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) para controlar quem pode ignorar o lobby

## <a name="related-topics"></a>Tópicos relacionados

[Ingressar em uma reunião sem uma conta do Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Usando o Centro de administração do Microsoft Teams para configurar a política em toda a organização](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[Os participantes externos recebem "Entre no Teams para ingressar ou entre em contato com o organizador da reunião"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)
