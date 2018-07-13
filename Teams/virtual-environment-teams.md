---
title: Execute o Microsoft Teams em um ambiente virtual
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/12/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: Saiba como executar Teams da Microsoft em um ambiente virtualizado.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: d00ee6a3c14b5a1bb97685124293b13977c323af
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20328722"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a>Execute o Microsoft Teams em um ambiente virtual
============================================

Este artigo descreve os requisitos e limitações do uso de equipes em um ambiente virtualizado.

Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações onde questões de segurança e conformidade são especialmente sensíveis. Seus usuários realizam o trabalho em uma área de trabalho virtual que contém todos os seus aplicativos de desktop e arquivos usando os serviços de área de trabalho remota ou uma conexão remota semelhante. Desde que equipes na área de trabalho virtual não foi otimizada para acessar ou usar os dispositivos de áudio ou vídeos no dispositivo de local do usuário (sem software adicional), a funcionar em um ambiente de VDI geralmente terá desafios relacionados aos cenários de multimídia, como a chamada, as chamadas de vídeo, compartilhamento de tela, compartilhamento de aplicativo, coautoria e muito mais. 

> [!NOTE]
> As organizações podem optar executar o equipes totalmente em VDI (usando o Web App ou o cliente de área de trabalho), mas é recomendável que as seguintes políticas ser desativado, para que os usuários não tenham uma experiência de baixa em um ambiente virtualizado. Observe que ela pode levar algum tempo para que essas alterações de diretiva propagar. Se você não vir as alterações de uma determinada conta imediatamente, tente novamente após algumas horas. 

## <a name="calling"></a>Chamadas

Os cmdlets *CsTeamsCallingPolicy* permitem que os administradores controlem se chamando-se e opções de chamada em particular e chats de grupo estão habilitadas ou não. 


|Nome da política |Descrição  |Valor recomendado  |
|---------|---------|---------|
|AllowPrivateCalling   |Controla se o aplicativo de chamada está disponível no trilho esquerdo do cliente equipes ou não. Também controla se os usuários ver as opções de chamada e chamada de vídeo em bate-papo privado. |Defina como **False** para remover o aplicativo de chamada do trilho esquerdo e remover as opções de chamada e chamada de vídeo no bate-papo privado. |

### <a name="powershell-instructions"></a>Instruções do PowerShell

1.  Inicie o PowerShell como administrador.
2.  Conecte ao conector do Skype Online:<br>
\>> *# Definir o nome de usuário do Office 365 e a senha*<br>
\>> *$username = "endereço de email do administrador"*<br>
\>> *$password = ConvertTo-SecureString "senha" - AsPlainText-Force*<br>
\>> *$LiveCred = System do novo objeto - typename - argumentlist $username, $password*<br><br>
\>> *N º conectar ao Skype Online*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New-CsOnlineSession-$LiveCred credencial*<br>
\>> *Import-PSSession $sfboSession*<br>
3.  Exiba a lista de opções de política de chamada:<br>
\>> *Get-CsTeamsCallingPolicy*
4.  Procure a opção pré-configurado onde todas as políticas de reunião são desabilitadas:<br>
![Captura de tela da opção de reuniões com todas as políticas de reunião desabilitada.](media/virtual-environment-image2.png)
5.  Aplique a opção de política pré-configurado "DisallowCalling" para todos os usuários que usarão as equipes em um ambiente virtualizado:<br>
\>> *Grant-CsTeamsMeetingPolicy - PolicyName AllOff-Identity "id de email do usuário"*

## <a name="meetings"></a>Reuniões

Os cmdlets *CsTeamsMeetingPolicy* permitem que os administradores controlem o tipo de reuniões que os usuários podem criar ou os recursos que eles possam acessar enquanto estiver em uma reunião. Isso também ajuda a determinar como as reuniões lidam com usuários anônimos ou externos.

|Nome da política |Descrição  |Valor recomendado  |
|---------|---------|---------|
|AllowPrivateMeetingScheduling    |Determina se um usuário seria permissão para agendar reuniões privadas.         |Defina como **False** para proibir que o usuário poder agendar reuniões privadas.         |
|AllowChannelMeetingScheduling     |Determina se um usuário seria permissão para agendar reuniões de canal.         |Defina como **False** para proibir que o usuário poder agendar reuniões de canal.         |
|AllowMeetNow     |Determina se um usuário seria permitido para criar ou iniciar reuniões ad hoc.         |Defina como **False** para proibir que o usuário poder iniciar reuniões ad hoc.         |
|ScreenSharingMode     |Determina o modo em que um usuário poderia ser poderão compartilhar tela em chamadas ou reuniões.         |Defina como **desabilitado** para impedir que o usuário de suas telas de compartilhamento.         |
|AllowIPVideo     |Determina se o vídeo é habilitado em reuniões ou chamadas de um usuário.         |Defina como **False** para proibir que o usuário compartilhando seu vídeo.         |
|AllowAnonymousUsersToDialOut     |Determina se os usuários anônimos poderão discar para um número PSTN.         |Defina como **False** para impedir que usuários anônimos de discagem.         |
|AllowAnonymousUsersToStartMeeting     |Determina se os usuários anônimos podem iniciar uma reunião.         |Defina como **False** para proibir que eles iniciando uma reunião.         |
|AllowOutlookAddIn     |Determina se um usuário pode agendar reuniões de equipes no cliente de desktop do Outlook.         |Defina como **False** para impedir que um usuário de agendamento de reunião de equipes no cliente Outlook.         |
|AllowParticipantGiveRequestControl     |Determina se os participantes podem solicitar ou conceder o controle de compartilhamento de tela.         |Defina como **False** para proibir que o usuário oferecendo, solicitando o controle em uma reunião.         |
|AllowExternalParticipantGiveRequestControl     |Determina se os participantes externos podem solicitar ou conceder o controle de compartilhamento de tela.         |Defina como **False** para proibir que um usuário externo oferecendo, solicitando o controle em uma reunião.         |
|AllowPowerPointSharing     |Determina se o compartilhamento do PowerPoint é permitida em reuniões de um usuário.         |Defina como **True** para permitir.<br>Defina como **False** para impedir que usuários de compartilhamento de arquivos do PowerPoint em uma reunião.         |
|AllowWhiteboard     |Determina se o quadro de comunicações é permitido em reuniões de um usuário.         |Defina como **False** para impedir o aplicativo de quadro de comunicações em uma reunião.         |
|AllowTranscription     |Determina se as legendas em tempo real e/ou posteriores à reunião e transcrições são permitidas em reuniões de um usuário.         |Defina como **False** para proibir transcrição e legenda em uma reunião.         |

### <a name="powershell-instructions"></a>Instruções do PowerShell

1.  Inicie o PowerShell como administrador.
2.  Conecte ao conector do Skype Online:<br>
\>> *# Definir o nome de usuário do Office 365 e a senha*<br>
\>> *$username = "endereço de email do administrador"*<br>
\>> *$password = ConvertTo-SecureString "senha" - AsPlainText-Force*<br>
\>> *$LiveCred = System do novo objeto - typename - argumentlist $username, $password*<br><br>
\>> *N º conectar ao Skype Online*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New-CsOnlineSession-$LiveCred credencial*<br>
\>> *Import-PSSession $sfboSession*
3.  Exiba a lista de opções de política de reunião:<br>
\>> *Get-CsTeamsMeetingPolicy*
4.  Procure a opção pré-configurado onde todas as políticas de reunião são desabilitadas:<br>
![Captura de tela da opção de chamada com todas as políticas de reunião desabilitadas.](media/virtual-environment-image1.png)
5.  Aplique a opção de política pré-configurado "AllOff" para todos os usuários que usarão as equipes em um ambiente virtualizado:<br>
\>> *Grant-CsTeamsMeetingPolicy - PolicyName AllOff-Identity "id de email do usuário"*

##<a name="known-limitations"></a>Limitações conhecidas

Além do previosly limitações de áudio e vídeo mencionado, há algumas limitações adicionais poderão ser enfrentadas por usuários em ambientes virtualizados:

- **Participar de reuniões criados por outras pessoas.** Embora as políticas acima restringem os usuários da criação de reuniões, eles ainda poderão ingressar em reuniões enviadas por outros usuários. Dentro dessas reuniões, sua capacidade de compartilhamento de vídeo, use o quadro de comunicações e outros recursos dependem se eles desabilitada ou não o administrador.

- **Problemas relacionados ao conteúdo armazenado em cache.** Se o ambiente virtual que equipes está sendo executado no não é persistente (dados estiver limpo no final de cada sessão do usuário), os usuários podem notar a diminuição do desempenho devido ao cliente precisar novamente baixar todo o conteúdo novamente, independentemente se determinado usuário acessado o mesmo conteúdo em uma sessão anterior. Esse impacto no desempenho poderá ser atenuado usando soluções de cache de roaming, como daquelas fornecidas pelo FSLogix.

Depois que as equipes foi otimizado para uso em ambientes de área de trabalho Virtual, os administradores podem reverter essas políticas e permitir que usuários usem equipes como faria normalmente.

         
        
        
        
        
        
        
        
        
        
        


