---
title: Definir os números de telefone incluídos nos convites no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 84bf0240270bfc9633f9d845130a6049d36c8cad
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237727"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="04be3-103">Definir os números de telefone incluídos nos convites no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="04be3-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="04be3-104">Para obter informações sobre os números de telefone incluídos nos convites no Microsoft Teams, consulte [Definir os números de telefone incluídos nos convites no Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="04be3-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="04be3-105">A audioconferência em Microsoft 365 ou Office 365 permite que os usuários em sua organização criem reuniões Skype for Business e, em seguida, permitam que os usuários discem para essas reuniões usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="04be3-105">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="04be3-106">Em Microsoft 365 e Office 365, você tem a opção de usar uma ponte de audioconferência da Microsoft ou uma ponte de audioconferência de terceiros hospedada por um provedor de audioconferência aprovado (ACP).</span><span class="sxs-lookup"><span data-stu-id="04be3-106">In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="04be3-107">Não há um recurso que contenha uma lista de todos os números de discagem para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="04be3-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="04be3-108">Se você estiver procurando ver se há números de telefone discados disponíveis em sua área ou país/região, use o centro de administração do **Skype for Business** Voz Telefone  >    >  **Números**, clique em **Adicionar** novos números de **serviço**.</span><span class="sxs-lookup"><span data-stu-id="04be3-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="04be3-109">Use as listas de **País/região**, **Estado/região** e **Cidade** para filtrar sua busca. Além disso, se você estiver procurando por números de serviço gratuitos, selecione **Números gratuitos** da lista **Estado/região**.</span><span class="sxs-lookup"><span data-stu-id="04be3-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="04be3-110">Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização.</span><span class="sxs-lookup"><span data-stu-id="04be3-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="04be3-111">Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.</span><span class="sxs-lookup"><span data-stu-id="04be3-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04be3-112">Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="04be3-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="04be3-113">Definir o número de telefone padrão para o organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="04be3-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="04be3-114">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="04be3-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="04be3-115">Escolha **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="04be3-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="04be3-116">Escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="04be3-116">Choose **Users**.</span></span>
    
    ![Mostra os usuários que podem ser selecionados no centro de administração do Skype for Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="04be3-118">Escolha os usuários que você deseja editar:</span><span class="sxs-lookup"><span data-stu-id="04be3-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="04be3-119">Para selecionar um único usuário, selecione o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="04be3-120">Para selecionar todos os usuários na página, marque a caixa ao lado do **Nome de exibição** na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="04be3-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="04be3-121">Para selecionar vários usuários, marque a caixa ao lado do nome de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="04be3-122">No painel direito, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="04be3-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="04be3-124">Escolha **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="04be3-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="04be3-125">Na página **Propriedades** , na lista **Nome do provedor** , escolha o provedor para o usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="04be3-126">Dependendo do provedor, preencha as seguintes caixas.</span><span class="sxs-lookup"><span data-stu-id="04be3-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="04be3-127">**A Microsoft é o provedor**: Use as listas **Número de chamada tarifada padrão** e **Número de chamada gratuita padrão** para selecionar os números padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="04be3-128">Pelo menos um número de chamada gratuita deve ser atribuído à sua ponte de conferência antes que ela possa ser definida como o número de chamada gratuita padrão de um usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="04be3-129">Para obter um número de chamada gratuita, consulte Obter números de telefone [de serviço para](/microsoftteams/getting-service-phone-numbers)Skype for Business .</span><span class="sxs-lookup"><span data-stu-id="04be3-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="04be3-130">**Um terceiro é o provedor**: Use os campos de **Número de chamada tarifada** e **Número de chamada gratuita** para inserir os números para o usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="04be3-131">Redefinir os números de telefone de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="04be3-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="04be3-132">No centro **Skype for Business de administração,** escolha **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="04be3-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="04be3-133">Na parte superior da página, escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="04be3-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="04be3-134">Escolha os usuários que você deseja redefinir e, em seguida, no painel de Ações, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="04be3-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="04be3-135">Por padrão, quando você altera as configurações de conferência de um usuário, um email é enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="04be3-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="04be3-136">Para alterar isso, consulte [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="04be3-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="04be3-137">Quando você altera as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Skype for Business devem ser atualizadas e enviadas aos participantes.</span><span class="sxs-lookup"><span data-stu-id="04be3-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="04be3-138">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="04be3-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="04be3-139">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="04be3-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="04be3-140">Use o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="04be3-140">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="04be3-141">Para mudar o número de chamada gratuita padrão de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="04be3-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="04be3-142">Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.</span><span class="sxs-lookup"><span data-stu-id="04be3-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04be3-143">Para encontrar o BridgeID, use o cmdlet **Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="04be3-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="04be3-144">Para definir o número de gratuita padrão para todos os usuários sem um como +18005551234, execute:</span><span class="sxs-lookup"><span data-stu-id="04be3-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="04be3-145">Para alterar o número padrão de gratuita de todos os usuários que têm +18005551234 como seu número de gratuita padrão para +18005551239, execute:</span><span class="sxs-lookup"><span data-stu-id="04be3-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="04be3-146">Para definir o número padrão de gratuitos de todos os usuários localizados nos EUA como +18005551234, execute:</span><span class="sxs-lookup"><span data-stu-id="04be3-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="04be3-147">Quer saber mais sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="04be3-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="04be3-p107">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="04be3-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="04be3-151">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="04be3-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="04be3-152">Por que você precisa usar Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="04be3-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="04be3-153">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="04be3-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="04be3-154">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="04be3-154">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="04be3-155">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="04be3-155">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="04be3-156">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="04be3-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="04be3-157">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="04be3-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="04be3-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="04be3-158">Related topics</span></span>

[<span data-ttu-id="04be3-159">Experimente ou compre Audioconferência em Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="04be3-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
