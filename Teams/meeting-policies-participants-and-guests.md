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
description: Aprenda a gerenciar configurações de política de reunião no Teams para participantes e convidados.
ms.openlocfilehash: a5d18ea0e3f8c6cd008a12258fd94c3a0b725ac3
ms.sourcegitcommit: 1fe19c4a6e9f6116515df531786cc3e482e27093
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2022
ms.locfileid: "68876277"
---
# <a name="meeting-policy-settings---participants--guests"></a>Configurações de política de reunião - Participantes e convidados

<a name="bkmeetingparticipants"> </a>

Essas configurações controlam quais participantes da reunião esperam no lobby antes de serem admitidos na reunião e o nível de participação permitido em uma reunião.

- [Permitir que pessoas anônimas participem de uma reunião](#let-anonymous-people-join-a-meeting)
- [Permitir que pessoas anônimas iniciem uma reunião](#let-anonymous-people-start-a-meeting)
- [Quem pode apresentar em reuniões](#who-can-present-in-meetings)
- [Admitir pessoas automaticamente](#automatically-admit-people)
- [Os usuários de discagem podem ignorar o lobby](#dial-in-users-can-bypass-the-lobby)
- [Reunir-se agora em reuniões privadas](#meet-now-in-private-meetings)
- [Legendas ao vivo](#live-captions)
- [Chat em reuniões](#chat-in-meetings)
- [Teams Q&A](#teams-qa)
- [Reações de reunião](#meeting-reactions)

Essas configurações são encontradas no centro de administração do Teams em **Políticas de reunião** de **reuniões** >  na seção **Participantes & convidados**.

> [!NOTE]
> As opções para ingressar em uma reunião variam, dependendo das configurações de cada grupo do Teams e do método de conexão. Se o seu grupo tiver audioconferência e a usar para se conectar, confira [Audioconferência](/microsoftteams/audio-conferencing-in-office-365). Se o seu grupo do Teams não tiver audioconferência, confira [Participar de uma reunião do Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Permitir que pessoas anônimas participem de uma reunião

Essa configuração por organizador permite que qualquer pessoa participe de reuniões como usuário anônimo selecionando o link no convite da reunião. Para saber mais, consulte [Ingressar em uma reunião sem uma conta do Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508). A capacidade dos usuários anônimos de ingressar em reuniões também é controlada no nível da organização, a configuração mais restritiva será eficaz. Para saber mais, confira [Usando o centro de administração do Microsoft Teams para configurar a política em toda a organização](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Permitir que pessoas anônimas iniciem uma reunião

Essa configuração é uma política por organizador que permite reuniões de conferência discada sem líder. Essa configuração controla se os usuários de acesso telefônico podem participar da reunião sem um usuário autenticado da organização em participação. Por padrão, essa configuração é desativada, o que significa que os usuários discados aguardarão no lobby até que um usuário autenticado da organização participe da reunião.

> [!NOTE]
> Se essa configuração estiver desativada e um usuário de acesso telefônico participar da reunião primeiro e for colocado no lobby, um usuário da organização deverá participar da reunião com um cliente do Teams para admitir o usuário do lobby. Não há controles de lobby disponíveis para os usuários.

## <a name="who-can-present-in-meetings"></a>Quem pode apresentar em reuniões

Essa é uma política por usuário. Essa configuração permite alterar o valor padrão da configuração **Quem pode apresentar?** nas **Opções de reunião** no cliente Teams. Essa configuração de política afeta todas as reuniões, incluindo reuniões Reunir Agora.

A configuração **Quem pode apresentar?** permite que os organizadores de reunião escolham quem pode apresentar na reunião. Para saber mais, confira [Alterar as configurações de participante de uma reunião do Teams](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) e [Funções em uma reunião do Teams](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Para especificar o valor padrão da configuração **Quem pode apresentar?** no Teams, defina como uma das seguintes configurações na política:

- **Organizadores, mas os usuários podem substituir**: apenas o organizador da reunião pode ser um apresentador e todos os participantes da reunião são designados como participantes. Esse parâmetro corresponde à configuração **Somente eu** no Teams.
- **Todos na organização, mas o usuário pode substituir**: usuários autenticados na organização, incluindo usuários convidados, podem ser apresentadores. Essa configuração corresponde ao **Pessoas na configuração da minha organização** no Teams.
- **Todos, mas o usuário pode substituir**: todos os participantes da reunião podem ser apresentadores. Esse é o valor padrão. Essa configuração corresponde à configuração **Todos** no Teams.

Lembre-se de que, depois de definir o valor padrão, os organizadores de reunião ainda poderão alterar essa configuração no Teams e escolher quem poderá apresentar nas reuniões agendadas por eles.

## <a name="automatically-admit-people"></a>Aceitar pessoas automaticamente

Esta é uma política por organizador. Essa configuração controla se as pessoas participam de uma reunião diretamente ou esperam no lobby até serem admitidas por um usuário autenticado. Essa configuração não se aplica aos usuários discando.

![Captura de tela mostrando uma reunião com um usuário no lobby.](media/meeting-policies-lobby.png)

 Os organizadores de reuniões podem clicar em **Opções de reunião** no convite da reunião para alterar essa configuração para todas as reuniões agendadas.

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|Valor de configuração  |Comportamento de ingresso |
|---------|---------|
|**Todos**   |Todos os participantes da reunião participam da reunião diretamente, sem aguardar no lobby. Isso inclui usuários autenticados, usuários de organizações confiáveis, convidados e usuários anônimos.     |
|**Pessoas na minha organização e convidados**     |Usuários autenticados dentro da organização, incluindo convidados, participam da reunião diretamente sem esperar no lobby. Os usuários de organizações confiáveis e usuários anônimos aguardam o lobby. Essa é a configuração padrão.    |
|**Pessoas da minha organização e organizações confiáveis**     |Usuários autenticados dentro da organização, incluindo convidados e usuários de organizações confiáveis, participam da reunião diretamente sem esperar no lobby.  Os usuários anônimos aguardam o lobby.   |
|**Pessoas na minha organização**    |Usuários autenticados de dentro da organização participam da reunião diretamente sem esperar no lobby.  Usuários de organizações confiáveis, convidados e usuários anônimos esperam no lobby.          |
|**Organizador somente**    |Somente os organizadores da reunião participam da reunião diretamente, sem aguardar no lobby. Todos os outros, incluindo usuários autenticados na organização, convidados, usuários de organizações confiáveis e usuários anônimos devem aguardar no lobby. Na página opções de reunião do cliente do Teams, ela aparece como "Somente eu".          |
|**Somente usuários convidados**    |Somente usuários convidados e organizadores da reunião podem participar da reunião diretamente sem esperar no lobby. Todos os outros, incluindo usuários autenticados na organização, convidados, usuários de organizações confiáveis e usuários anônimos devem aguardar no lobby. Na página opções de reunião do cliente do Teams, ela aparece como "Pessoas eu convido". Os usuários adicionados como parte de um grupo de distribuição terão que passar pelo lobby.      |

 > [!NOTE]
> Organizações confiáveis são domínios com os quais você permite comunicações federadas no Teams. Se você habilitar **Permitir todos os domínios externos** para acesso externo no centro de administração do Teams, qualquer usuário autenticado em qualquer organização do Teams será confiável. Se você optar por especificar domínios externos permitidos e bloquear todos os outros, os domínios permitidos se tornarão organizações confiáveis. Qualquer domínio bloqueado é considerado não uma organização confiável.

## <a name="dial-in-users-can-bypass-the-lobby"></a>Os usuários de discagem podem ignorar o lobby

Esta é uma política por organizador. Essa configuração controla se as pessoas que se conectam por telefone ingressam diretamente na reunião ou esperam o lobby, independentemente da configuração **Aceitar pessoas automaticamente**. Por padrão, essa configuração é desabilitada. Quando essa configuração estiver desativada, os usuários de acesso telefônico aguardarão no lobby até que um usuário da organização ingresse na reunião com um cliente do Teams e os admita. Quando essa configuração estiver ativada, os usuários discados ingressarão automaticamente na reunião quando um usuário da organização ingressar na reunião com um cliente do Teams.

> [!NOTE]
> Se um usuário de acesso telefônico participar de uma reunião antes de um usuário da organização ingressar na reunião, ele será colocado no lobby até que um usuário da organização ingresse na reunião usando um cliente de equipes e o admita. Se você alterar a configuração padrão para qualquer usuário, ela será aplicada a todas as novas reuniões organizadas por esse usuário e a qualquer reunião anterior em que o usuário não tiver modificado as Opções de reunião.

## <a name="meet-now-in-private-meetings"></a>Reunir-se agora em reuniões privadas

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se um usuário pode iniciar uma reunião privada não planejada. Por padrão, essa configuração é ativada.

## <a name="live-captions"></a>Legendas ao vivo

Essa configuração é uma política por usuário e se aplica durante uma reunião. Essa configuração controla se a opção **Ativar legendas ao vivo** está disponível para que o usuário ative e desative as legendas ao vivo nas reuniões que o usuário faz.  

![Captura de tela mostrando a opção Ativar legendas ao vivo.](media/meeting-policies-live-captions.png)

|Valor de configuração |Comportamento  |
|---------|---------|
|**Não habilitado, mas o usuário pode substituir**     | As legendas ao vivo não são automaticamente ativadas para o usuário durante uma reunião. O usuário verá a opção **Ativar legendas ao vivo** no menu flutuante (**...**) para ativá-las. Essa é a configuração padrão. |
|**Não habilitado**     | As legendas ao vivo estão desabilitadas para o usuário durante uma reunião. O usuário não tem a opção para ativá-las.          |

Para obter mais informações sobre como seus **usuários finais podem ativar legendas ao vivo**, consulte [Usar legendas ao vivo em uma reunião do Teams](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260).

### <a name="live-translated-captions"></a>Legendas traduzidas ao vivo

> [!NOTE]
> Esse recurso está disponível temporariamente em versão prévia pública. Após a visualização, o organizador da reunião deve ter uma licença do Teams Premium para que os participantes usem legendas traduzidas ao vivo.

Por padrão, **as legendas ao vivo são exibidas** no idioma falado durante uma reunião. **As legendas traduzidas ao vivo** permitem que seus usuários vejam legendas traduzidas para o idioma com o qual estão mais confortáveis.

Para habilitar **legendas traduzidas ao vivo**, **as legendas ao vivo devem ser definidas** como **Não habilitadas, mas o usuário pode substituir** no centro de administração do Teams. Para **desativar legendas traduzidas ao vivo**, defina isso como **Não habilitado**.

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chat em reuniões

Essa é uma política por usuário e por organizador. Essa configuração controla se o chat de reunião é permitido na reunião do usuário. Essa configuração não se aplica a reuniões de canal.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Ativá-lo para todos**     | Todos os participantes podem escrever e exibir mensagens de chat. |
|**Desativar para todos**     | O chat da reunião está desativado para todos os participantes.  |
|**Ativá-lo para todos, menos usuários anônimos**     | O acesso de gravação de chat de reunião é desativado apenas para participantes anônimos.  |

Depois que essa política **de Chat em reuniões** for aplicada aos usuários, um organizador não poderá substituir essa política por meio de **opções de reunião**.

A política aplicada ao organizador da reunião pode afetar outros usuários na reunião. Por exemplo:

- Se o organizador tiver o **Chat em reuniões** definido **para Ativá-lo para todos** ou **Ativá-lo para todos, exceto usuários anônimos**, a política individual de um usuário será aplicada e todos os usuários com **Desativar para todos** os conjuntos não poderão conversar na reunião.
- Se o organizador tiver **o Chat nas reuniões** definido para **Desativar para todos**, a política do organizador se aplicará e ninguém poderá conversar na reunião.

<a name="bkparticipantsandguests"> </a>

## <a name="teams-qa"></a>Teams Q&A

Esta é uma política por organizador. Essa configuração ativa ou desativa a experiência Perguntas & Respostas (Q&A).

A configuração é imposta quando uma reunião é criada ou é atualizada pelos organizadores. Por padrão, essa configuração é desabilitada. Saiba mais sobre [q&A em reuniões do Teams](/manage-qna-for-teams).

O parâmetro QnAEngagementMode controla essa política no PowerShell. Q&A também pode ser ajustado no centro de administração do Teams.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Ativado**     | Os organizadores podem adicionar Q&A ao criar reuniões. |
|**Desativado**     | Os organizadores não terão a opção de adicionar Q&A ao criar reuniões.  |

## <a name="meeting-reactions"></a>Reações de reunião

As reações de reunião estão ativadas por padrão. Desativar as reações para um usuário não significa que ele não possa usar as reações nas reuniões agendadas por ele. O organizador da reunião ainda pode ativar as reações na página de opção da reunião, independentemente da configuração padrão.

## <a name="enable-meeting-policy-settings"></a>Habilitar configurações de política de reunião

Para habilitar as configurações da política de reunião, você pode usar o [centro de administração do Teams](https://admin.teams.microsoft.com/policies/meetings) (**Políticas** >  de Reunião **Editar uma política** > **Participantes & convidados**) ou o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) no Teams PowerShell. 

Neste exemplo, usamos o PowerShell para modificar a política de reunião global para permitir que qualquer pessoa inicie ou participe de uma reunião.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Depois de configurar uma política, você precisa aplicá-la aos usuários. Se você modificou a política Global (padrão em toda a organização), ela se aplicará automaticamente aos usuários. Você precisa esperar pelo menos 4 horas para que qualquer alteração de política entre em vigor, mas pode levar até 24 horas.


## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
- [Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários](meeting-policies-restricted-anonymous-access.md)
