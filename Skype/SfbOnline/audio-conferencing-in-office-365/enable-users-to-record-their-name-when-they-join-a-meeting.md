---
title: Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Saiba como ativar ou desativar a opção de seus usuários gravarem seus nomes ao ingressar em uma reunião no Skype for Business Online.
ms.openlocfilehash: 6022d7ebf0e653bc43373cb00faabc207f91562a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850037"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="80572-103">Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80572-103">Enable users to record their name when they join a meeting</span></span>

> [!Note]
> <span data-ttu-id="80572-104">Se você quiser permitir que os usuários registrem seus nomes no Teams, consulte [Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="80572-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="80572-105">Quando você estiver configurando a Audioconferência no Office 365, você receberá números de telefone e o que é chamado de ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="80572-105">When you are setting up dial-in conferencing in Skype for Business Online, you will receive phone numbers and what is called a dial-in or audio conferencing bridge.</span></span> <span data-ttu-id="80572-106">Uma ponte de conferência pode conter um ou mais números de telefone, que podem ser um número de telefone dedicado ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="80572-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="80572-107">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião usando o telefone.</span><span class="sxs-lookup"><span data-stu-id="80572-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="80572-108">A ponte de conferência atende o autor da chamada com comandos de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações, pedir para o autor da chamada gravar o nome dele e configurar a segurança do PIN para os organizadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="80572-108">The conferencing bridge answers the caller with voice prompts from an auto attendant and then, depending on their settings, can play notifications, ask callers to record their name, and sets up the PIN security for meeting organizers.</span></span> <span data-ttu-id="80572-109">Os PINs são fornecidos aos organizadores de reuniões para permitir que eles iniciem uma reunião.</span><span class="sxs-lookup"><span data-stu-id="80572-109">PINs are given to a meeting organizer that allows them to start a meeting.</span></span> <span data-ttu-id="80572-110">Entretanto, você pode configurá-lo para que não seja necessário um PIN para iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="80572-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="80572-111">Definir se os autores da chamada devem registrar seu nome</span><span class="sxs-lookup"><span data-stu-id="80572-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="80572-112">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá até **Audioconferência** > **Configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="80572-112">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="80572-113">Em **Experiência de participação da reunião**, veja a caixa de seleção **Habilitar a ativação de notificações de entrada e saída na reunião**.</span><span class="sxs-lookup"><span data-stu-id="80572-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="80572-114">Os autores de chamadas **marcados**serão solicitados a gravarem o nome antes de entrarem na reunião.</span><span class="sxs-lookup"><span data-stu-id="80572-114">**Checked** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="80572-115">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="80572-115">This is selected by default.</span></span>
    
  - <span data-ttu-id="80572-116">Os autores de chamadas **desmarcados**não serão solicitados a gravarem o nome antes de entrarem na reunião.</span><span class="sxs-lookup"><span data-stu-id="80572-116">**Unchecked** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="80572-117">Depois de fazer as alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80572-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="80572-118">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="80572-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="80572-119">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="80572-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="80572-120">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="80572-120">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="80572-121">Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas.</span><span class="sxs-lookup"><span data-stu-id="80572-121">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="80572-122">Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="80572-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="80572-123">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="80572-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="80572-124">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80572-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="80572-125">O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação com o uso exclusivo do Centro de administração do Office 365, como, por exemplo, ao fazer alterações em configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="80572-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="80572-126">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="80572-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="80572-127">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80572-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="80572-128">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80572-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="80572-129">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80572-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="80572-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="80572-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="80572-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="80572-132">Related topics</span></span>

[<span data-ttu-id="80572-133">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="80572-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
