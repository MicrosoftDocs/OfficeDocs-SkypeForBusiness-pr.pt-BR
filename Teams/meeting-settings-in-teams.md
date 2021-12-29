---
title: Gerenciar configurações da reunião
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Aprenda a gerenciar as configurações das reuniões do Teams que os usuários agendam em sua organização.
ms.openlocfilehash: ed042552ea6057c8184b4dad444afa543550b052
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625912"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gerenciar configurações de reunião no Microsoft Teams

Como administrador, você usa as configurações de reunião do Teams para controlar se usuários anônimos podem participar de reuniões do Teams, personalizar convites para reuniões e, se desejar habilitar a Qualidade de Serviço (QoS), definir intervalos de portas para tráfego em tempo real. Essas configurações se aplicam a todas as reuniões do Teams que os usuários agendam na sua organização. Você gerencia essas configurações em **Reuniões** > **Configurações de reunião** no centro de administração do Microsoft Teams.

Por meio de uma configuração de política por organizador, os administradores agora podem controlar se usuários específicos ou grupos de usuários podem permitir que usuários anônimos participem das reuniões que organizam. As configurações de política por organizador e de toda a organização controlam a junção anônima e a mais restritiva entra em vigor.

> [!Important]
 > **-DisableAnonymousJoin** é a configuração de política em toda a organização. Ela será preterida no futuro e, em seguida, a política por organizador será a única maneira de controlar o ingresso anônimo.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que usuários anônimos ingressem em reuniões

Com o ingresso anônimo, qualquer pessoa pode ingressar na reunião como um usuário anônimo clicando no link do convite para a reunião. Para saber mais, consulte [Ingressar em uma reunião sem uma conta do Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). Você pode controlar a capacidade dos usuários anônimos de ingressar em reuniões no nível da organização ou por organizador da reunião usando duas configurações de política diferentes.

 ### <a name="using-the-microsoft-teams-admin-center-to-configure-organization-wide-policy"></a>Usando o Centro de administração do Microsoft Teams para configurar a política em toda a organização

Você deve ser um administrador do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).

2. Na navegação à esquerda, vá para **Encontros** > **Configurações de reunião**.

3. Em **Participantes**, ative **Usuários anônimos podem ingressar em uma reunião**.

    ![Captura de tela das configurações dos participantes para reuniões no centro de administração.](media/meeting-settings-participants.png "Captura de tela das configurações dos participantes das reuniões do Teams no centro de administração do Microsoft Teams")

> [!CAUTION]
> Se você não deseja que usuários anônimos participem de reuniões agendadas por usuários em sua organização, desative essa configuração.

### <a name="using-powershell-to-configure-per-organizer-policy"></a>Usar o PowerShell para configurar a política por organizador

Os administradores agora podem controlar se usuários específicos ou grupos de usuários podem permitir que usuários anônimos participem das reuniões que organizam. Essa nova política por organizador é controlada usando o parâmetro **-AllowAnonymousUsersToJoinMeeting** em [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Isso vem com o PowerShell do Teams versão 2.6.0 e posterior.

Você pode usar qualquer política, para toda a organização ou por organizador, para gerenciar o ingresso anônimo. Recomendamos que você implemente a política por organizador. A configuração de política em toda a organização será preterida no futuro e a política por organizador será a única maneira de controlar o ingresso anônimo.

Como as políticas de toda a organização e por organizador controlam o ingresso anônimo, a configuração mais restritiva será efetiva. Por exemplo, se você não permitir o ingresso anônimo no nível da organização, essa será sua política efetiva, independentemente do que você configurar para a política por organizador. Portanto, para permitir que usuários anônimos participem de reuniões, você deve configurar ambas as políticas para permitir o ingresso anônimo definindo os seguintes valores:

- **-DisableAnonymousJoin** definido como **$false**
- **-AllowAnonymousUsersToJoinMeeting** definido como **$true**

Qualquer outra combinação de valores impedirá que usuários anônimos participem de reuniões.
> [!NOTE]
> Para usar a política por organizador para organizações com o ingresso anônimo desativado por organização, os administradores precisam criar uma política e atribuí-la aos usuários. Para saber como fazer isso, consulte [Gerenciar políticas de reunião no Microsoft Teams](/microsoftteams/meeting-policies-overview).


## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>Permitir que usuários anônimos interajam com aplicativos em reuniões

Os usuários anônimos agora herdarão a política de permissão padrão global no nível do usuário. Esse controle permitirá que usuários anônimos interajam com aplicativos em reuniões do Teams, desde que a política de permissão em nível de usuário tenha habilitado o aplicativo. Observe que usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos. 

> [!IMPORTANT]
> Por padrão, a configuração para permitir que usuários anônimos interajam com aplicativos em reuniões está habilitada.

 **Usando o centro de administração do Microsoft Teams**

Você deve ser um administrador de serviço do Teams para acessar esta configuração. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).

2. Na navegação à esquerda, vá para **Encontros** > **Configurações de reunião**.

3. Sob **Participantes**, a configuração para **Usuários anônimos podem interagir com aplicativos em reuniões** pode ser mudado.

> [!CAUTION]
> Se você não deseja que usuários anônimos interajam com aplicativos em reuniões agendadas por usuários em sua organização, desative esta configuração.

## <a name="customize-meeting-invitations"></a>Personalizar convites para reuniões

Você pode personalizar os convites de reunião do Teams para atender às necessidades da sua organização. Você pode adicionar o logotipo da sua organização e incluir informações úteis, como links para seu site de suporte e aviso de isenção de responsabilidade legal e um rodapé somente texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Dicas para criar um logotipo para convites de reuniões  

1. Crie uma imagem com no máximo 188 pixels de largura por 30 pixels de altura (bastante pequena).
2. Salve a imagem no formato JPG ou PNG.
3. Armazene a imagem em um local que todos os que receberem o convite possam acessar, como um site público.

    Agora você pode adicioná-la aos seus convites para reuniões. Veja as próximas etapas.

### <a name="customize-your-meeting-invitations"></a>Personalize seus convites para reuniões

 **Usando o centro de administração do Microsoft Teams**

1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).
2. Na navegação à esquerda, vá para **Encontros** > **Configurações de reunião**.
3. Em **Convite por email**, faça o seguinte:

    ![Captura de tela das configurações de convite para reunião que você pode personalizar.](media/meeting-settings-invitation.png "Captura de tela das configurações de convite de reunião que você pode personalizar para reuniões do Teams")

    - **URL do logotipo** Digite a URL em que seu logotipo está armazenado.
    - **URL jurídica** Se sua organização possui um site jurídico que você deseja que as pessoas acessem para quaisquer questões jurídicas, digite a URL aqui.
    - **URL de ajuda** Se a sua organização tiver um site de suporte que você deseja que as pessoas acessem se tiverem problemas, digite a URL aqui.
    - **Rodapé** Digite o texto que você deseja incluir como rodapé.
4. Clique em **Visualizar convite** para ver uma prévia do seu convite para a reunião.
5. Quando terminar, clique em **Salvar**.
6. Aguarde cerca de uma hora para que as alterações sejam propagadas. Em seguida, agende uma reunião do Teams para ver como é o convite da reunião.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Defina como você deseja lidar com o tráfego de mídia em tempo real nas reuniões do Teams

<a name="bknetwork"> </a>

Se você estiver usando a Qualidade de Serviço (QoS) para priorizar o tráfego de rede, poderá habilitar marcadores de QoS e definir intervalos de portas para cada tipo de tráfego de mídia. Definir intervalos de portas para diferentes tipos de tráfego é apenas uma etapa no tratamento de mídia em tempo real; consulte [Qualidade de serviço (QoS) no Teams](qos-in-teams.md) para obter muito mais detalhes.

> [!IMPORTANT]
> Sistemas baseados na Apple: A única instância que sabemos de onde os dispositivos baseados na Apple realmente definem o valor DSCP é se todas as condições a seguir forem atendidas:
> - iOS.
> - Rede Wi-Fi.
> - Comutadores Cisco.
> - O administrador da rede adicionou o aplicativo à lista de aprovados.
>
> Sistemas baseados em Android: Não há limitações conhecidas.
>
> Se você habilitar o QoS ou alterar as configurações no centro de administração do Microsoft Teams para o serviço Teams, também precisará [ aplicar configurações correspondentes a todos os dispositivos do usuário](QoS-in-Teams-clients.md) e todos os dispositivos de rede internos para implementar totalmente as alterações de QoS no Teams.

  **Usando o centro de administração do Microsoft Teams**
1. Vá para o [Centro de administração do Teams](https://admin.teams.microsoft.com).
2. Na navegação à esquerda, vá para **Encontros** > **Configurações de reunião**.
3. Em **Rede**, faça o seguinte:

    ![Captura de tela das configurações de rede para reuniões no centro de administração.](media/meeting-settings-network.png "Captura de tela das configurações de rede para reuniões do Teams no centro de administração do Microsoft Teams")

    - Para permitir que as marcações DSCP sejam usadas para QoS, ative os **Marcadores de QoS (Qualidade de Serviço) para tráfego de mídia em tempo real**. Você só tem a opção de usar ou não usar marcadores; você não pode definir marcadores personalizados para cada tipo de tráfego. Consulte [Selecionar um método de implementação de QoS](QoS-in-Teams.md#select-a-qos-implementation-method) para obter mais informações sobre marcadores DSCP.

        > [!IMPORTANT]
        > Observe que a habilitação da QoS somente é executada nos pontos de extremidade para marcar os pacotes que saem do cliente. Ainda recomendamos aplicar as regras de QoS correspondentes em todos os dispositivos de rede internos para o tráfego de entrada.
        
        > [!NOTE]
        > A marcação DSCP é normalmente feita por meio de portas de origem e o tráfego UDP será roteado para o retransmissão de transporte com a porta de destino 3478 por padrão. Se sua empresa exigir marcação nas portas de destino, entre em contato com o suporte para habilitar a comunicação com o Transport Relay com as portas UDP 3479 (Áudio), 3480 (Vídeo) e 3481 (Compartilhamento).
    - Para especificar os intervalos de portas, ao lado de **Selecionar um intervalo de portas para cada tipo de tráfego de mídia em tempo real**, selecionar  **Especificar intervalos de portas**, e então digitar as portas inicial e final para áudio, vídeo e compartilhamento de tela. A seleção desta opção é necessária para implementar a QoS. 
        > [!Note]
        > Se **Marcadores de Qualidade de Serviço (QoS) para tráfego de mídia em tempo real** estiver ligado, então você tem que gerenciar suas configurações de porta. Eles não são gerenciados automaticamente.
        
        > [!IMPORTANT]
        > Se você selecionar **Usar automaticamente qualquer porta disponível**, serão usadas portas disponíveis entre 1024 e 65535. Use esta opção apenas quando não estiver implementando a QoS.
        >
        > A seleção de um intervalo de portas muito restrito resultará em queda de chamadas e baixa qualidade de chamadas. As recomendações abaixo devem ser o mínimo.

Se você não tiver certeza de quais intervalos de portas usar em seu ambiente, as seguintes configurações são um bom ponto de partida. Para saber mais, leia [Implementar a Qualidade de Serviço (QoS) no Microsoft Teams](QoS-in-Teams.md). Esses são os marcadores DSCP necessários e os intervalos de portas de mídia correspondentes sugeridos usados pelo Teams e pelo ExpressRoute.

### <a name="port-ranges-and-dscp-markings"></a>Intervalos de portas e marcações DSCP

Tipo de tráfego de mídia| Intervalo de portas de origem do cliente \* |Protocolo|Valor DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Áudio            | 50.000–50.019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Vídeo            | 50.020–50.039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\* Os intervalos de porta que você atribui não podem se sobrepor e devem ser adjacentes uns aos outros.

Depois que a QoS estiver em uso por algum tempo, você terá informações de uso sobre a demanda para cada uma dessas três cargas de trabalho, e poderá escolher que mudanças fazer com base em suas necessidades específicas. [O Painel de Qualidade de Chamadas](turning-on-and-using-call-quality-dashboard.md) será útil para isso.
