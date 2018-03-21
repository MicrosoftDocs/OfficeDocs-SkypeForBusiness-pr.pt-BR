---
title: "Atribuir um terceiro como um provedor de serviços de audioconferência"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: b765e064558e9ef3a2bfaa4af2a3b6200c03f5bd
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="d3fe1-103">Atribuir um terceiro como um provedor de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="d3fe1-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="d3fe1-104">Um provedor de serviços de audioconferência fornece a *ponte de conferência*.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="d3fe1-105">A ponte de conferência fornece o número de telefone de discagem, os PINs e as IDs de conferência para as reuniões criadas.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="d3fe1-106">Você precisará atribuir um provedor de serviços de audioconferência para pessoas que estão indo para agendar ou liderança Skype para reuniões de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3fe1-107">For Microsoft Teams, um usuário não é possível usar um provedor de serviços de audioconferência de terceiros, eles deverão usar os serviços de audioconferência no Office 365, que define o provedor de serviços de audioconferência à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="d3fe1-108">Etapas para se fazer antes de designar um provedor de serviços de audioconferência de terceiros</span><span class="sxs-lookup"><span data-stu-id="d3fe1-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="d3fe1-109">Dependendo do seu plano do Office 365, você talvez precise adquirir licenças de complemento de **Conferência de áudio** para as pessoas na sua organização que estão indo para agendar ou liderança Skype para reuniões de negócios ou Microsoft Teams usando a conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="d3fe1-110">Para saber mais, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="d3fe1-111">Se você adquiriu licenças de complemento de **Conferência de áudio** , atribua as pessoas na sua organização que estão indo para agendar ou liderança reuniões que utilizam o áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="d3fe1-112">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3fe1-113">Se você atribuir uma licença de **Serviços de audioconferência** para alguém **depois** que você atribua um provedor de serviços de audioconferência de terceiros, essa pessoa será automaticamente definida para usar o Microsoft como seu provedor de serviços de audioconferência em vez disso!</span><span class="sxs-lookup"><span data-stu-id="d3fe1-113">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead!</span></span> <span data-ttu-id="d3fe1-114">Se isso ocorrer, você precisará remover primeiro a Microsoft como um provedor de serviços de audioconferência antes de designar um provedor de serviços de audioconferência de terceiros para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-114">If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="d3fe1-115">Encontre um provedor de serviços de audioconferência de terceiros no [Microsoft identifique](https://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-115">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span> <span data-ttu-id="d3fe1-116">Entre em contato com ele para saber como fazer a configuração.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-116">Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="d3fe1-117">Ele lhe fornecerá:</span><span class="sxs-lookup"><span data-stu-id="d3fe1-117">They will give you:</span></span>
    
  - <span data-ttu-id="d3fe1-118">**Números de discagem (Chamada Tarifada)** e números para ligações gratuitas se eles estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="d3fe1-p106">**IDs de conferência** que são usadas para cada pessoa que agenda reuniões. Alguns ACPs as chamam de senhas de conferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3fe1-121">Se você fez a inicial configurar um ACP de terceiros, mas agora você precisa fazer alterações, na parte inferior da página **Microsoft Bridge** **clique aqui para configurar um provedor de serviços de audioconferência de terceiros**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d3fe1-122">Quando você habilitar uma pessoa para conferência de áudio e atribuí-las um provedor de serviços de audioconferência de terceiros, os números de áudio e as IDs de conferência (códigos de acesso) são adicionados automaticamente a qualquer **novo** Skype para reuniões Online de negócios que eles criam.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="d3fe1-123">Como atribuir um provedor de serviços de audioconferência de terceiros a um usuário</span><span class="sxs-lookup"><span data-stu-id="d3fe1-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="d3fe1-p107">No **Centro de administração do Skype for Business**, escolha **Usuários**. Selecione o usuário na lista e clique em **Editar** no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="d3fe1-126">Na página de propriedades do usuário, clique em **conferência de áudio** e insira essas informações:</span><span class="sxs-lookup"><span data-stu-id="d3fe1-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="d3fe1-127">**Nome do provedor** Selecione o provedor de terceiros da lista.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="d3fe1-128">**Número de Chamada Tarifada padrão** Isso é necessário.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="d3fe1-129">**Número de chamada gratuito padrão** Isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="d3fe1-130">**ID de conferência** Isso é fornecido pelo seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="d3fe1-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="d3fe1-132">Envie a cada pessoa o PIN que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-132">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="d3fe1-133">Talvez seja necessário o PIN a ser chamado na como o organizador da chamada em conferência ou líder.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-133">The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3fe1-134">Quando você usa um provedor de serviços de audioconferência de terceiros, não há uma maneira de ver ou definir PINs em nome organizadores de reuniões.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="d3fe1-135">Como atribuir um provedor de serviços de audioconferência de terceiros para muitas pessoas ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="d3fe1-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="d3fe1-136">No **Skype para centro de administração de negócios**, escolha **audioconferências** > **ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="d3fe1-137">Na parte inferior da página, clique no link na **se você gostaria de configurar um provedor de serviços de audioconferência de terceiros em vez disso, clique aqui**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3fe1-138">Se você fez a inicial configurar um ACP de terceiros, mas agora você precisa fazer alterações, na parte inferior da página de **Ponte da Microsoft** , **clique aqui para configurar um provedor de serviços de audioconferência de terceiros**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="d3fe1-139">Na página **Configurar um provedor de serviços de audioconferência de terceiros** , em **usuários de importação e exportação**, clique em **Assistente para exportar**e siga as etapas no **Assistente para exportação de usuários**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-139">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**.</span></span> <span data-ttu-id="d3fe1-140">Quando terminar, você terá um arquivo que lista as pessoas que você deseja configurar para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-140">When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="d3fe1-141">Envie o arquivo que você criou para seu provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-141">Send the file you created to your third-party audio conferencing provider.</span></span> <span data-ttu-id="d3fe1-142">Eles serão adicionar informações de conferência de áudio para as pessoas listadas no arquivo e, em seguida, retornar o arquivo para você.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-142">They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="d3fe1-p112">Verifique se o arquivo retornado contém as informações certas. Ouvimos falar de casos em que nem todas as pessoas listadas no arquivo obtiveram as informações certas.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="d3fe1-145">Na página **Configurar um provedor de serviços de audioconferência terceiro**, em **Importar e exportar usuários**, clique em **Assistente de importação** e siga as etapas do **Assistente para importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="d3fe1-146">Envie a cada pessoa o PIN que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-146">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="d3fe1-147">O PIN pode ser necessário para a chamada como organizador ou líder de chamada em conferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-147">The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3fe1-148">Quando você usa um provedor de serviços de audioconferência de terceiros, não há uma maneira de ver ou definir PINs em nome organizadores de reuniões.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="d3fe1-149">Quando usar um provedor de serviços de audioconferência de terceiros</span><span class="sxs-lookup"><span data-stu-id="d3fe1-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="d3fe1-150">Se você estiver em um país ou região onde os serviços de audioconferência no Office 365 não está disponível, a qualidade de serviço não é ótima devido a seu local ou você tiver um contrato existente com um provedor de serviços de audioconferência de terceiros, recomendamos o uso de um áudio de terceiros provedor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-150">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="d3fe1-151">Caso contrário, é recomendável usar o Microsoft como seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-151">Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="d3fe1-152">Automatizar a atribuição do provedor de audioconferência de terceiros usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3fe1-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="d3fe1-153">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3fe1-154">Para alterar o provedor de áudio da Microsoft para um provedor de serviços de audioconferência de terceiros, você deve remover o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-154">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="d3fe1-155">Para isso, use o cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-155">To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="d3fe1-156">Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="d3fe1-157">O que mais eu preciso saber?</span><span class="sxs-lookup"><span data-stu-id="d3fe1-157">What else do I need to know?</span></span>

<span data-ttu-id="d3fe1-158">Uma pessoa em sua organização só pode usar um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d3fe1-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="d3fe1-159">Para alterar o provedor de serviços de audioconferência de uma pessoa para a Microsoft, consulte [Mover o provedor de serviços de audioconferência do usuário à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou [Atribuir Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe1-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d3fe1-160">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="d3fe1-160">Related Topics</span></span>

[<span data-ttu-id="d3fe1-161">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3fe1-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="d3fe1-162">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d3fe1-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

