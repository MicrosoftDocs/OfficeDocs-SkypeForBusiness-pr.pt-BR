---
title: Configurar a licença de telefone da área comum
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Saiba como configurar telefones celulares comuns para "lobbies", áreas de recepção e salas de conferência '
ms.openlocfilehash: d9d77765451f98028f808028822ec42e6e51fdc7
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552299"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="3d00e-103">Configurar a licença de Telefone de Área Comum para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d00e-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="3d00e-104">Telefones celulares comuns não oferecem suporte ao correio de voz.</span><span class="sxs-lookup"><span data-stu-id="3d00e-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="3d00e-105">Um telefone de área comum geralmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, um lobby ou um telefone de conferência.</span><span class="sxs-lookup"><span data-stu-id="3d00e-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="3d00e-106">Telefones celulares comuns são conectados com contas ligadas a uma licença de telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="3d00e-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="3d00e-107">A política TeamsIPPhone também deve ser definida apropriadamente para o telefone ter uma experiência de usuário da área comum.</span><span class="sxs-lookup"><span data-stu-id="3d00e-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="3d00e-108">Nas etapas a seguir, ajudaremos você a configurar uma conta para o sistema telefônico implantar telefones de área comuns para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d00e-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="3d00e-109">Para obter uma experiência de reunião mais completa, incluindo videoconferência, considere comprar a licença de sala de reunião dedicada com um dispositivo de sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="3d00e-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="3d00e-110">Primeiro, você precisa comprar uma licença de telefone (CAP) de área comum e verificar se tem um telefone certificado.</span><span class="sxs-lookup"><span data-stu-id="3d00e-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="3d00e-111">Para procurar e saber mais sobre telefones certificados, acesse [dispositivos Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="3d00e-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="3d00e-112">Etapa 1 - Compre as licenças</span><span class="sxs-lookup"><span data-stu-id="3d00e-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="3d00e-113">No centro de administração do Microsoft 365, vá **Billing**para  >  **serviços de compra** de cobrança e, em seguida, expanda **outros planos**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de tela mostrando o bloco de telefone de área comum](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="3d00e-115">Selecione comprar **telefone da área comum**  >  **agora**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="3d00e-116">Na página check-out, clique em **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="3d00e-117">Expanda **assinaturas complementares** e clique para comprar um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3d00e-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="3d00e-118">Escolha o **plano de chamadas domésticas** ou de **chamadas domésticas e internacionais**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="3d00e-119">Se você estiver usando o roteamento direto do sistema de telefonia da Microsoft, você não precisa de uma licença de plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="3d00e-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="3d00e-120">Você não precisa adicionar uma licença do sistema de telefone.</span><span class="sxs-lookup"><span data-stu-id="3d00e-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="3d00e-121">Ela está incluída na licença do Telefone da Área Comum.</span><span class="sxs-lookup"><span data-stu-id="3d00e-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="3d00e-122">Para obter mais informações sobre licenças, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="3d00e-122">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="3d00e-123">A licença de telefonia do Common Area é compatível com:</span><span class="sxs-lookup"><span data-stu-id="3d00e-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="3d00e-124">Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="3d00e-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="3d00e-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d00e-125">Skype for Business</span></span> |   <span data-ttu-id="3d00e-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="3d00e-126">&#x2714;</span></span> |
|<span data-ttu-id="3d00e-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d00e-127">Microsoft Teams</span></span> |   <span data-ttu-id="3d00e-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="3d00e-128">&#x2714;</span></span> |
|<span data-ttu-id="3d00e-129">Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="3d00e-129">Phone System</span></span> |    <span data-ttu-id="3d00e-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="3d00e-130">&#x2714;</span></span> |
|<span data-ttu-id="3d00e-131">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="3d00e-131">Audio Conferencing</span></span> |       <span data-ttu-id="3d00e-132">&#x2718; &SUP1;</span><span class="sxs-lookup"><span data-stu-id="3d00e-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="3d00e-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3d00e-133">Microsoft Intune</span></span> |        <span data-ttu-id="3d00e-134">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="3d00e-134">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="3d00e-135">Disponibilidade mundial</span><span class="sxs-lookup"><span data-stu-id="3d00e-135">Worldwide Availability</span></span> |    <span data-ttu-id="3d00e-136">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="3d00e-136">&#x2714;</span></span> |
|<span data-ttu-id="3d00e-137">Disponibilidade do canal</span><span class="sxs-lookup"><span data-stu-id="3d00e-137">Channel Availability</span></span> |    <span data-ttu-id="3d00e-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="3d00e-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="3d00e-139">&SUP1; Os telefones da área comum podem ingressar em conferências de áudio por meio do número de discagem fornecido pelo organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="3d00e-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="3d00e-140">&sup2; Não disponível em nuvens soberana</span><span class="sxs-lookup"><span data-stu-id="3d00e-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="3d00e-141">Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças</span><span class="sxs-lookup"><span data-stu-id="3d00e-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="3d00e-142">No centro de administração do Microsoft 365, vá para **usuários**usuários  >  **ativos**  >  **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="3d00e-143">Insira um nome de usuário como "Main" para o primeiro nome e "recepção" para o segundo nome.</span><span class="sxs-lookup"><span data-stu-id="3d00e-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="3d00e-144">Digite um nome para exibição se ele não gerar automaticamente uma como "recepção principal".</span><span class="sxs-lookup"><span data-stu-id="3d00e-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="3d00e-145">Digite um nome de usuário como "MainReception" ou "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="3d00e-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="3d00e-146">Para telefones celulares comuns, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os seus telefones comuns da área.</span><span class="sxs-lookup"><span data-stu-id="3d00e-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="3d00e-147">Além disso, você pode pensar em desmarcar a caixa de seleção **fazer com que este usuário altere sua senha quando entrar pela primeira vez** .</span><span class="sxs-lookup"><span data-stu-id="3d00e-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="3d00e-148">Atribua as licenças ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3d00e-148">Assign the licenses to the user.</span></span> <span data-ttu-id="3d00e-149">Na mesma página, clique para expandir as **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="3d00e-150">Habilite o telefone de área comum e escolha um **plano de chamadas domésticas** ou um **plano de chamadas doméstico e internacional**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="3d00e-152">Se você estiver usando o roteamento direto do sistema de telefonia da Microsoft, você não precisará atribuir uma licença de plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="3d00e-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="3d00e-153">Para obter mais informações, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="3d00e-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="3d00e-154">Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="3d00e-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="3d00e-155">Use o centro de administração do teams para atribuir um número ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3d00e-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="3d00e-156">No centro de administração do Teams, selecione números de telefone de **voz**  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="3d00e-157">Selecione um número na lista de números de telefone e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="3d00e-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="3d00e-158">Na página **atribuir** , na caixa usuário de voz, digite o nome do usuário que usará o telefone e, em seguida, selecione o usuário na lista suspensa **selecionar um usuário de voz** .</span><span class="sxs-lookup"><span data-stu-id="3d00e-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="3d00e-159">Em seguida, você precisa adicionar um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="3d00e-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="3d00e-160">Escolha **Pesquisar por cidade**, **Pesquisar por descrição**ou **Pesquisar por local** na lista suspensa e, em seguida, insira a cidade, a descrição ou o local na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="3d00e-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="3d00e-161">Depois de Pesquisar, procure em **selecionar endereço de emergência** para selecionar o endereço correto para você.</span><span class="sxs-lookup"><span data-stu-id="3d00e-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="3d00e-162">Clique em **Salvar** e seu usuário ficará assim:</span><span class="sxs-lookup"><span data-stu-id="3d00e-162">Click **Save** and your user should look like this:</span></span>

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="3d00e-164">Os usuários só aparecerão se tiverem uma licença do sistema de telefonia aplicada.</span><span class="sxs-lookup"><span data-stu-id="3d00e-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="3d00e-165">Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.</span><span class="sxs-lookup"><span data-stu-id="3d00e-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="3d00e-166">Para obter mais informações, consulte [como obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="3d00e-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="3d00e-167">Você também pode levar seu número de telefone com outra transportadora e "portar" ou transferi-la para o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d00e-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="3d00e-168">Veja [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3d00e-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
