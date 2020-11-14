---
title: Configurar a videoconferência para empresas de pequeno e médio porte
ms.author: v-lanac
author: lanachin
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
description: 'Saiba como configurar a conferência de áudio na sua pequena ou média empresa para as pessoas que precisam usar um telefone para fazer chamadas para reuniões. '
ms.openlocfilehash: 4c0d47246f8a321a91ea175e06279bfe147a634a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031177"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="5b214-103">Configurar a videoconferência para empresas de pequeno e médio porte</span><span class="sxs-lookup"><span data-stu-id="5b214-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="5b214-104">Com o áudio videoconferência, as pessoas podem fazer chamadas para reuniões do teams usando um telefone, em vez de usar o aplicativo Teams em seu dispositivo móvel ou do computador.</span><span class="sxs-lookup"><span data-stu-id="5b214-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="5b214-105">Se você for uma pequena ou média empresa com até 300 usuários e não tiver nenhuma licença de audioconferência, você pode adquirir o áudio para conferências grátis por um ano.</span><span class="sxs-lookup"><span data-stu-id="5b214-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="5b214-106">Esta oferta gratuita está disponível a partir de 1 ° de outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="5b214-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="5b214-107">A licença do complemento do Audio Conferencing pode ser aplicada a usuários que tenham licenças do Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 ou Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="5b214-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="5b214-108">Para saber mais, consulte [licenças de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="5b214-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="5b214-109">Se você tiver o Enterprise E5 ou o Microsoft 365 Business Voice, você não poderá usar a oferta de audioconferência de áudio gratuita, pois essas licenças já incluem videoconferência.</span><span class="sxs-lookup"><span data-stu-id="5b214-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="5b214-110">Neste artigo, vamos orientá-lo sobre como configurar a conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="5b214-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="5b214-111">Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b214-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="5b214-112">Os participantes da reunião que fizerem chamadas para reuniões não precisam de licenças ou outras configurações.</span><span class="sxs-lookup"><span data-stu-id="5b214-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="5b214-113">Para saber mais, confira [áudio videoconferência](audio-conferencing-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="5b214-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="5b214-114">Configurar a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="5b214-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="5b214-115">Quando você configura a conferência de áudio, um número de telefone é automaticamente atribuído à sua ponte de conferência para que possa ser usado em convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="5b214-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="5b214-116">O número de telefone atribuído como o número padrão de sua ponte de conferência será um do país ou região da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5b214-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="5b214-117">Este número de telefone é um número de chamada tarifada, no qual tarifas de longa distância podem ser aplicadas.</span><span class="sxs-lookup"><span data-stu-id="5b214-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="5b214-118">Você também pode usar um número de chamada gratuita, que requer algumas etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="5b214-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="5b214-119">Para saber mais sobre números de telefone para a sua ponte de conferência, consulte [números de telefone de conferência de áudio](#audio-conferencing-phone-numbers) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5b214-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="5b214-120">Etapa 1: obter licenças de audioconferência</span><span class="sxs-lookup"><span data-stu-id="5b214-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="5b214-121">Obtenha uma licença de conferência de áudio para cada pessoa que conduzirá reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b214-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="5b214-122">Use o centro de administração do Microsoft 365 para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5b214-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="5b214-123">No centro de administração do Microsoft 365, vá **Billing** para  >  **serviços de compra** de cobrança e, em seguida, na parte inferior da página, selecione Complementos. **Add-ons**</span><span class="sxs-lookup"><span data-stu-id="5b214-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** , and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="5b214-124">Selecione detalhes da **promoção de adoção do áudio Microsoft 365**  >  **Details** e, em seguida, selecione **obter agora**.</span><span class="sxs-lookup"><span data-stu-id="5b214-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details** , and then select **Get now**.</span></span>
3. <span data-ttu-id="5b214-125">Digite o número de licenças necessárias para os organizadores da reunião e conclua o seu pedido.</span><span class="sxs-lookup"><span data-stu-id="5b214-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Captura de tela da licença promocional de adoção da audioconferência":::

    > [!NOTE]
    > <span data-ttu-id="5b214-127">Marque ou desmarque a opção **atribuir automaticamente a todos os usuários sem licenças** , dependendo se você deseja atribuir automaticamente uma licença de audioconferência a todos os usuários que não têm essa licença.</span><span class="sxs-lookup"><span data-stu-id="5b214-127">Clear or select the **Automatically assign to all of your users with no licenses** , depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="5b214-128">Etapa 2: atribuir uma licença de audioconferência para os usuários que liderarem reuniões</span><span class="sxs-lookup"><span data-stu-id="5b214-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="5b214-129">Atribua uma licença a cada pessoa que conduzirá reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b214-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="5b214-130">Use o centro de administração do Microsoft 365 para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5b214-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="5b214-131">Atribuir uma licença a um usuário</span><span class="sxs-lookup"><span data-stu-id="5b214-131">Assign a license to one user</span></span>

1. <span data-ttu-id="5b214-132">No centro de administração do Microsoft 365, vá **para usuários**  >  **ativos** do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b214-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="5b214-133">Selecione a linha do usuário à qual você deseja atribuir a licença e, em seguida, no painel, selecione **licenças e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="5b214-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="5b214-134">Marque a caixa de seleção **conferência de áudio da Microsoft 365** e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="5b214-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="5b214-135">Atribuir uma licença a vários usuários</span><span class="sxs-lookup"><span data-stu-id="5b214-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="5b214-136">No centro de administração do Microsoft 365, vá **para usuários**  >  **ativos** do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b214-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="5b214-137">Selecione os círculos ao lado dos usuários aos quais você deseja atribuir a licença e, em seguida, selecione **gerenciar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="5b214-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="5b214-138">No painel **gerenciar licenças de produto** , selecione **atribuir mais**.</span><span class="sxs-lookup"><span data-stu-id="5b214-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="5b214-139">Marque a caixa de seleção **conferência de áudio da Microsoft 365** e, em seguida, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="5b214-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="5b214-140">Agendar reuniões do Microsoft Teams no Outlook</span><span class="sxs-lookup"><span data-stu-id="5b214-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="5b214-141">Os organizadores da reunião agora podem agendar reuniões no Outlook.</span><span class="sxs-lookup"><span data-stu-id="5b214-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="5b214-142">No Outlook, vá para **calendário** e, em seguida, selecione o botão **nova reunião do teams** .</span><span class="sxs-lookup"><span data-stu-id="5b214-142">In Outlook, go to **Calendar** , and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="5b214-143">Os números de discagem da reunião e a ID de conferência são adicionados automaticamente ao convite de reunião enviado aos participantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="5b214-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="5b214-144">Para saber mais, consulte [agendar uma reunião do teams no Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span><span class="sxs-lookup"><span data-stu-id="5b214-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="5b214-145">Se desejar, você pode personalizar convites de reunião para adicionar o logotipo da sua empresa, links para seu site de suporte e isenção de responsabilidade legal e um rodapé somente texto.</span><span class="sxs-lookup"><span data-stu-id="5b214-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="5b214-146">Para saber mais, confira [personalizar convites de reunião](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="5b214-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="5b214-147">Números de telefone de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="5b214-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="5b214-148">Há dois tipos de números que você pode usar para a sua ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="5b214-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="5b214-149">Você pode usar **números compartilhados** (como na seção [Configurar a conferência de áudio](#set-up-audio-conferencing) anteriormente neste artigo) ou **números dedicados**.</span><span class="sxs-lookup"><span data-stu-id="5b214-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="5b214-150">Veja mais informações sobre cada um deles.</span><span class="sxs-lookup"><span data-stu-id="5b214-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="5b214-151">Números compartilhados</span><span class="sxs-lookup"><span data-stu-id="5b214-151">Shared numbers</span></span>

<span data-ttu-id="5b214-152">Um número compartilhado é um número compartilhado em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="5b214-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="5b214-153">Números compartilhados são números de chamada tarifada e são atribuídos automaticamente quando você configura a conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="5b214-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="5b214-154">Para ver o número padrão atribuído à sua ponte de conferência, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **reuniões**  >  **conferência Bridges** e, em seguida, localize o número para o local mais próximo de você.</span><span class="sxs-lookup"><span data-stu-id="5b214-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges** , and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="5b214-155">Números dedicados</span><span class="sxs-lookup"><span data-stu-id="5b214-155">Dedicated numbers</span></span>

<span data-ttu-id="5b214-156">Um número dedicado é um número que está disponível apenas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="5b214-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="5b214-157">Um número dedicado pode ser um número de chamada tarifada ou um número de chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="5b214-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="5b214-158">Para usar um número dedicado, você precisará primeiro obter o número, atribuí-lo à sua ponte de conferência e atribuir o número a cada pessoa que iniciará reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b214-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="5b214-159">Há algumas maneiras de obter um número exclusivo.</span><span class="sxs-lookup"><span data-stu-id="5b214-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="5b214-160">Você pode obter um número da Microsoft ou transferir (porta) um número existente de seu provedor de serviços atual para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b214-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="5b214-161">Para saber mais sobre como fazer isso, consulte [obtendo números de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="5b214-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="5b214-162">Lembre-se de que, se você usar um número de chamada gratuita, será preciso atribuir primeiro uma licença de créditos de comunicações a cada pessoa que conduzirá reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b214-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="5b214-163">Para saber mais, confira [Configurar créditos de comunicações para a sua organização](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="5b214-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="5b214-164">Depois de ter seu número, atribua-o à sua ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="5b214-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="5b214-165">Use o centro de administração do Microsoft Teams para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5b214-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="5b214-166">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **reuniões**  >  **conferência pontes**.</span><span class="sxs-lookup"><span data-stu-id="5b214-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="5b214-167">Selecione **Adicionar** e, em seguida, selecione **número de chamada** ou número **de chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="5b214-167">Select **Add** , and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="5b214-168">No painel **Adicionar número de telefone** , selecione o número e, em seguida, selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="5b214-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="5b214-169">Em seguida, atribua o número a cada pessoa que iniciará reuniões.</span><span class="sxs-lookup"><span data-stu-id="5b214-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="5b214-170">Use o centro de administração do Microsoft Teams para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5b214-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="5b214-171">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários** , clique no nome de exibição do usuário e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5b214-171">In the left navigation of the Microsoft Teams admin center, select **Users** , click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="5b214-172">Selecione **Editar** ao lado **de videoconferência** e, em seguida, no painel **conferência de áudio** , selecione um número nas listas número de **chamada** ou número de **chamada gratuita** e, em seguida, selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="5b214-172">Select **Edit** next to **Audio Conferencing** , and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5b214-173">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5b214-173">Related topics</span></span>

- [<span data-ttu-id="5b214-174">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="5b214-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="5b214-175">Configurar a conferência de áudio para o Teams</span><span class="sxs-lookup"><span data-stu-id="5b214-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="5b214-176">Números de telefone para audioconferência</span><span class="sxs-lookup"><span data-stu-id="5b214-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="5b214-177">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="5b214-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="5b214-178">Obtendo números de serviço</span><span class="sxs-lookup"><span data-stu-id="5b214-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="5b214-179">Licenças de Complementos do teams</span><span class="sxs-lookup"><span data-stu-id="5b214-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="5b214-180">Atribuir licenças a usuários</span><span class="sxs-lookup"><span data-stu-id="5b214-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
