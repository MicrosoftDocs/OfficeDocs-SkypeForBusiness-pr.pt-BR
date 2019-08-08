---
title: Gerenciar configurações de reunião
author: lanachin
ms.author: v-lanac
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
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como gerenciar as configurações de reuniões do Team que os usuários agendam em sua organização.
ms.openlocfilehash: c26165abdc753fbe37d3465738200c43b42d087d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236555"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gerenciar configurações de reunião no Microsoft Teams

Como administrador, você usa as configurações de reuniões do teams para controlar se os usuários anônimos podem ingressar em reuniões do Teams, personalizar convites de reunião e se você deseja habilitar a QoS (qualidade de serviço), definir intervalos de porta para tráfego em tempo real. Essas configurações se aplicam a todas as reuniões do teams que os usuários agendam em sua organização. Você gerencia essas configurações de **** > **configurações de reunião** de reuniões no centro de administração do Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que usuários anônimos ingressem em reuniões

Com a junção anônima, qualquer pessoa pode ingressar na reunião como usuário anônimo clicando no link no convite da reunião.

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para**configurações de reunião**de **reuniões** > .
2. Em **participantes**, ativar **usuários anônimos podem ingressar em uma reunião**.

    ![Captura de tela das configurações de participantes para reuniões no centro de administração] (media/meeting-settings-participants.png "Captura de tela das configurações de participantes para reuniões do teams no centro de administração do Microsoft Teams")

Se você não quiser que os usuários anônimos ingressem em reuniões agendadas pelos usuários da sua organização, desative essa configuração.

## <a name="customize-meeting-invitations"></a>Personalizar convites de reunião

Você pode personalizar convites de reunião do teams para atender às necessidades da sua organização. Você pode adicionar o logotipo da sua organização e incluir informações úteis, como links para seu site de suporte e isenção de responsabilidade e um rodapé somente texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Dicas para criar um logotipo para convites de reunião  

1. Crie uma imagem que não tenha mais de 188 pixels de largura por 30 pixels de altura (é muito pequena).
2. Salve a imagem no formato JPG ou PNG.
3. Armazene a imagem em um local central que todos em sua organização possam acessar, como um compartilhamento de rede.

    Agora você pode adicioná-lo aos convites para reunião. Veja as próximas etapas.

### <a name="customize-your-meeting-invitations"></a>Personalizar seus convites de reunião

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para**configurações de reunião**de **reuniões** > .
2. Em **convite por email**, faça o seguinte:

    ![Captura de tela das configurações de convite de reunião que você pode personalizar] (media/meeting-settings-invitation.png "Captura de tela das configurações de convite de reunião que você pode personalizar para reuniões do teams")

    - **URL do logotipo** Digite a URL onde o seu logotipo está armazenado.
    - **URL legal** Se a sua organização tiver um site legal para o qual você deseja que as pessoas vá para qualquer preocupação legal, insira a URL aqui.
    - **URL da ajuda** Se a sua organização tiver um site de suporte para o qual você deseja que as pessoas possam acessar, insira a URL aqui.
    - **Rodapé** Insira o texto que você deseja incluir como um rodapé.
3. Aguarde uma hora ou para que as alterações sejam propagadas. Em seguida, agende uma reunião do teams para ver a aparência do convite da reunião.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Defina como você deseja manipular o tráfego de mídia em tempo real para reuniões de equipes

<a name="bknetwork"> </a>

Se você estiver usando a [QoS (](qos-in-teams.md) qualidade de serviço) para priorizar o tráfego de rede, poderá habilitar os marcadores de QoS e poderá definir intervalos de porta para cada tipo de tráfego de mídia.

 ![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para**configurações de reunião**de **reuniões** > .
2. Em **rede**, faça o seguinte:

    ![Captura de tela das configurações de rede para reuniões no centro de administração] (media/meeting-settings-network.png "Captura de tela das configurações de rede para reuniões do teams no centro de administração do Microsoft Teams")

    - Para permitir que as marcações DSCP sejam usadas para a QoS, ative **Inserir marcadores de qualidade de serviço (QoS) para tráfego de mídia em tempo real**. Você só tem a opção de usar marcadores ou não; Você não pode definir marcadores personalizados para cada tipo de tráfego. Consulte [selecionar um método de implementação de QoS](QoS-in-Teams.md#select-a-qos-implementation-method) para saber mais sobre marcadores DSCP.
    - Para especificar intervalos de porta, ao lado de **selecionar um intervalo de portas para cada tipo de tráfego de mídia em tempo real**, selecione **especificar intervalos de porta**e insira as portas inicial e final para o áudio, o vídeo e o compartilhamento de tela. Selecionar essa opção é necessária para implementar QoS.
    > [!IMPORTANT]
    > Se você selecionar **usar automaticamente as portas disponíveis**, as portas disponíveis entre 1024 e 65535 serão usadas. Use essa opção somente quando não estiver implementando a QoS.
    >
    > A seleção de um intervalo de porta muito estreito levará a chamadas e a uma baixa qualidade da chamada. As recomendações a seguir devem ser um mínimo simples.

 Se você não tiver certeza de quais intervalos de porta usar no seu ambiente, as configurações a seguir são um bom ponto de partida. Para saber mais, leia [implementar qualidade de serviço (QoS) no Microsoft Teams](QoS-in-Teams.md). Estas são as marcações DSCP necessárias e os intervalos de porta de mídia sugeridos correspondentes usados pelo Teams e pela rota expressa.

_Intervalos de porta e marcações DSCP_

Tipo de tráfego de mídia| Intervalo de porta de origem do cliente\* |Protocolo|Valor de DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Áudio            | 50000 – 50019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Vídeo            | 50,020–50,039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50,040–50,059      |TCP/UDP |dezoito        |Encaminhamento garantido (AF21)|
| | | | |

\*Os intervalos de porta que você atribui não podem ser sobrepostos e devem ser adjacentes entre si.

A configuração de intervalos de porta para diferentes tipos de tráfego é apenas uma etapa na manipulação da mídia em tempo real; consulte [QoS (qualidade de serviço) no Teams](qos-in-teams.md) para obter muito mais detalhes. Se você habilitar ou alterar as configurações no centro de administração do Microsoft Teams, será necessário [aplicar configurações correspondentes a todos os dispositivos de usuário](QoS-in-Teams-clients.md) e dispositivos de rede interna para implementar completamente as alterações no QoS no Microsoft Teams.

Depois que a QoS estiver em uso por algum tempo, você terá informações de uso sobre a demanda de cada uma dessas três cargas de trabalho e poderá escolher quais alterações devem ser feitas com base em suas necessidades específicas. O [painel de qualidade de chamada](turning-on-and-using-call-quality-dashboard.md) será útil para isso.
