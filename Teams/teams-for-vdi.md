---
title: Equipes de infraestrutura de área de trabalho virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Saiba como executar Teams da Microsoft em um ambiente virtualizado do Desktop Infrastructure (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869826"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Equipes de infraestrutura de área de trabalho virtualizada

Este artigo descreve os requisitos e limitações para usar o Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional de área de trabalho e aplicativos em um servidor centralizado em um data center. Isso permite uma experiência de área de trabalho totalmente personalizada para usuários com uma fonte centralizada totalmente protegido e em conformidade. 
 
Atualmente, equipes em um ambiente virtualizado está disponível com suporte para a funcionalidade de bate-papo e colaboração com uma dedicado persistente virtualizada VM (máquina). Para garantir uma experiência ideal do usuário, siga as orientações neste artigo. 

## <a name="teams-requirements"></a>Requisitos de equipes

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Definir diretivas para desativar a chamada e funcionalidade nas equipes de reunião

As equipes chamando-se e experiência de reunião não está otimizado para um ambiente de VDI (em breve). Recomendamos que você defina políticas no nível do usuário para desativar, chamando-se e funcionalidade nas equipes de reunião.

Você ainda pode optar por executar as equipes de totalmente em VDI usando o aplicativo de área de trabalho de equipes ou aplicativo da web. No entanto, recomendamos que você defina as políticas para evitar comprometer a experiência do usuário.  

Pode levar algum tempo (algumas horas) para que as alterações de diretiva propagar. Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.

> [!NOTE]
> Quando a chamada de equipes e reuniões são otimizados para uso em ambientes virtuais de área de trabalho, você pode reverter essas políticas e permitir que usuários usem equipes como faria normalmente. 

#### <a name="calling"></a>Chamadas

Use os cmdlets de **CSTeamsCallingPolicy** para controlar se os usuários poderão usar chamando-se e opções de chamada em particular e chats de grupo. Aqui está uma lista de configurações de diretiva e valores recomendados.

|Nome da política  |Descrição |Valor recomendado  |
|---------|---------|---------|
|AllowCalling    |Interoperabilidade de controles recursos de chamada. Ativando Isso permite Skype para que os usuários corporativos pessoal durante chamadas com usuários de equipes e vice-versa.         |Defina como False para evitar que as chamadas para usuários comerciais inicial em equipes do Skype.          |
|AllowPrivateCalling     | Controla se o aplicativo de chamada está disponível na barra de aplicativos no lado esquerdo do cliente equipes e se os usuários veem a chamada e opções de chamada no bate-papo privado de vídeo         |Defina como False para remover o aplicativo de chamada da barra de aplicativos no lado esquerdo de equipes e remover as opções de chamada de chamada e vídeo no bate-papo privado.          |

#### <a name="create-and-assign-a-calling-policy"></a>Criar e atribuir uma política de chamada

1. Inicie uma sessão do Windows PowerShell como administrador.
2. Conecte-se ao conector Skype Online.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Exiba uma lista de opções de política de chamada.

       Get-CsTeamsCallingPolicy
 
4. Procure a opção de diretiva interna onde todas as diretivas de chamada estão desabilitadas. Ele tem esta aparência.
   
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

5. Aplique a opção de diretiva interna de DisallowCalling a todos os usuários que usarão as equipes em um ambiente virtualizado.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Para obter mais informações sobre políticas de chamada de equipes, consulte [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Reuniões

Use os cmdlets **CsTeamsMeetingPolicy** para controlar o tipo de reuniões que os usuários podem criar, os recursos que eles possam acessar enquanto estiver em uma reunião e os recursos da reunião que estão disponíveis para usuários anônimos e externos. Aqui está uma lista de configurações de diretiva e valores recomendados.

|Nome da política |Descrição|Valor recomendado                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Determina se um usuário tem permissão para agendar reuniões privadas.| Defina como False para proibir que o usuário poder agendar reuniões privadas.  |
|AllowChannelMeetingScheduling  | Determina se um usuário tem permissão para agendar reuniões de canal. | Defina como False para proibir que o usuário poder agendar reuniões de canal.                       |
|AllowMeetNow |Determina se um usuário tem permissão para criar ou iniciar reuniões ad hoc.              |  Defini-la como False para proibir que o usuário poder iniciar reuniões ad hoc.                     |
|ScreenSharingMode | Determina o modo em que um usuário tem permissão para compartilhar sua tela em chamadas ou reuniões. | Defina como desabilitado para impedir que o usuário de suas telas de compartilhamento                          |
|AllowIPVideo |Determina se o vídeo é habilitado em reuniões ou chamadas de um usuário.                  |    Defina como False para proibir que o usuário compartilhando sua vídeo                                         |
| AllowAnonymousUsersToDialOut | Determina se os usuários anônimos poderão discar para um número PSTN. | Defina como False para proibir que os usuários anônimos discagem externa                                  |
| AllowAnonymousUsersToStartMeeting | Determina se os usuários anônimos podem iniciar uma reunião.     |  Defina como False para proibir que os usuários iniciando uma reunião                                            |
| AllowOutlookAddIn |Determina se um usuário pode agendar reuniões de equipes no cliente de desktop do Outlook.| Defina como False para proibir que um usuário agendar reuniões de equipes no cliente de desktop do Outlook|
| AllowParticipantGiveRequestControl|Determina se os participantes podem solicitar ou conceder o controle de compartilhamento de tela.| Defina como False para proibir que o usuário oferecendo e solicitar controle em uma reunião    |
| AllowExternalParticipantGiveRequestControl | Determina se os participantes externos podem solicitar ou conceder o controle de compartilhamento de tela.| Defina como False para proibir que um usuário externo oferecendo, solicitando o controle em uma reunião|
|AllowPowerPointSharing|Determina se o compartilhamento do PowerPoint é permitida em reuniões de um usuário. |Defina como False para proibir que um usuário compartilhando arquivos do PowerPoint em uma reunião  |
|AllowWhiteboard | Determina se o quadro de comunicações é permitido em reuniões de um usuário. |   Defina como False para proibir o quadro de comunicações em uma reunião |
| AllowTranscription |Determina se as legendas em tempo real e/ou posteriores à reunião e transcrições são permitidas em reuniões de um usuário.|    Defina como False para proibir transcrição e legendas em uma reunião  |  
| AllowSharedNotes | Determina se os usuários poderão fazer anotações compartilhadas. | Defina como False para proibir que os usuários fazer anotações compartilhadas |
|MediaBitRateKB |Determina a taxa de bits de mídia de áudio/vídeo/app compartilhamento transmissões em reuniões  | Valor sugerido é 5000 (5 MB). Você pode alterar, com base nas necessidades da sua organização.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Criar e atribuir uma política de reunião

1. Inicie uma sessão do Windows PowerShell como administrador.
2. Conecte-se ao conector Skype Online.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Exiba uma lista de opções de política de reunião.

       Get-CsTeamsMeetingPolicy
 
4. Procure a opção de diretiva interna onde todas as políticas de reunião estão desabilitadas. Ele tem esta aparência.
   
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

5. Aplique a opção de diretiva interna de AllOff a todos os usuários que usarão as equipes em um ambiente virtualizado. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Para obter mais informações sobre políticas de reunião de equipes, consulte [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O aplicativo de equipes foi validado no principais provedores de solução de virtualização. Com vários provedores de mercado, consulte seu provedor de soluções de virtualização para garantir que sejam cumpridos os requisitos mínimos.

### <a name="virtual-machine-requirements"></a>Requisitos de máquina virtual

Com as cargas de trabalho diversas e as necessidades do usuário em um ambiente virtualizado, a seguir é o mínimo recomendado de configuração da VM.

|Parâmetro  |Medida  |
|---------|---------|
|vCPU    |  2 núcleos       |
|RAM     |  4 GB      |
|Armazenamento     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Requisitos de sistema operacional da máquina virtual

Os sistemas operacionais suportados para a VM são:

- Windows 10 e posterior
- Windows Server 2012 R2 e posterior

## <a name="install-teams-on-vdi"></a>Instalar equipes em VDI

Aqui está o processo e ferramentas para implantar o aplicativo de área de trabalho de equipes. 

1. Baixe o pacote MSI equipes usando um dos links a seguir, dependendo do ambiente. Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.

    - [versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Execute o seguinte comando para instalar o MSI do VM VDI (ou concluir atualizá-lo).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Essa etapa instala equipes para arquivos de programa. Neste ponto, a configuração de imagem de ouro estará concluída.
 
    A próxima sessão de logon interativo inicia equipes e solicita credenciais. Observe que não é possível desabilitar a inicialização automática das equipes ao instalar equipes em VDI usando a propriedade ALLUSER. 

3. Execute o seguinte comando para desinstalar o MSI de VDI VM (ou se preparar para atualizá-lo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Isso desinstala equipes de arquivos de programa.

## <a name="known-issues-and-limitations"></a>Problemas e limitações conhecidos

A seguir está problemas conhecida e limitações para equipes de VDI.

- **Implantações de tipo de host de sessão compartilhados**: implantações de tipo de host de sessão de compartilhados (por exemplo, não é persistente VM configuração compartilhada) não estão em escopo.
- A **chamada e reuniões**:

    - Chamada e cenários de reunião não são otimizados para VDI. Esses cenários executará mal. É recomendável usar políticas de nível de usuário, conforme descrito na seção [definir diretivas para desativar o chamando-se e funcionalidade nas equipes de reunião](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .  
    - Aplicar as políticas descritas neste artigo afeta a capacidade de usar a funcionalidade de reunião e de chamada, que, dependendo das outras políticas, pode afetar outros usuários em sua organização. Se os usuários em sua organização usarem os clientes não-VDI, você pode optar por não aplicar as políticas.  

- **Ingressando em chamadas e reuniões criados por outros usuários**: Embora as políticas de restringem os usuários da criação de reuniões, eles ainda podem ingressar em reuniões se outro usuário discar para acessá-los da reunião. Nessas reuniões, a capacidade do usuário para compartilhar vídeo, usar quadro de comunicações e outros recursos dependem se você desabilitou esses recursos usando TeamsMeetingPolicy.  
- **Cache de conteúdo**: se for o ambiente virtual no quais as equipes de execução não é persistente (e dados limpos no final de cada sessão do usuário), os usuários podem observar a diminuição do desempenho devido à atualização de conteúdo, independentemente se o usuário acessada a mesma conteúdo em uma sessão anterior.
- **Atualizações do cliente**: equipes de VDI não é atualizado automaticamente como a forma como os clientes não - VDI equipes estão.  Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção [Instalar equipes em VDI](#install-teams-on-vdi) . Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- **Experiência do usuário**: equipes a experiência do usuário em um ambiente VDI pode ser diferente de um ambiente de não-VDI. As diferenças podem ser devido às configurações de política e/ou o recurso de suporte no ambiente.

Para as equipes problemas conhecidos que não estão relacionados ao VDI, consulte [problemas para equipes da Microsoft conhecidos](Known-issues.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar usando o MSI Teams da Microsoft](msi-deployment.md)