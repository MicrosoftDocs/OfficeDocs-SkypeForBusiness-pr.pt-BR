---
title: Gerenciar políticas de reunião para participantes e convidados
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Saiba como gerenciar as configurações de política de reunião no Teams para participantes e convidados.
ms.openlocfilehash: 46db9b7f5a1fae40d3f46bad156e318a3e677d07
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706618"
---
# <a name="meeting-policy-settings---participants--guests"></a>Configurações de política de reunião - Participantes e convidados

<a name="bkmeetingparticipants"> </a>

Essas configurações controlam quais participantes da reunião aguardam no lobby antes de serem admitidos na reunião e o nível de participação permitido em uma reunião.

- [Permitir que pessoas anônimas ingressem em uma reunião](#let-anonymous-people-join-a-meeting)
- [Permitir que pessoas anônimas iniciem uma reunião](#let-anonymous-people-start-a-meeting)
- [Admitir pessoas automaticamente](#automatically-admit-people)
- [Permitir que os usuários de acesso telefônico ignorem o lobby](#allow-dial-in-users-to-bypass-the-lobby)
- [Legendas ao vivo](#live-captions)
- [Chat em reuniões](#chat-in-meetings)

> [!NOTE]
> As opções para ingressar em uma reunião variam, dependendo das configurações de cada grupo do Teams e do método de conexão. Se o seu grupo tiver audioconferência e a usar para se conectar, confira [Audioconferência](/microsoftteams/audio-conferencing-in-office-365). Se o seu grupo do Teams não tiver audioconferência, confira [Participar de uma reunião do Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Permitir que pessoas anônimas ingressem em uma reunião

Essa configuração por organizador permite que qualquer pessoa ingresse em reuniões como um usuário anônimo selecionando o link no convite da reunião. Para saber mais, consulte [Ingressar em uma reunião sem uma conta do Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). A capacidade dos usuários anônimos de ingressar em reuniões também são controladas no nível da sua organização, a configuração mais restritiva será eficaz. Para saber mais, confira [Como usar o centro de administração do Microsoft Teams para configurar a política em toda a organização](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Permitir que pessoas anônimas iniciem uma reunião

Essa configuração é uma política por organizador que permite reuniões de conferência discada sem líder. Essa configuração controla se os usuários de acesso telefônico podem participar da reunião sem um usuário autenticado da organização em participação. Por padrão, essa configuração está desativada, o que significa que os usuários de discagem aguardarão no lobby até que um usuário autenticado da organização ingresse na reunião.

> [!NOTE]
> Se essa configuração estiver desativada e um usuário de acesso telefônico participar da reunião primeiro e for colocado no lobby, um usuário da organização deverá participar da reunião com um cliente do Teams para admitir o usuário do lobby. Não há controles de lobby disponíveis para os usuários.

## <a name="automatically-admit-people"></a>Aceitar pessoas automaticamente

Esta é uma política por organizador. Essa configuração controla se as pessoas ingressam em uma reunião diretamente ou aguardam no lobby até serem reconhecidas por um usuário autenticado. Essa configuração não se aplica a usuários de discagem.

![Captura de tela mostrando uma reunião com um usuário no lobby.](media/meeting-policies-lobby.png)

 Os organizadores de reuniões podem clicar em **Opções de reunião** no convite da reunião para alterar essa configuração para todas as reuniões agendadas.

> [!NOTE]
> Nas opções da reunião, a configuração é rotulada "Quem pode ignorar o lobby". Se você alterar a configuração padrão para qualquer usuário, ela será aplicada a todas as novas reuniões organizadas por esse usuário e a qualquer reunião anterior em que o usuário não tiver modificado as Opções de reunião.
  
|Valor de configuração  |Comportamento de ingresso |
|---------|---------|
|**Todos**   |Todos os participantes da reunião participam da reunião diretamente, sem aguardar no lobby. Isso inclui usuários autenticados, usuários de organizações confiáveis, convidados e usuários anônimos.     |
|**Pessoas na minha organização e convidados**     |Os usuários autenticados dentro da organização, incluindo convidados, ingressam na reunião diretamente sem esperar no lobby. Os usuários de organizações confiáveis e usuários anônimos aguardam o lobby. Essa é a configuração padrão.    |
|**Pessoas da minha organização e organizações confiáveis**     |Os usuários autenticados dentro da organização, incluindo convidados e usuários de organizações confiáveis, ingressam na reunião diretamente sem aguardar no lobby.  Os usuários anônimos aguardam o lobby.   |
|**Pessoas na minha organização**    |Os usuários autenticados de dentro da organização ingressam na reunião diretamente sem aguardar no lobby.  Os usuários de organizações confiáveis, convidados e usuários anônimos aguardam no lobby.          |
|**Organizador somente**    |Somente os organizadores da reunião participam da reunião diretamente, sem aguardar no lobby. Todos os outros, incluindo usuários autenticados dentro da organização, convidados, usuários de organizações confiáveis e usuários anônimos devem aguardar no lobby. Na página de opções de reunião do cliente do Teams, ele aparece como "Somente eu".          |
|**Somente usuários convidados**    |Somente usuários convidados e organizadores da reunião podem ingressar na reunião diretamente sem aguardar no lobby. Todos os outros, incluindo usuários autenticados dentro da organização, convidados, usuários de organizações confiáveis e usuários anônimos devem aguardar no lobby. Na página de opções de reunião do cliente do Teams, ele aparece como "Pessoas eu convidar". Os usuários adicionados como parte de um grupo de distribuição terão que passar pelo lobby.      |

 > [!NOTE]
> As organizações confiáveis são domínios com os qual você permite comunicações federadas no Teams. Se você **habilitar Permitir todos os domínios externos** para acesso externo no centro de administração do Teams, qualquer usuário autenticado em qualquer organização do Teams será confiável. Se você optar por especificar domínios externos permitidos e bloquear todos os outros, os domínios permitidos se tornarão organizações confiáveis. Qualquer domínio bloqueado é considerado não uma organização confiável.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Permitir que os usuários de acesso telefônico ignorem o lobby

Esta é uma política por organizador. Essa configuração controla se as pessoas que se conectam por telefone ingressam diretamente na reunião ou esperam o lobby, independentemente da configuração **Aceitar pessoas automaticamente**. Por padrão, essa configuração é desabilitada. Quando essa configuração estiver desativada, os usuários de acesso telefônico aguardarão no lobby até que um usuário da organização ingresse na reunião com um cliente do Teams e os admita. Quando essa configuração estiver ativada, os usuários de discagem ingressarão automaticamente na reunião quando um usuário da organização ingressar na reunião com um cliente do Teams.

> [!NOTE]
> Se um usuário de acesso telefônico participar de uma reunião antes de um usuário da organização ingressar na reunião, ele será colocado no lobby até que um usuário da organização ingresse na reunião usando um cliente de equipes e o admita. Se você alterar a configuração padrão para qualquer usuário, ela será aplicada a todas as novas reuniões organizadas por esse usuário e a qualquer reunião anterior em que o usuário não tiver modificado as Opções de reunião.

## <a name="live-captions"></a>Legendas ao vivo

Essa configuração é uma política por usuário e se aplica durante uma reunião. Essa configuração controla se a opção **Ativar legendas ao vivo** está disponível para que o usuário ative e desative as legendas ao vivo nas reuniões que o usuário faz.  

![Captura de tela mostrando a opção Ativar legendas ao vivo.](media/meeting-policies-live-captions.png)

|Valor de configuração |Comportamento  |
|---------|---------|
|**Desabilitado, mas o usuário pode ignorar**     | As legendas ao vivo não são automaticamente ativadas para o usuário durante uma reunião. O usuário verá a opção **Ativar legendas ao vivo** no menu flutuante (**...**) para ativá-las. Essa é a configuração padrão. |
|**Não habilitado**     | As legendas ao vivo estão desabilitadas para o usuário durante uma reunião. O usuário não tem a opção para ativá-las.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chat em reuniões

Essa é uma política por usuário e por organizador. Essa configuração controla se o chat de reunião é permitido na reunião do usuário. Essa configuração não se aplica a reuniões de canal.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Ativá-lo para todos**     | Todos os participantes podem escrever e exibir mensagens de chat. |
|**Desative-o para todos**     | O chat de reunião está desativado para todos os participantes.  |
|**Ativá-lo para todos, exceto usuários anônimos**     | O acesso de gravação de chat de reunião está desativado somente para participantes anônimos.  |

Depois que **essa política de Chat em reuniões** for aplicada aos usuários, um organizador não poderá substituir essa política por meio das **opções de Reunião**.

A política aplicada ao organizador da reunião pode afetar outros usuários na reunião. Por exemplo:

- Se o organizador tiver o **Chat** em reuniões definido  para ativá-lo para todos ou ativá-lo para todos, exceto usuários anônimos **, a** política individual de um usuário  será aplicada e todos os usuários com Desativação para todos os usuários definidos não poderão conversar na reunião.
- Se o organizador tiver **o Chat em reuniões** definido como Desativá-lo para **todos, a** política do organizador será aplicada e ninguém poderá conversar na reunião.

<a name="bkparticipantsandguests"> </a>

## <a name="qa-in-meetings"></a>P&A em reuniões

Esta é uma política por organizador. Essa configuração permite que os administradores de locatários do Microsoft 365 habilitem ou desabilitem as perguntas & experiência de respostas (Q&A).

A configuração é imposta quando uma reunião é criada ou atualizada pelos Organizadores. Por padrão, essa configuração é desabilitada. Saiba mais sobre o Q&A [aqui](/manage-qna-for-meetings).

O parâmetro QnAEngagementMode controla essa política no PowerShell. As&A também podem ser ajustadas no portal de administração.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Habilitado**     | Os organizadores podem adicionar Q&A ao criar reuniões. |
|**Desabilitado**     | Os organizadores não terão a opção de adicionar Q&A ao criar reuniões.  |

## <a name="enable-meeting-policy-settings"></a>Habilitar configurações de política de reunião

Parahabilitar as configurações de política de reunião, você pode usar o centro de administração do [Teams](https://admin.teams.microsoft.com/policies/meetings) **(** >  > Políticas de Reunião Editam uma política participantes **& convidados**) ou o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) no Teams PowerShell. 

Neste exemplo, usamos o PowerShell para modificar a política de reunião global para permitir que qualquer pessoa inicie ou ingresse em uma reunião.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Depois de configurar uma política, você precisará aplicá-la aos usuários. Se você modificou a política Global (padrão em toda a organização), ela será aplicada automaticamente aos usuários. Você precisa aguardar pelo menos 4 horas para que as alterações de política entre em vigor, mas pode levar até 24 horas.


## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
- [Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários](meeting-policies-restricted-anonymous-access.md)
