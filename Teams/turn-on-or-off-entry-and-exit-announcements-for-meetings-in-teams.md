---
title: Ativar ou desativar anúncios de entrada e de saída para reuniões no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar ou desativar anúncios de entrada e de saída em uma reunião no Microsoft Teams. '
ms.openlocfilehash: 1bddd07cc251f031daf85c077601c0e670038300
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347518"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="7b1b3-103">Ativar ou desativar anúncios de entrada e de saída para reuniões no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b1b3-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="7b1b3-104">Quando você estiver configurando a Audioconferência no Office 365, você receberá uma ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="7b1b3-105">Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para ligar para uma reunião do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="7b1b3-106">A ponte de conferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="7b1b3-107">A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático de conferência e, dependendo das suas configurações, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="7b1b3-108">É fornecido um PIN para o organizador da reunião do Microsoft Teams que permite que ele inicie uma reunião se ele não conseguir iniciar usando o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="7b1b3-109">No entanto, você pode fazer a configuração de modo que o PIN não seja obrigatório para iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="7b1b3-110">Definir as opções de participação da reunião</span><span class="sxs-lookup"><span data-stu-id="7b1b3-110">Setting meeting join options</span></span>

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="7b1b3-112">Usando equipes da Microsoft e Skype para Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="7b1b3-112">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="7b1b3-113">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7b1b3-114">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="7b1b3-115">No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-115">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="7b1b3-116">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-116">This is selected by default.</span></span> <span data-ttu-id="7b1b3-117">Entretanto, se você a desmarcar, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-117">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="7b1b3-118">Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-118">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="7b1b3-119">Caso escolha **Nomes ou números de telefone**, ative ou desative **Solicitar que os chamadores gravem seu nome antes de entrar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-119">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="7b1b3-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-120">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7b1b3-121">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7b1b3-121">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7b1b3-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7b1b3-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7b1b3-125">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="7b1b3-125">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7b1b3-126">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b1b3-126">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7b1b3-127">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7b1b3-127">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7b1b3-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7b1b3-128">Related topics</span></span>

[<span data-ttu-id="7b1b3-129">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="7b1b3-129">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
