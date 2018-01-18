---
title: "Defina o telefone convidam números incluídos no"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 8cc9b90d37e1a30c995547035fb2815aad89b7cf
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="42471-103">Defina o telefone convidam números incluídos no</span><span class="sxs-lookup"><span data-stu-id="42471-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="42471-104">Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar Skype para reuniões de negócios e Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="42471-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="42471-105">No Office 365, você tem a opção de usar uma ponte de conferência de áudio da Microsoft ou uma ponte de conferência de áudio de terceiros que é hospedada por um provedor de serviços de audioconferência aprovada (ACP).</span><span class="sxs-lookup"><span data-stu-id="42471-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="42471-106">Não há um recurso que contém uma lista de todos os números de discagem para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="42471-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="42471-107">Se você estiver procurando para ver se existem números de telefone de discagem disponíveis na sua área ou país/região, use o **Skype para centro de administração de negócios** > **voz** > **Números de telefone**, clique em **Adicionar** e em seguida **novos números de serviço **.</span><span class="sxs-lookup"><span data-stu-id="42471-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="42471-108">Use as listas de **País/região**, estado/região do **** e **cidade** para filtrar search. > Além disso, se você estiver procurando por números de serviço gratuito tarifados, selecione **chamada gratuita** do estado/região **** lista.</span><span class="sxs-lookup"><span data-stu-id="42471-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="42471-109">Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização.</span><span class="sxs-lookup"><span data-stu-id="42471-109">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="42471-110">Todos eles podem ser usados para ingressar as reuniões que criou um organizador de reunião, mas você pode selecionar quais serão incluídos em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="42471-110">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42471-111">Pode haver um máximo de chamada um Tarifada e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também existe um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="42471-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="42471-112">Configurando o número de telefone de discagem padrão para o organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="42471-112">Setting the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="42471-113">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="42471-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="42471-114">Escolha **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="42471-114">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="42471-115">Escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="42471-115">Choose **Users**.</span></span>
    
    ![Mostra a seleção de usuários no Skype para centro de administração do Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="42471-117">Escolha os usuários que você deseja editar:</span><span class="sxs-lookup"><span data-stu-id="42471-117">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="42471-118">Para selecionar um único usuário, selecione o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-118">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="42471-119">Para selecionar todos os usuários na página, marque a caixa ao lado do **nome para exibição** na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="42471-119">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="42471-120">Para selecionar vários usuários, marque a caixa ao lado do nome de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-120">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="42471-121">No painel direito, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="42471-121">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="42471-123">Escolha a **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="42471-123">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="42471-124">Na página **Propriedades** , na lista **nome do provedor** , escolha o provedor para o usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-124">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="42471-125">Dependendo do provedor, preencha as seguintes caixas.</span><span class="sxs-lookup"><span data-stu-id="42471-125">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="42471-126">**A Microsoft tem o provedor**: Use o **número de Chamada Tarifada padrão** e **número de chamada gratuito padrão** lista para selecionar os números de padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-126">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="42471-127">Pelo menos um número de chamada gratuito deve ser atribuído à sua ponte de conferência antes que ela pode ser definida como o número de chamada gratuita do padrão de um usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-127">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="42471-128">Para obter um número de discagem gratuito, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="42471-128">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="42471-129">**Um terceiro é o provedor**: Use os campos de **número de Chamada Tarifada** e **número de chamada gratuito** para inserir os números para o usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-129">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>
    
## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="42471-130">Redefinir os números de telefone de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="42471-130">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="42471-131">No **Skype para centro de administração de negócios**, escolha a **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="42471-131">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="42471-132">Na parte superior da página, escolha **usuários**.</span><span class="sxs-lookup"><span data-stu-id="42471-132">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="42471-133">Escolha os usuários que você deseja redefinir e, em seguida, no painel de ações, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="42471-133">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="42471-134">Por padrão, quando você altera as configurações de conferência de um usuário, um email é enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="42471-134">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="42471-135">Para alterar essa opção, consulte [Habilitar ou desabilitar o envio de emails ao alteram as configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="42471-135">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="42471-136">Quando você altera as configurações de conferência de áudio de um usuário, Skype recorrente e futura para reuniões de negócios e Teams da Microsoft deve ser atualizado e enviado aos participantes.</span><span class="sxs-lookup"><span data-stu-id="42471-136">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="42471-137">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="42471-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="42471-138">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="42471-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="42471-139">Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="42471-139">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="42471-140">Para mudar o número de chamada gratuita padrão de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="42471-140">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="42471-141">Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.</span><span class="sxs-lookup"><span data-stu-id="42471-141">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="42471-142">Para localizar o BridgeID, use o **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="42471-142">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="42471-143">Para definir o número de chamada gratuita padrão para todos os usuários sem um para +18005551234, execute:</span><span class="sxs-lookup"><span data-stu-id="42471-143">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="42471-144">Para alterar o número de chamada gratuita do padrão de todos os usuários que possuem +18005551234 como seu número de chamada gratuita padrão para +18005551239, execute:</span><span class="sxs-lookup"><span data-stu-id="42471-144">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="42471-145">Para definir o número de chamada gratuita do padrão de todos os usuários localizados nos EUA para +18005551234, execute:</span><span class="sxs-lookup"><span data-stu-id="42471-145">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="42471-146">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="42471-146">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="42471-p107">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="42471-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="42471-150">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="42471-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="42471-151">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="42471-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="42471-p108">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="42471-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="42471-154">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42471-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="42471-155">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="42471-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="42471-156">Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="42471-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="42471-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="42471-157">Related topics</span></span>

[<span data-ttu-id="42471-158">Configurar a Audioconferência para o Skype for Business e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42471-158">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

