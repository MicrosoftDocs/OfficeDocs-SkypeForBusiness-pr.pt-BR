---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: Saiba como executar o Microsoft Teams em um ambiente de infraestrutura de área de trabalho virtualizada (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e88a5fb4e8522a94389e3bad24ddc3da8283a53
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588139"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e as limitações para usar o Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

A Virtual Desktop Infrastructure (VDI) é a tecnologia de virtualização que hospeda um sistema operacional e aplicativos de área de trabalho em um servidor centralizado em um Data Center. Isso permite uma experiência de área de trabalho totalmente personalizada para os usuários com uma fonte centralizada totalmente segura e compatível. 
 
Atualmente, o Teams em um ambiente virtualizado está disponível com suporte para funcionalidade de colaboração e chat com uma máquina virtualizada (VM) persistente dedicada. Para garantir uma experiência de usuário ideal, siga as orientações deste artigo. 

## <a name="teams-requirements"></a>Requisitos do teams

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Definir políticas para desativar a funcionalidade de chamada e de reunião no Teams

As chamadas e a experiência da reunião do Teams não são otimizadas para um ambiente VDI (disponível em breve). Recomendamos que você defina políticas em nível de usuário para desativar a funcionalidade de chamada e reunião no Microsoft Teams.

Você ainda pode optar por executar o Teams totalmente na VDI usando o aplicativo da área de trabalho do teams ou o aplicativo Web. No entanto, recomendamos que você defina as políticas para evitar comprometer a experiência do usuário.  

Pode levar algum tempo (algumas horas) para que as alterações de política sejam propagadas. Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.

> [!NOTE]
> Quando chamadas e reuniões de equipes são otimizadas para uso em ambientes de área de trabalho virtual, você pode reverter essas políticas e permitir que os usuários usem o Microsoft Teams normalmente. 

#### <a name="calling"></a>Chamadas

Use os cmdlets **CSTeamsCallingPolicy** para controlar se os usuários podem usar as opções de chamadas e chamadas em conversas privadas e em grupo. Veja a lista de configurações de política e os valores recomendados.

|Nome da política  |Descrição |Valor recomendado  |
|---------|---------|---------|
|AllowCalling    |Controla os recursos de chamada Interop. Ativar isso permite que os usuários do Skype for Business tenham chamadas individuais com usuários do Microsoft Teams e vice-versa.         |Definido como falso para impedir chamadas do pouso usuários do Skype for Business no Teams.          |
|AllowPrivateCalling     | Controla se o aplicativo de chamada está disponível na barra de aplicativos no lado esquerdo do cliente do Teams e se os usuários veem opções de chamadas e chamadas com vídeo no chat privado         |Definido como falso para remover o aplicativo de chamada da barra de aplicativos no lado esquerdo do Teams e para remover as opções de chamadas e chamadas com vídeo no chat privado.          |

#### <a name="create-and-assign-a-calling-policy"></a>Criar e atribuir uma política de chamada

1. Inicie uma sessão do Windows PowerShell como administrador.
2. Conecte-se ao conector online do Skype.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Exibir uma lista de opções de política de chamada.

       Get-CsTeamsCallingPolicy
 
4. Procure a opção de política interna na qual todas as políticas de chamadas estão desabilitadas. Ele tem a seguinte aparência.
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. Aplique a opção de política interna do DisallowCalling a todos os usuários que usarão o Teams em um ambiente virtualizado.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Para obter mais informações sobre as políticas de chamada de equipes, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Reuniões

Use os cmdlets **CsTeamsMeetingPolicy** para controlar o tipo de reunião que os usuários podem criar, os recursos que eles podem acessar durante uma reunião e os recursos de reunião que estão disponíveis para usuários anônimos e externos. Veja a lista de configurações de política e os valores recomendados.

|Nome da política |Descrição|Valor recomendado                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Determina se um usuário tem permissão para agendar reuniões particulares.| Defina como false para impedir que o usuário seja capaz de agendar reuniões particulares.  |
|AllowChannelMeetingScheduling  | Determina se um usuário tem permissão para agendar reuniões de canal. | Defina como false para impedir que o usuário seja capaz de agendar reuniões de canal.                       |
|AllowMeetNow |Determina se um usuário tem permissão para criar ou iniciar reuniões ad hoc.              |  Defina como false para impedir que o usuário seja capaz de iniciar reuniões ad hoc.                     |
|ScreenSharingMode | Determina o modo no qual um usuário pode compartilhar sua tela em chamadas ou reuniões. | Definido como desabilitado para proibir o usuário de compartilhar suas telas                          |
|AllowIPVideo |Determina se o vídeo está habilitado em reuniões ou chamadas de um usuário.                  |    Definido como falso para impedir que o usuário Compartilhe seu vídeo                                         |
| AllowAnonymousUsersToDialOut | Determina se os usuários anônimos podem discar para um número PSTN. | Definido como falso para proibir usuários anônimos de discar                                  |
| AllowAnonymousUsersToStartMeeting | Determina se os usuários anônimos podem iniciar uma reunião.     |  Definido como falso para impedir que os usuários iniciem uma reunião                                            |
| AllowOutlookAddIn |Determina se um usuário pode agendar reuniões de equipes no cliente da área de trabalho do Outlook.| Definido como falso para proibir um usuário de agendar reuniões de equipes no cliente da área de trabalho do Outlook|
| AllowParticipantGiveRequestControl|Determina se os participantes podem solicitar ou dar controle ao compartilhamento de tela.| Definido como false para impedir que o usuário dê e solicite controle em uma reunião    |
| AllowExternalParticipantGiveRequestControl | Determina se os participantes externos podem solicitar ou dar controle ao compartilhamento de tela.| Definido como falso para impedir que um usuário externo dê, solicitando o controle em uma reunião|
|AllowPowerPointSharing|Determina se o compartilhamento do PowerPoint é permitido em reuniões de um usuário. |Definido como falso para impedir que um usuário Compartilhe arquivos do PowerPoint em uma reunião  |
|AllowWhiteboard | Determina se o whiteboard é permitido em reuniões de um usuário. |   Definido como falso para proibir o quadro de comunicações em uma reunião |
| AllowTranscription |Determina se as transcrições e as legendas de tempo real e/ou pós-reunião são permitidas nas reuniões de um usuário.|    Definido como falso para proibir transcrição e legendas em uma reunião  |  
| AllowSharedNotes | Determina se os usuários têm permissão para fazer anotações compartilhadas. | Definido como falso para proibir os usuários de fazer anotações compartilhadas |
|MediaBitRateKB |Determina a taxa de bits de mídia para transmissões de compartilhamento de áudio/vídeo/aplicativo em reuniões  | O valor sugerido é 5000 (5 MB). Você pode alterá-lo com base nas necessidades da sua organização.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Criar e atribuir uma política de reunião

1. Inicie uma sessão do Windows PowerShell como administrador.
2. Conecte-se ao conector online do Skype.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Exibir uma lista de opções de política de reunião.

       Get-CsTeamsMeetingPolicy
 
4. Procure a opção de política interna na qual todas as políticas de reunião estão desativadas. Ele tem a seguinte aparência.
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. Aplique a opção de política interna do AllOff a todos os usuários que usarão o Teams em um ambiente virtualizado. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Para obter mais informações sobre as políticas de reunião do Teams, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O aplicativo Teams foi validado nos principais provedores de soluções de virtualização. Com vários provedores de mercado, consulte seu provedor de soluções de virtualização para garantir que os requisitos mínimos sejam atendidos.

### <a name="virtual-machine-requirements"></a>Requisitos da máquina virtual

Com as diversas cargas de trabalho e necessidades de usuário em um ambiente virtualizado, a seguir está a configuração de VM mínima recomendada.

|Parâmetro  |Certa  |
|---------|---------|
|vCPU    |  2 núcleos       |
|RAM     |  4 GB      |
|SPS     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Requisitos do sistema operacional da máquina virtual

Os sistemas operacionais com suporte para VM são:

- Windows 10 e posterior
- Windows Server 2012 R2 e posterior

## <a name="install-teams-on-vdi"></a>Instalar o Microsoft Teams no VDI

Aqui está o processo e as ferramentas para implantar o aplicativo da área de trabalho Teams. 

1. Baixe o pacote MSI do teams usando um dos links a seguir, dependendo do ambiente. Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.

    - [versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Execute o seguinte comando para instalar o MSI na VM VDI (ou conclua a atualização).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Isso instala o Microsoft Teams para arquivos de programas. Neste ponto, a configuração da imagem dourada está completa.
 
    A próxima sessão de logon interativo inicia o Teams e solicita credenciais. Observe que não é possível desabilitar a inicialização automática de equipes ao instalar o Microsoft Teams no VDI usando a propriedade MyUser. 

3. Execute o comando a seguir para desinstalar o MSI da VM VDI (ou preparar-se para atualizá-lo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Isso desinstala equipes de arquivos de programas.

## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

Os itens a seguir são limitações e problemas conhecidos do teams em VDI.

- Implantações de **tipos de host de sessão compartilhada**: implantações de tipo de host de sessão compartilhada (por exemplo, configuração de VM não persistente compartilhada) não estão no escopo.
- **Chamadas e reuniões**:

    - Os cenários de chamada e reunião não são otimizados para VDI. Esses cenários serão executados com baixa qualidade. Recomendamos o uso de políticas em nível de usuário, conforme descrito na seção [definir as políticas para desativar a funcionalidade de chamada e de reunião na](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) seção Teams.  
    - A aplicação das políticas descritas neste artigo impacta a capacidade de usar a funcionalidade de chamada e de reunião, o que, dependendo das outras políticas, pode afetar outros usuários da organização. Se os usuários da sua organização usarem clientes não VDI, você poderá optar por não aplicar as políticas.  

- **Ingressando em chamadas e reuniões criadas por outros usuários**: embora as políticas impeçam que os usuários criem reuniões, elas ainda podem ingressar em reuniões se outro usuário discar para elas pela reunião. Nessas reuniões, a capacidade do usuário de compartilhar vídeo, usar o whiteboard e outros recursos depende se você desabilitou esses recursos usando o TeamsMeetingPolicy.  
- **Conteúdo em cache**: se o ambiente virtual no qual as equipes estiver em execução não for persistente (e os dados forem limpos no final de cada sessão do usuário), os usuários poderão perceber a degradação do desempenho devido à atualização de conteúdo, independentemente de o usuário ter acesso ao mesmo conteúdo em uma sessão anterior.
- **Atualizações de cliente**: o Teams não é atualizado automaticamente como a maneira como os clientes de equipes não VDI são.  Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção instalar o Microsoft [Teams no VDI](#install-teams-on-vdi) . Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- **Experiência do usuário**: a experiência do usuário do teams em um ambiente VDI pode ser diferente de um ambiente não VDI. As diferenças podem ser devido às configurações de política e/ou suporte a recursos no ambiente.

Para os problemas conhecidos do teams que não estão relacionados ao VDI, consulte [problemas conhecidos do Microsoft Teams](Known-issues.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Microsoft Teams usando o MSI](msi-deployment.md)
