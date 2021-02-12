---
title: Gerenciar configurações da reunião
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
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
ms.openlocfilehash: d3301c8232fda2133e77f973ca0efbc13cfa571d
ms.sourcegitcommit: c6b999226294aeea98dafa9ef5f0bd256fcb6a0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49903562"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gerenciar configurações de reunião no Microsoft Teams

Como administrador, você usa as configurações de reunião do Teams para controlar se usuários anônimos podem participar de reuniões do Teams, personalizar convites para reuniões e, se desejar habilitar a Qualidade de Serviço (QoS), definir intervalos de portas para tráfego em tempo real. Essas configurações se aplicam a todas as reuniões do Teams que os usuários agendam na sua organização. Você gerencia essas configurações em **Reuniões** > **Configurações de reunião** no centro de administração do Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que usuários anônimos ingressem em reuniões

Com o ingresso anônimo, qualquer pessoa pode ingressar na reunião como um usuário anônimo clicando no link do convite para a reunião. Para saber mais, consulte [Ingressar em uma reunião sem uma conta do Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

Você deve ser um administrador do serviço do Teams para fazer essas alterações. Confira [as funções de administrador do Teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.

1. Vá para o centro de administração.

2. Na barra de navegação à esquerda, vá para **Reuniões** > **Configurações de reunião**.

3. Em **Participantes**, ative **Usuários anônimos podem ingressar em uma reunião**.

    ![Captura de tela das configurações dos participantes para reuniões no centro de administração](media/meeting-settings-participants.png "Captura de tela das configurações dos participantes das reuniões do Teams no centro de administração do Microsoft Teams")

> [!CAUTION]
> Se você não deseja que usuários anônimos participem de reuniões agendadas por usuários em sua organização, desative essa configuração.

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>Permitir que usuários anônimos interajam com aplicativos em reuniões

Os usuários anônimos agora herdarão a política de permissão padrão global em nível de usuário. Esse controle permitirá que usuários anônimos interajam com aplicativos em reuniões do Teams, desde que a política de permissão no nível do usuário tenha habilitado o aplicativo. Observe que os usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos. 

> [!IMPORTANT]
> Por padrão, a configuração para permitir que usuários anônimos interajam com aplicativos em reuniões está habilitada.

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

Você deve ser um administrador de serviço do Teams para acessar essa configuração. Confira [as funções de administrador do Teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.

1. Vá para o centro de administração.

2. Na barra de navegação à esquerda, vá para **Reuniões** > **Configurações de reunião**.

3. Em **Participantes,** a configuração para **usuários anônimos pode interagir com aplicativos em reuniões** pode ser alterada.

> [!CAUTION]
> Se você não quiser que usuários anônimos interajam com aplicativos em reuniões agendadas por usuários em sua organização, desligue essa configuração.

## <a name="customize-meeting-invitations"></a>Personalizar convites para reuniões

Você pode personalizar os convites para reuniões do Teams para atender às necessidades da sua organização. Você pode adicionar o logotipo da sua organização e incluir informações úteis, como links para o site de suporte, aviso legal e um rodapé somente texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Dicas para criar um logotipo para convites de reuniões  

1. Crie uma imagem com no máximo 188 pixels de largura por 30 pixels de altura (bastante pequena).
2. Salve a imagem no formato JPG ou PNG.
3. Armazene a imagem em um local que todos os que receberem o convite possam acessar, como um site público.

    Agora você pode adicioná-la aos seus convites para reuniões. Veja os próximos passos.

### <a name="customize-your-meeting-invitations"></a>Personalize seus convites para reuniões

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Vá para o centro de administração.
2. Na barra de navegação à esquerda, vá para **Reuniões** > **Configurações de reunião**.
3. Em **Convite por email**, faça o seguinte:

    ![Captura de tela das configurações de convite para reunião que você pode personalizar](media/meeting-settings-invitation.png "Captura de tela das configurações de convite de reunião que você pode personalizar para reuniões do Teams")

    - **URL do logotipo** Digite a URL em que seu logotipo está armazenado.
    - **URL jurídica** Se sua organização possui um site jurídico que você deseja que as pessoas acessem para quaisquer questões jurídicas, digite a URL aqui.
    - **URL de ajuda** Se a sua organização tiver um site de suporte que você deseja que as pessoas acessem se tiverem problemas, digite a URL aqui.
    - **Rodapé** Digite o texto que você deseja incluir como rodapé.
4. Clique em **Visualizar convite** para ver uma prévia do seu convite para a reunião.
5. Quando terminar, clique em **Salvar**.
6. Aguarde cerca de uma hora para que as alterações sejam propagadas. Em seguida, agende uma reunião do Teams para ver como é o convite da reunião.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Defina como você deseja lidar com o tráfego de mídia em tempo real nas reuniões do Teams

<a name="bknetwork"> </a>

Se estiver usando QoS (Qualidade de Serviço) para priorizar o tráfego de rede, você pode habilitar marcadores QoS e definir intervalos de porta para cada tipo de tráfego de mídia. Definir intervalos de portas para diferentes tipos de tráfego é apenas uma etapa no tratamento de mídia em tempo real; consulte [Qualidade de serviço (QoS) no Teams](qos-in-teams.md) para obter muito mais detalhes.

> [!IMPORTANT]
> Se você habilitar a QoS ou alterar as configurações no Centro de administração do Microsoft Teams para o serviço do Teams, também precisará aplicar configurações correspondentes a todos os dispositivos de usuário e a todos os [dispositivos](QoS-in-Teams-clients.md) de rede interna para implementar totalmente as alterações no QoS no Teams.

 ![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**
1. Vá para o centro de administração.
2. Na barra de navegação à esquerda, vá para **Reuniões** > **Configurações de reunião**.
3. Em **Rede**, faça o seguinte:

    ![Captura de tela das configurações de rede para reuniões no centro de administração](media/meeting-settings-network.png "Captura de tela das configurações de rede para reuniões do Teams no centro de administração do Microsoft Teams")

    - Para permitir que marcadores DSCP sejam usados para QoS, ative **Inserir marcadores Quality of Service (QoS) para tráfego de mídia em tempo real**. Você só tem a opção de usar ou não usar marcadores; você não pode definir marcadores personalizados para cada tipo de tráfego. Consulte [Selecionar um método de implementação de QoS](QoS-in-Teams.md#select-a-qos-implementation-method) para obter mais informações sobre marcadores DSCP.
        > [!NOTE]
        > A marcação DSCP normalmente é feita por meio de Portas de Origem e o tráfego UDP roteia para a Retransmissão de Transporte com a porta de destino 3478 por padrão. Se sua empresa exigir marcação nas portas de destino, entre em contato com o suporte para habilitar a comunicação com a Retransmissão de Transporte com as portas UDP 3479 (Áudio), 3480 (Vídeo) e 3481 (Compartilhamento).
    - Para especificar intervalos de portas, ao lado de **Selecione um intervalo de portas para cada tipo de tráfego de mídia em tempo real**, selecione **Especificar intervalos de portas** e insira as portas inicial e final para compartilhamento de áudio, vídeo e tela. A seleção desta opção é necessária para implementar a QoS. 
        > [!Note]
        > Se **os marcadores QoS (Qualidade** do Serviço) para tráfego de mídia em tempo real estiver on, então você terá que gerenciar as configurações da porta. Eles não são gerenciados automaticamente.
        
        > [!IMPORTANT]
        > Se você selecionar **Usar automaticamente qualquer porta disponível**, serão usadas portas disponíveis entre 1024 e 65535. Use esta opção apenas quando não estiver implementando a QoS.
        >
        > A seleção de um intervalo de portas muito restrito resultará em queda de chamadas e baixa qualidade de chamadas. As recomendações abaixo devem ser o mínimo.

Se você não tiver certeza de quais intervalos de portas usar em seu ambiente, as seguintes configurações são um bom ponto de partida. Para saber mais, leia [Implementar a Qualidade de Serviço (QoS) no Microsoft Teams](QoS-in-Teams.md). Esses são os marcadores DSCP necessários e os intervalos de portas de mídia correspondentes sugeridos usados pelo Teams e pelo ExpressRoute.

### <a name="port-ranges-and-dscp-markings"></a>Intervalos de portas e marcadores DSCP

Tipo de tráfego de mídia| Intervalo de portas de origem do cliente \* |Protocolo|Valor DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Áudio            | 50.000–50.019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Vídeo            | 50.020–50.039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\* Os intervalos de porta que você atribuir não podem se sobrepor e devem ser adjacentes uns aos outros.

Depois que a QoS estiver em uso por um tempo, você terá informações de uso sobre a demanda para cada uma dessas três cargas de trabalho e poderá escolher as alterações a serem feitas com base em suas necessidades específicas. O [Painel de Qualidade de Chamadas](turning-on-and-using-call-quality-dashboard.md) ajudará com isso.
