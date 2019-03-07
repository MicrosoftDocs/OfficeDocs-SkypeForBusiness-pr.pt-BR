---
title: Gerenciar configurações de reunião
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como gerenciar configurações para reuniões de equipes que os usuários a agendar em sua organização.
ms.openlocfilehash: ad48e44ef475d3643444cfb570e81d8224117133
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462640"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gerenciar configurações de reunião no Microsoft Teams

Como um administrador, você usar configurações de reuniões de equipes para controlar se os usuários anônimos podem participar de reuniões de equipes, personalizar convites de reunião e se você deseja habilitar Quality of Service (QoS), defina os intervalos de porta para o tráfego em tempo real. Essas configurações se aplicam a todas as reuniões de equipes que agenda de usuários em sua organização. Gerenciar essas definições de **reuniões** > **configurações de reunião** no Centro de administração do Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que usuários anônimos ingressem em reuniões

Com o ingresso anônimo, qualquer pessoa pode ingressar na reunião como um usuário anônimo, clicando no link no convite da reunião.

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.
2. Em **participantes**, ative **os usuários anônimos podem ingressar em uma reunião**.

    ![reunião-configurações-participants.png] (media/meeting-settings-participants.png "Captura de tela das configurações de participantes de reuniões de equipes no Centro de administração de equipes da Microsoft")

Se você não desejar que usuários anônimos para participar de reuniões agendadas por usuários em sua organização, desative esta configuração.

## <a name="customize-meeting-invitations"></a>Personalizar convites de reunião

Você pode personalizar convites de reunião de equipes para atender às necessidades da sua organização. Você pode adicionar o logotipo da sua organização e incluir informações úteis, como links para seu site de suporte e o aviso de isenção legal e um rodapé somente texto.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Dicas para criar um logotipo para convites de reunião  

1. Crie uma imagem que é não ultrapassa 188 pixels de largura por 30 pixels de altura (é muito pequeno).
2. Salve a imagem no formato JPG.
3. Armazene a imagem em um local central que todos em sua organização possam acessar, como em um compartilhamento de rede.

### <a name="customize-your-meeting-invitations"></a>Personalizar seus convites de reunião

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.
2. Em um **convite por Email**, faça o seguinte:

    ![reunião-configurações-invitation.png] (media/meeting-settings-invitation.png "Captura de tela da reunião configurações de convite que você pode personalizar para reuniões de equipes")

    - **URL do logotipo** Insira a URL onde o logotipo de sua está armazenado.
    - **URL legal** Se sua organização tem um site legal que você deseja que as pessoas ir para de qualquer preocupações legais, insira a URL aqui.
    - **URL da Ajuda** Se sua organização tem um site de suporte que você deseja que as pessoas se eles encontrar problemas, insira a URL aqui.
    - **Rodapé** Insira o texto que você deseja incluir como um rodapé.
3. Aguarde uma hora ou mais para que as alterações sejam propagadas. Em seguida, agende uma reunião de equipes para ver a aparência de convite da reunião.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Definir como você deseja lidar com o tráfego de mídia em tempo real para reuniões de equipes

<a name="bknetwork"> </a>

Se você estiver usando o Quality of Service [(QoS)](qos-in-teams.md) para priorizar o tráfego de rede, é possível habilitar o QoS marcadores e você pode definir intervalos de porta para cada tipo de tráfego de mídia.

 ![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.
2. Em **rede**, faça o seguinte:

    ![reunião-configurações-network.png] (media/meeting-settings-network.png "Captura de tela das configurações de rede para reuniões de equipes no Centro de administração de equipes da Microsoft")

    - Para permitir que as marcações de DSCP a ser usado para QoS, ative **os marcadores de inserir Quality of Service (QoS) para tráfego de mídia em tempo real**. Você só tem a opção de usar os marcadores ou não, você não pode definir marcadores personalizadas para cada tipo de tráfego. Consulte [Selecionar um método de implementação de QoS](QoS-in-Teams.md#select-a-qos-implementation-method) para marcadores de DSCP diante mais.
    - Para especificar os intervalos de porta, ao lado de **Selecionar um intervalo de porta para cada tipo de tráfego de mídia em tempo real**, selecione **especificar intervalos de porta**e, em seguida, insira as portas inicial e finais para áudio, vídeo e compartilhamento de tela. Esta opção é necessária para implementar o QoS.
    > [!IMPORTANT]
    > Se você selecionar **usar automaticamente qualquer porta disponível**, portas disponíveis entre 1024 e 65535 são usados. Use essa opção somente quando não implementando QoS.
    >
    > Selecionar um intervalo de portas é muito estreito levarão à redução capitular chamadas e chamada de baixa qualidade. As recomendações a seguir devem ser mínimo.

 Se você não tiver certeza de qual porta intervalos para usar em seu ambiente, as configurações a seguir são um bom ponto de partida. Para saber mais, leia [Implementar Quality of Service (QoS) em equipes da Microsoft](QoS-in-Teams.md). Estas são as marcas de DSCP necessárias e a mídia correspondente sugerida usados por equipes e ExpressRoute de intervalos da porta.

_Intervalos de porta e as marcações de DSCP_

Tipo de tráfego de mídia| Intervalo de porta de origem do cliente\* |Protocolo|Valor de DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Áudio            | 50.000 – 50,019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Vídeo            | 50,020 – 50,039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Compartilhamento de tela do aplicativo| 50,040 – 50,059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\*Os intervalos de porta que você atribuir não podem sobrepor-se e devem ser adjacentes entre si.

Configurando intervalos de portas para diferentes tipos de tráfego é apenas uma etapa do tratamento de mídia de tempo real, consulte [Quality of a Service (QoS) em equipes](qos-in-teams.md) for muito mais detalhes. Se você ativar ou alterar as configurações no Centro de administração de equipes, você precisará [Aplicar configurações correspondentes a todos os dispositivos do usuário](QoS-in-Teams-clients.md) e os dispositivos de rede interna totalmente implementar as alterações a serem QoS em equipes.

Depois de QoS tenha sido usado por um tempo, você terá informações de uso sobre a demanda para cada uma dessas três cargas de trabalho e você pode escolher quais alterações a serem feitas com base em suas necessidades específicas. [Painel de qualidade de chamada](turning-on-and-using-call-quality-dashboard.md) serão úteis com isso.