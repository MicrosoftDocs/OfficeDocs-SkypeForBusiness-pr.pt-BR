---
title: Configurar eventos ao vivo no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Saiba como definir as configurações de evento ao vivo na Teams da Microsoft, incluindo a definição de visibilidade de participante e opções de gravação.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354352"
---
# <a name="configure-live-events-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a>Configurar o link de suporte do evento
Este é o link que será exibido para os participantes do evento ao vivo. 

No Windows PowerShell, execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a>Configurar opções de visibilidade do participante
Isso permite que os organizadores de evento ao vivo criar eventos com visibilidade attendee apropriado.

|**Valores**  |**Comportamento**  |
|---------|---------|
|Todos     |O usuário tem uma opção para criar eventos ao vivo com a visibilidade de participante a seguir: público, todos na empresa e pessoas específicas. |
|EveryoneInCompany     |O usuário tem uma opção para criar eventos ao vivo com a visibilidade de participante a seguir: todos na empresa e pessoas específicas. O usuário não pode criar eventos ao vivo que podem ser assistidos por usuários anônimos.|
|InvitedUsers |O usuário só pode criar eventos que são limitados a pessoas específicas, como inseridas pelo organizador evento ao vivo. O usuário não pode criar eventos ao vivo com público e todos na autenticação de empresa. |

Use o BroadcastAttendeeVisibility em TeamsMeetingBroadcastPolicy no PowerShell de configuração para controlar se os usuários podem agendar a transmissão de eventos que podem ser observados por participantes anônimos. 

A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem o padrão definido como EveryoneInCompany. 
 
No Windows PowerShell, execute o seguinte procedimento para permitir que usuários criem eventos anônimos na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a>Configurar opções de gravação
> [!NOTE]
> Essa opção é aplicável a eventos que usam apenas o método de produção de início rápido.

Isso permite que administradores controlar se os eventos ao vivo sempre são registrados, nunca registrados, ou se o organizador de evento pode optar por registrar o evento ou não.  

|**Valores**  |**Comportamento**  |
|---------|---------|
|Sempre habilitada |Os eventos ao vivo organizados pelo usuário sempre são registrados. O usuário não tem uma opção para substituir. Se o evento ao vivo é registrado, os membros da equipe de evento são capazes de fazer o download de gravação após o evento e os participantes podem assistir o evento após o evento está sobre. |
|AlwaysDisabled |Os eventos ao vivo organizados pelo usuário nunca são registrados. O usuário não tem uma opção para substituir. Se o evento ao vivo é registrado, nenhum registro é criado para os membros da equipe de evento e os participantes não podem assistir o evento após ele está sobre. |
|UserOverride |Usuário poderá decidir se o evento ao vivo é registrado para que um arquivo de gravação que pode ser criado para os membros da equipe de evento, e os participantes podem assistir o evento após o evento está sobre. |

Use a configuração *BroadcastRecordingMode* no **TeamsMeetingBroadcastPolicy** no PowerShell ao controle opções dos eventos ao vivo criados pelo organizador evento ao vivo de gravação.

No Windows PowerShell, execute o seguinte cmdlet para atualizar o modo de gravação na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurar a transcrição em tempo real e uma tradução em eventos ao vivo de equipes (em breve)
> [!NOTE]
> Essa opção é aplicável a eventos que usam apenas o método de produção de início rápido.

Isso permite que os organizadores de evento ao vivo Ativar legendas em tempo real e uma tradução para os participantes do evento ao vivo. 

Use a configuração *AllowBroadcastTranscription* no **TeamsMeetingBroadcastPolicy** no PowerShell para controlar se os participantes do evento ao vivo poderão ver a transcrição e uma tradução. Saiba mais sobre como gerenciar **TeamsMeetingBroadcastPolicy** com o Office 365 PowerShell aqui.  

A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem a transcrição e uma tradução desabilitado por padrão.

No Windows PowerShell, execute o seguinte cmdlet para ativar a transcrição e uma tradução em para os participantes do evento na política global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a>Ferramentas administrativas 
Embora a Microsoft diretamente controla todos os centros de dados Online do Office 365 e é responsável pelo desempenho geral do sistema, ele pode controlar apenas uma parte dos elementos que são combinados para fornecer a experiência total para usuários do Office 365. Organizações sozinhos são responsáveis por conexões de rede para os data centers, rede de longa distância (WAN), do cliente e do cliente redes locais (LANs). Além disso, eles estarão responsável por dispositivos de usuário e sua configuração.Eles também são responsável por manter o licenciamento necessários por usuário para qualquer recurso desejado, incluindo, mas não limitado a, a capacidade de gerenciar esses recursos, para desde que o usuário precisar de acesso ao recurso.

Os clientes podem usar as seguintes ferramentas para gerenciar uma variedade de tarefas relacionadas do equipes eventos ao vivo.
- [Centro de administração do Microsoft Office 365](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams e Skype para Business Online admin center](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Centro de administração do Microsoft Stream](https://stream.microsoft.com)
- [Windows PowerShell remoto](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?
Quando se trata de Windows PowerShell, ele é tudo sobre o gerenciamento de usuários e quais os usuários poderão ou não podem para fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e Skype para negócios Online usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
 - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
 - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
