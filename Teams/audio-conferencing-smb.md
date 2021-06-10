---
title: Configurar Audioconferência para pequenas e médias empresas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Saiba como definir a Audioconferência em sua pequena ou média empresa para pessoas que precisam usar um telefone para ligar para reuniões. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122345"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="e5652-103">Configurar Audioconferência para pequenas e médias empresas</span><span class="sxs-lookup"><span data-stu-id="e5652-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="e5652-104">Com a Audioconferência, as pessoas podem ligar para Teams reuniões usando um telefone em vez de usar o aplicativo Teams no dispositivo móvel ou no computador.</span><span class="sxs-lookup"><span data-stu-id="e5652-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="e5652-105">Se você for uma pequena ou média empresa com até 300 usuários e atualmente não tiver licenças de Audioconferência, poderá obter Audioconferência gratuita por um ano.</span><span class="sxs-lookup"><span data-stu-id="e5652-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="e5652-106">Essa oferta gratuita está disponível a partir de 1º de outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="e5652-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="e5652-107">A licença de complemento de Audioconferência pode ser aplicada a usuários que tenham licenças Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 ou Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="e5652-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="e5652-108">Para saber mais, [confira Teams licenças de complemento](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e5652-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="e5652-109">Se você tiver Enterprise E5 ou Microsoft 365 Business Voice, não poderá usar a oferta gratuita de Audioconferência porque essas licenças já incluem Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e5652-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="e5652-110">Neste artigo, vamos mostrar como configurar a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e5652-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="e5652-111">Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5652-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="e5652-112">Os participantes da reunião que ligarem para reuniões não precisam de licenças ou outras configurações.</span><span class="sxs-lookup"><span data-stu-id="e5652-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="e5652-113">Para saber mais, confira [Audioconferência](audio-conferencing-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e5652-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="e5652-114">Configurar a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="e5652-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="e5652-115">Quando você configura a Audioconferência, um número de telefone é atribuído automaticamente à ponte de conferência para que ele possa ser usado em convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="e5652-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="e5652-116">O número de telefone atribuído como o número padrão da ponte de conferência será um do país ou região da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e5652-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="e5652-117">Esse número de telefone é um número de chamada, no qual os encargos de longa distância podem ser aplicados.</span><span class="sxs-lookup"><span data-stu-id="e5652-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="e5652-118">Você também pode usar um número gratuito, que exige algumas etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="e5652-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="e5652-119">Para saber mais sobre números de telefone para sua ponte de conferência, consulte Números de telefone de [audioconferência](#audio-conferencing-phone-numbers) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e5652-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="e5652-120">Etapa 1: Obter licenças de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="e5652-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="e5652-121">Obter uma licença de Audioconferência para cada pessoa que conduzirá as reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5652-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="e5652-122">Use o Microsoft 365 de administração para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e5652-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="e5652-123">No centro Microsoft 365 de administração, vá para Cobrança Serviços de Compra e, na parte inferior da  >  página, selecione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e5652-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="e5652-124">Selecione **Microsoft 365 detalhes promocionais** de adoção de  >  **audioconferência** e selecione **Obter agora**.</span><span class="sxs-lookup"><span data-stu-id="e5652-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="e5652-125">Insira o número de licenças que você precisa para seus organizadores de reunião e conclua seu pedido.</span><span class="sxs-lookup"><span data-stu-id="e5652-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Captura de tela da licença promocional de adoção de audioconferência":::

    > [!NOTE]
    > <span data-ttu-id="e5652-127">Desembaixe ou selecione a atribuição automática a todos os usuários sem **licenças,** dependendo se você deseja atribuir automaticamente uma licença de Audioconferência a todos os usuários que não têm essa licença.</span><span class="sxs-lookup"><span data-stu-id="e5652-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="e5652-128">Etapa 2: Atribuir uma licença de Audioconferência aos usuários que conduzem reuniões</span><span class="sxs-lookup"><span data-stu-id="e5652-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="e5652-129">Atribua uma licença a cada pessoa que conduzirá as reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5652-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="e5652-130">Use o Microsoft 365 de administração para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e5652-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="e5652-131">Atribuir uma licença a um usuário</span><span class="sxs-lookup"><span data-stu-id="e5652-131">Assign a license to one user</span></span>

1. <span data-ttu-id="e5652-132">No centro Microsoft 365 de administração, vá para **Usuários**  >  **Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="e5652-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="e5652-133">Selecione a linha do usuário a que você deseja atribuir a licença e, no painel, selecione **Licenças e Aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="e5652-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="e5652-134">Marque a **caixa de seleção Microsoft 365 Audioconferência** e selecione Salvar **alterações**.</span><span class="sxs-lookup"><span data-stu-id="e5652-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="e5652-135">Atribuir uma licença a vários usuários</span><span class="sxs-lookup"><span data-stu-id="e5652-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="e5652-136">No centro Microsoft 365 de administração, vá para **Usuários**  >  **Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="e5652-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="e5652-137">Selecione os círculos ao lado dos usuários aos que você deseja atribuir a licença e selecione **Gerenciar licenças de produto.**</span><span class="sxs-lookup"><span data-stu-id="e5652-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="e5652-138">No painel **Gerenciar licenças de** produto, selecione **Atribuir mais**.</span><span class="sxs-lookup"><span data-stu-id="e5652-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="e5652-139">Marque a **caixa de seleção Microsoft 365 Audioconferência** e selecione Salvar **alterações**.</span><span class="sxs-lookup"><span data-stu-id="e5652-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="e5652-140">Agendar Teams reuniões no Outlook</span><span class="sxs-lookup"><span data-stu-id="e5652-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="e5652-141">Os organizadores da reunião agora podem agendar reuniões Outlook.</span><span class="sxs-lookup"><span data-stu-id="e5652-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="e5652-142">Em Outlook, vá para **Calendário** e selecione o botão Novo Teams **reunião.**</span><span class="sxs-lookup"><span data-stu-id="e5652-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="e5652-143">Os números de discagem da reunião e a ID da conferência são adicionados automaticamente ao convite de reunião enviado aos participantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="e5652-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="e5652-144">Para saber mais, confira [Agendar uma reunião Teams em Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span><span class="sxs-lookup"><span data-stu-id="e5652-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="e5652-145">Se quiser, você pode personalizar convites de reunião para adicionar o logotipo da sua empresa, links para seu site de suporte e aviso de isenção de responsabilidade legal e um rodapé somente texto.</span><span class="sxs-lookup"><span data-stu-id="e5652-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="e5652-146">Para saber mais, confira [Personalizar convites de reunião.](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="e5652-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="e5652-147">Números de telefone de audioconferência</span><span class="sxs-lookup"><span data-stu-id="e5652-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="e5652-148">Há dois tipos de números que você pode usar para sua ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="e5652-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="e5652-149">Você pode usar números **compartilhados** (como na seção [Configurar Audioconferência](#set-up-audio-conferencing) anteriormente neste artigo) ou **números dedicados.**</span><span class="sxs-lookup"><span data-stu-id="e5652-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="e5652-150">Aqui estão mais informações sobre cada um.</span><span class="sxs-lookup"><span data-stu-id="e5652-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="e5652-151">Números compartilhados</span><span class="sxs-lookup"><span data-stu-id="e5652-151">Shared numbers</span></span>

<span data-ttu-id="e5652-152">Um número compartilhado é um número compartilhado em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="e5652-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="e5652-153">Números compartilhados são números de pedágio e são atribuídos automaticamente ao configurar a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e5652-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="e5652-154">Para ver o número padrão atribuído à sua ponte de conferência, na navegação à esquerda do centro de administração do Microsoft Teams, vá até Pontes de Conferência de Reuniões e encontre o número do local mais próximo  >  a você.</span><span class="sxs-lookup"><span data-stu-id="e5652-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="e5652-155">Números dedicados</span><span class="sxs-lookup"><span data-stu-id="e5652-155">Dedicated numbers</span></span>

<span data-ttu-id="e5652-156">Um número dedicado é um número que está disponível apenas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="e5652-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="e5652-157">Um número dedicado pode ser um número de telefone ou um número gratuito.</span><span class="sxs-lookup"><span data-stu-id="e5652-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="e5652-158">Para usar um número dedicado, você terá que primeiro obter o número, atribuí-lo à ponte de conferência e, em seguida, atribuir o número a cada pessoa que conduzirá as reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5652-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="e5652-159">Há algumas maneiras de obter um número dedicado.</span><span class="sxs-lookup"><span data-stu-id="e5652-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="e5652-160">Você pode obter um número da Microsoft ou transferir (porta) um número existente do provedor de serviços atual para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5652-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="e5652-161">Para saber mais sobre como fazer isso, consulte [Obter números de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="e5652-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="e5652-162">Lembre-se de que, se você usar um número gratuito, terá que primeiro atribuir uma licença de Créditos de Comunicação a cada pessoa que conduzirá as reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5652-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="e5652-163">Para saber mais, consulte [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e5652-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="e5652-164">Depois de ter seu número, atribua-o à ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="e5652-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="e5652-165">Use o Microsoft Teams de administração para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e5652-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="e5652-166">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Pontes de**  >  **Conferência de Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="e5652-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e5652-167">Selecione **Adicionar** e, em seguida, selecione **Número de telefone** ou número **gratuito**.</span><span class="sxs-lookup"><span data-stu-id="e5652-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="e5652-168">No painel **Adicionar número de** telefone, selecione o número e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e5652-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="e5652-169">Em seguida, atribua o número a cada pessoa que conduzirá as reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5652-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="e5652-170">Use o Microsoft Teams de administração para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e5652-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="e5652-171">Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Usuários**, clique no nome de exibição do usuário e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e5652-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="e5652-172">Selecione **Editar** ao lado de **Audioconferência** e, em seguida,  no painel  **Audioconferência,** selecione um número nas listas número de telefone ou número de telefone gratuito e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e5652-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5652-173">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e5652-173">Related topics</span></span>

- [<span data-ttu-id="e5652-174">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="e5652-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="e5652-175">Configurar Audioconferência para Teams</span><span class="sxs-lookup"><span data-stu-id="e5652-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="e5652-176">Números de telefone para audioconferência</span><span class="sxs-lookup"><span data-stu-id="e5652-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="e5652-177">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="e5652-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="e5652-178">Obter números de serviço</span><span class="sxs-lookup"><span data-stu-id="e5652-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="e5652-179">Teams licenças de complemento</span><span class="sxs-lookup"><span data-stu-id="e5652-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="e5652-180">Atribuir licenças aos usuários</span><span class="sxs-lookup"><span data-stu-id="e5652-180">Assign licenses to users</span></span>](/microsoft-365/admin/manage/assign-licenses-to-users)