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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: O administrador pode saber mais sobre como ativar ou desativar anúncios de entrada e de saída em uma reunião do Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372200"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="72368-103">Ativar ou desativar anúncios de entrada e de saída para reuniões no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72368-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="72368-104">Ao configurar a videoconferência no Microsoft 365 ou no Office 365, você receberá uma ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="72368-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="72368-105">Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para ligar para uma reunião do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="72368-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="72368-106">A ponte de conferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="72368-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="72368-107">A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático de conferência e, dependendo das suas configurações, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN.</span><span class="sxs-lookup"><span data-stu-id="72368-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="72368-108">É fornecido um PIN para o organizador da reunião do Microsoft Teams que permite que ele inicie uma reunião se ele não conseguir iniciar usando o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="72368-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="72368-109">No entanto, você pode fazer a configuração de modo que o PIN não seja obrigatório para iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="72368-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="72368-110">Definir as opções de participação da reunião</span><span class="sxs-lookup"><span data-stu-id="72368-110">Setting meeting join options</span></span>

<span data-ttu-id="72368-111">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="72368-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="72368-112">Você deve ser um administrador de serviços do teams para fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="72368-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="72368-113">Consulte [usar funções de administrador do teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.</span><span class="sxs-lookup"><span data-stu-id="72368-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="72368-114">Conecte-se ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="72368-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="72368-115">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="72368-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="72368-116">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="72368-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="72368-117">No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="72368-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="72368-118">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="72368-118">This is selected by default.</span></span> <span data-ttu-id="72368-119">Entretanto, se você a desmarcar, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="72368-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="72368-120">Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.</span><span class="sxs-lookup"><span data-stu-id="72368-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="72368-121">Por padrão, os participantes externos não conseguem ver os números de telefone dos participantes discadas.</span><span class="sxs-lookup"><span data-stu-id="72368-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="72368-122">Se você quiser manter a privacidade desses números de telefone, selecione **Tons** para o **tipo de anúncio de entrada/saída** (isso impede que os números sejam lidos pelas equipes).</span><span class="sxs-lookup"><span data-stu-id="72368-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="72368-123">Caso escolha **Nomes ou números de telefone**, ative ou desative **Solicitar que os chamadores gravem seu nome antes de entrar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="72368-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="72368-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="72368-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="72368-125">Quer saber mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72368-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="72368-126">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="72368-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="72368-127">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="72368-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="72368-128">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="72368-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="72368-129">Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="72368-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="72368-130">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72368-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="72368-131">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="72368-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="72368-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="72368-132">Related topics</span></span>

[<span data-ttu-id="72368-133">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="72368-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
