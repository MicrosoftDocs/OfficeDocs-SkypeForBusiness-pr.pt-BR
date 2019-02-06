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
ms.openlocfilehash: e4eba5f585f7621add95101d06194bebead507e2
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754413"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="6adb6-103">Gerenciar configurações de reunião no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6adb6-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="6adb6-104">Como um administrador, você usar configurações de reuniões de equipes para controlar se os usuários anônimos podem participar de reuniões de equipes, personalizar convites de reunião e se você deseja habilitar Quality of Service (QoS), defina as portas para o tráfego em tempo real.</span><span class="sxs-lookup"><span data-stu-id="6adb6-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set ports for real-time traffic.</span></span> <span data-ttu-id="6adb6-105">Essas configurações se aplicam a todas as reuniões de equipes que agenda de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6adb6-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="6adb6-106">Gerenciar essas definições de **reuniões** > **configurações de reunião** no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6adb6-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span> 

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="6adb6-107">Permitir que usuários anônimos ingressem em reuniões</span><span class="sxs-lookup"><span data-stu-id="6adb6-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="6adb6-108">Com o ingresso anônimo, qualquer pessoa pode ingressar na reunião como um usuário anônimo, clicando no link no convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="6adb6-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> 

<span data-ttu-id="6adb6-109">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="6adb6-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="6adb6-110">No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.</span><span class="sxs-lookup"><span data-stu-id="6adb6-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="6adb6-111">Em **participantes**, ative **os usuários anônimos podem ingressar em uma reunião**.</span><span class="sxs-lookup"><span data-stu-id="6adb6-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span> 

    <span data-ttu-id="6adb6-112">![reunião-configurações-participants.png] (media/meeting-settings-participants.png "Captura de tela das configurações de participantes de reuniões de equipes no Centro de administração de equipes da Microsoft")</span><span class="sxs-lookup"><span data-stu-id="6adb6-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="6adb6-113">Se você não desejar que usuários anônimos para participar de reuniões agendadas por usuários em sua organização, desative esta configuração.</span><span class="sxs-lookup"><span data-stu-id="6adb6-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span> 

## <a name="customize-meeting-invitations"></a><span data-ttu-id="6adb6-114">Personalizar convites de reunião</span><span class="sxs-lookup"><span data-stu-id="6adb6-114">Customize meeting invitations</span></span>

<span data-ttu-id="6adb6-115">Você pode personalizar convites de reunião de equipes para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6adb6-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="6adb6-116">Você pode adicionar o logotipo da sua organização e incluir informações úteis, como links para seu site de suporte e o aviso de isenção legal e um rodapé somente texto.</span><span class="sxs-lookup"><span data-stu-id="6adb6-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span> 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="6adb6-117">Dicas para criar um logotipo para convites de reunião</span><span class="sxs-lookup"><span data-stu-id="6adb6-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="6adb6-118">Crie uma imagem que é não ultrapassa 188 pixels de largura por 30 pixels de altura (é muito pequeno).</span><span class="sxs-lookup"><span data-stu-id="6adb6-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span> 
2. <span data-ttu-id="6adb6-119">Salve a imagem no formato JPG.</span><span class="sxs-lookup"><span data-stu-id="6adb6-119">Save the image in JPG format.</span></span> 
3. <span data-ttu-id="6adb6-120">Armazene a imagem em um local central que todos em sua organização possam acessar, como em um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="6adb6-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span> 

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="6adb6-121">Personalizar seus convites de reunião</span><span class="sxs-lookup"><span data-stu-id="6adb6-121">Customize your meeting invitations</span></span>

<span data-ttu-id="6adb6-122">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="6adb6-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6adb6-123">No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.</span><span class="sxs-lookup"><span data-stu-id="6adb6-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="6adb6-124">Em um **convite por Email**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6adb6-124">Under **Email invitation**, do the following:</span></span> 

    <span data-ttu-id="6adb6-125">![reunião-configurações-invitation.png] (media/meeting-settings-invitation.png "Captura de tela da reunião configurações de convite que você pode personalizar para reuniões de equipes")</span><span class="sxs-lookup"><span data-stu-id="6adb6-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span> 

    - <span data-ttu-id="6adb6-126">**URL do logotipo** Insira a URL onde o logotipo de sua está armazenado.</span><span class="sxs-lookup"><span data-stu-id="6adb6-126">**Logo URL** Enter the URL where your logo is stored.</span></span> 
    - <span data-ttu-id="6adb6-127">**URL legal** Se sua organização tem um site legal que você deseja que as pessoas ir para de qualquer preocupações legais, insira a URL aqui.</span><span class="sxs-lookup"><span data-stu-id="6adb6-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span> 
    - <span data-ttu-id="6adb6-128">**URL da Ajuda** Se sua organização tem um site de suporte que você deseja que as pessoas se eles encontrar problemas, insira a URL aqui.</span><span class="sxs-lookup"><span data-stu-id="6adb6-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="6adb6-129">**Rodapé** Insira o texto que você deseja incluir como um rodapé.</span><span class="sxs-lookup"><span data-stu-id="6adb6-129">**Footer** Enter text that you want to include as a footer.</span></span> 
3. <span data-ttu-id="6adb6-130">Aguarde uma hora ou mais para que as alterações sejam propagadas.</span><span class="sxs-lookup"><span data-stu-id="6adb6-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="6adb6-131">Em seguida, agende uma reunião de equipes para ver a aparência de convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="6adb6-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="6adb6-132">Definir como você deseja lidar com o tráfego de mídia em tempo real para reuniões de equipes</span><span class="sxs-lookup"><span data-stu-id="6adb6-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>
<span data-ttu-id="6adb6-133">Se você estiver usando o Quality of Service (QoS) para priorizar o tráfego de rede, é possível habilitar o QoS marcadores e você pode definir intervalos de porta para cada tipo de tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="6adb6-133">If you're using Quality of Service (QoS) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> 

 <span data-ttu-id="6adb6-134">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="6adb6-134">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6adb6-135">No painel de navegação esquerdo, vá para **reuniões** > **configurações de reunião**.</span><span class="sxs-lookup"><span data-stu-id="6adb6-135">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="6adb6-136">Em **rede**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6adb6-136">Under **Network**, do the following:</span></span>

    <span data-ttu-id="6adb6-137">![reunião-configurações-network.png] (media/meeting-settings-network.png "Captura de tela das configurações de rede para reuniões de equipes no Centro de administração de equipes da Microsoft")</span><span class="sxs-lookup"><span data-stu-id="6adb6-137">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="6adb6-138">Para habilitar o QoS marcadores, ative **os marcadores de inserir Quality of Service (QoS) para tráfego de mídia em tempo real**.</span><span class="sxs-lookup"><span data-stu-id="6adb6-138">To enable QoS markers, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span>
    - <span data-ttu-id="6adb6-139">Para especificar os intervalos de porta, ao lado de **Selecionar um intervalo de porta para cada tipo de tráfego de mídia em tempo real**, selecione **especificar intervalos de porta**e, em seguida, insira as portas inicial e finais para áudio, vídeo e compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="6adb6-139">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> 
    
        <span data-ttu-id="6adb6-140">Se você selecionar **usar automaticamente qualquer porta disponível**, portas disponíveis entre 1024 e 65535 são usados.</span><span class="sxs-lookup"><span data-stu-id="6adb6-140">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="6adb6-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6adb6-141">Related topics</span></span>
- [<span data-ttu-id="6adb6-142">Qualidade de serviço (QoS) em equipes</span><span class="sxs-lookup"><span data-stu-id="6adb6-142">Quality of Service (QoS) in Teams</span></span>](qos-in-teams.md)

