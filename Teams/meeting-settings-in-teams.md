---
title: Gerenciar configurações de reunião no Microsoft Teams
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
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: Saiba como gerenciar configurações para reuniões de equipes que os usuários a agendar em sua organização.
ms.openlocfilehash: bf7350d94f61fcbaff60dacb161d5096b8f549e7
ms.sourcegitcommit: 72afa227b917f9fabd278fc7bea9d515b5d53def
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2018
ms.locfileid: "26671008"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gerenciar configurações de reunião no Microsoft Teams

Como um administrador, você usar configurações de reuniões de equipes para controlar se os usuários anônimos podem participar de reuniões de equipes, personalizar convites de reunião e se você deseja habilitar Quality of Service (QoS), defina as portas para o tráfego em tempo real. Essas configurações se aplicam a todas as reuniões de equipes que agenda de usuários em sua organização. Gerenciar essas definições de **reuniões** > **configurações de reunião** no Microsoft Teams & Skype para Business Admin Center. 

## <a name="allow-anonymous-users-to-join-meetings"></a>Permitir que usuários anônimos ingressem em reuniões

Com o ingresso anônimo, qualquer pessoa pode ingressar na reunião como um usuário anônimo, clicando no link no convite da reunião. 

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) Usando as equipes da Microsoft & Skype para Business Admin Center
1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**. 
2. Em **participantes**, ative **os usuários anônimos podem ingressar em uma reunião**. 

    ![reunião-configurações-participants.png] (media/meeting-settings-participants.png "Captura de tela das configurações de participantes de reuniões de equipes no Skype para Business Admin Center & equipes da Microsoft")

Se você não desejar que usuários anônimos para participar de reuniões agendadas por usuários em sua organização, desative esta configuração. 
## <a name="customize-meeting-invitations"></a>Personalizar convites de reunião

Você pode personalizar convites de reunião de equipes para atender às necessidades da sua organização. Você pode adicionar o logotipo da sua organização e incluir informações úteis, como links para seu site de suporte e o aviso de isenção legal e um rodapé somente texto. 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Dicas para criar um logotipo para convites de reunião  

1. Crie uma imagem que é não ultrapassa 188 pixels de largura por 30 pixels de altura (é muito pequeno). 
2. Salve a imagem no formato JPG. 
3. Armazene a imagem em um local central que todos em sua organização possam acessar, como em um compartilhamento de rede. 

### <a name="customize-your-meeting-invitations"></a>Personalizar seus convites de reunião

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) Usando as equipes da Microsoft & Skype para Business Admin Center

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.
2. Em um **convite por Email**, faça o seguinte: 

    ![reunião-configurações-invitation.png] (media/meeting-settings-invitation.png "Captura de tela da reunião configurações de convite que você pode personalizar para reuniões de equipes") 

    - **URL do logotipo** Insira a URL onde o logotipo de sua está armazenado. 
    - **URL legal** Se sua organização tem um site legal que você deseja que as pessoas ir para de qualquer preocupações legais, insira a URL aqui. 
    - **URL da Ajuda** Se sua organização tem um site de suporte que você deseja que as pessoas se eles encontrar problemas, insira a URL aqui.
    - **Rodapé** Insira o texto que você deseja incluir como um rodapé. 
3. Aguarde uma hora ou mais para que as alterações sejam propagadas. Em seguida, agende uma reunião de equipes para ver a aparência de convite da reunião.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings-coming-soon"></a>Definir como você deseja lidar com o tráfego de mídia em tempo real para reuniões de equipes (em breve) 
Se você estiver usando o Quality of Service (QoS) para priorizar o tráfego de rede, é possível habilitar o QoS marcadores e você pode definir intervalos de porta para cada tipo de tráfego de mídia. 

 ![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) Usando o Microsoft Teams & Skype para centro de administração de negócios

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**. 
2. Em **rede**, faça o seguinte:

    ![reunião-configurações-network.png] (media/meeting-settings-network.png "Captura de tela das configurações de rede para reuniões de equipes no Skype para Business Admin Center & equipes da Microsoft")

    - Para habilitar o QoS marcadores, ative **os marcadores de inserir Quality of Service (QoS) para tráfego de mídia em tempo real**.
    - Para especificar os intervalos de porta, ao lado de **Selecionar um intervalo de porta para cada tipo de tráfego de mídia em tempo real**, selecione **especificar intervalos de porta**e, em seguida, insira as portas inicial e finais para áudio, vídeo e compartilhamento de tela. 
    
        Se você selecionar **usar automaticamente qualquer porta disponível**, portas disponíveis entre 1024 e 65535 são usados. 

 ### <a name="related-topics"></a>Tópicos relacionados
- [Qualidade de serviço (QoS) em equipes](qos-in-teams.md)

