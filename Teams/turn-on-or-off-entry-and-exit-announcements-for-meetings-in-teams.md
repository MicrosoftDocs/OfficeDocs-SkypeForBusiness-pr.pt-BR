---
title: Ativar ou desativar a entrada e sair de comunicados para reuniões em Teams da Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar a entrada e sair comunicados ativada ou desativada em uma reunião do Microsoft Teams. '
ms.openlocfilehash: 94a091590ff00d2c78278e8ad559b61b1e732130
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884625"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="f67ef-103">Ativar ou desativar a entrada e sair de comunicados para reuniões em Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f67ef-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="f67ef-104">Quando você estiver configurando a Audioconferência no Office 365, obterá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="f67ef-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="f67ef-105">Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para uma reunião Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f67ef-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="f67ef-106">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="f67ef-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="f67ef-107">A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático de conferência e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN.</span><span class="sxs-lookup"><span data-stu-id="f67ef-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="f67ef-108">Um PIN é fornecido ao organizador da reunião Teams da Microsoft e permite que eles iniciem uma reunião se eles não é possível iniciar a reunião usando o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f67ef-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="f67ef-109">Você pode, no entanto, defini-lo para que não é necessário um PIN para iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="f67ef-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="f67ef-110">Definir as opções de participação da reunião</span><span class="sxs-lookup"><span data-stu-id="f67ef-110">Setting meeting join options</span></span>

1. <span data-ttu-id="f67ef-111">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="f67ef-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f67ef-112">Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="f67ef-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="f67ef-113">No painel de **configurações de ponte** , habilitar ou desabilitar a **entrada de reunião e sair de notificações**.</span><span class="sxs-lookup"><span data-stu-id="f67ef-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="f67ef-114">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="f67ef-114">This is selected by default.</span></span> <span data-ttu-id="f67ef-115">Se você desmarcar a ele, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="f67ef-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="f67ef-116">Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.</span><span class="sxs-lookup"><span data-stu-id="f67ef-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="f67ef-117">Se você escolher **nomes ou números de telefone**, habilitar ou desabilitar **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="f67ef-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="f67ef-118">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f67ef-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f67ef-119">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f67ef-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f67ef-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f67ef-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f67ef-123">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="f67ef-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f67ef-124">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f67ef-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f67ef-125">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f67ef-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f67ef-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f67ef-126">Related topics</span></span>

[<span data-ttu-id="f67ef-127">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="f67ef-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
