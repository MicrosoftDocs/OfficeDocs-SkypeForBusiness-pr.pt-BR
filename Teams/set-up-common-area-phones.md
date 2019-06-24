---
title: Configurar a licença de Telefone de Área Comum para o Microsoft Teams
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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar telefones celulares comuns para "lobbies", áreas de recepção e salas de conferência '
ms.openlocfilehash: a62399c1c7b7b27e35fdea1fc52b9531a1fa25cc
ms.sourcegitcommit: 66213b972920b4e09faf7d7e732c4bfe7b322ac4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131508"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="7e85b-103">Configurar a licença de Telefone de Área Comum para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e85b-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="7e85b-104">Telefones celulares comuns não oferecem suporte ao correio de voz.</span><span class="sxs-lookup"><span data-stu-id="7e85b-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="7e85b-105">Um telefone de área comum geralmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, um lobby ou um telefone de conferência.</span><span class="sxs-lookup"><span data-stu-id="7e85b-105">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="7e85b-106">Os telefones de área comuns são configurados como dispositivos, e não usuários, e podem entrar automaticamente em uma rede.</span><span class="sxs-lookup"><span data-stu-id="7e85b-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="7e85b-107">Nas etapas a seguir, ajudaremos você a configurar uma conta para o sistema telefônico implantar telefones de área comuns para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="7e85b-107">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="7e85b-108">Para obter uma experiência de reunião mais completa, incluindo videoconferência, considere comprar a licença de sala de reunião dedicada com um dispositivo de sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="7e85b-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="7e85b-109">As primeiras coisas que você precisa fazer são comprar uma licença de CAP (telefone fixo) comum e verificar se você tem um telefone certificado.</span><span class="sxs-lookup"><span data-stu-id="7e85b-109">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="7e85b-110">Para procurar e saber mais sobre telefones certificados, acesse [dispositivos Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="7e85b-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="7e85b-111">Etapa 1 - Compre as licenças</span><span class="sxs-lookup"><span data-stu-id="7e85b-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="7e85b-112">No centro de administração do Microsoft 365, vá para**serviços de compra** de **cobrança** > e, em seguida, expanda **outros planos**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de tela mostrando o bloco de telefone de área comum](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="7e85b-114">Selecione comprar **telefone** > da área comum**agora**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="7e85b-115">Na página **check-out** , clique em **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-115">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="7e85b-116">Expanda **assinaturas complementares** e clique para comprar um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7e85b-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="7e85b-117">Escolha o **plano de chamadas domésticas** ou de **chamadas domésticas e internacionais**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e85b-118">Você não precisa de uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="7e85b-118">You don't need a Phone System license.</span></span> <span data-ttu-id="7e85b-119">Ela está incluída na licença do Telefone da Área Comum.</span><span class="sxs-lookup"><span data-stu-id="7e85b-119">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="7e85b-120">Para obter mais informações sobre licenças, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="7e85b-120">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="7e85b-121">A licença de telefonia do Common Area é compatível com:</span><span class="sxs-lookup"><span data-stu-id="7e85b-121">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="7e85b-122">Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="7e85b-122">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="7e85b-123">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7e85b-123">Skype for Business</span></span> |   <span data-ttu-id="7e85b-124">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="7e85b-124">&#x2714;</span></span> |
|<span data-ttu-id="7e85b-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e85b-125">Microsoft Teams</span></span> |   <span data-ttu-id="7e85b-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="7e85b-126">&#x2714;</span></span> |
|<span data-ttu-id="7e85b-127">Sistemas de telefonia</span><span class="sxs-lookup"><span data-stu-id="7e85b-127">Phone Systems</span></span> |    <span data-ttu-id="7e85b-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="7e85b-128">&#x2714;</span></span> |
|<span data-ttu-id="7e85b-129">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="7e85b-129">Audio Conferencing</span></span> |       <span data-ttu-id="7e85b-130">&#x2718; &SUP1;</span><span class="sxs-lookup"><span data-stu-id="7e85b-130">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="7e85b-131">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7e85b-131">Microsoft Intune</span></span> |        <span data-ttu-id="7e85b-132">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="7e85b-132">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="7e85b-133">Disponibilidade mundial</span><span class="sxs-lookup"><span data-stu-id="7e85b-133">Worldwide Availability</span></span> |    <span data-ttu-id="7e85b-134">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="7e85b-134">&#x2714;</span></span> |
|<span data-ttu-id="7e85b-135">Disponibilidade do canal</span><span class="sxs-lookup"><span data-stu-id="7e85b-135">Channel Availability</span></span> |    <span data-ttu-id="7e85b-136">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="7e85b-136">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="7e85b-137">&SUP1; Os telefones da área comum podem ingressar em conferências de áudio por meio do número de discagem fornecido pelo organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="7e85b-137">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="7e85b-138">&sup2; Não disponível em nuvens soberana</span><span class="sxs-lookup"><span data-stu-id="7e85b-138">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="7e85b-139">Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças</span><span class="sxs-lookup"><span data-stu-id="7e85b-139">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="7e85b-140">No centro de administração do Microsoft 365, vá para **usuários** > usuários**ativos** > **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-140">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="7e85b-141">Insira um nome de usuário como "Main" para o primeiro nome e "recepção" para o segundo nome.</span><span class="sxs-lookup"><span data-stu-id="7e85b-141">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="7e85b-142">Digite um nome para exibição se ele não gerar automaticamente uma como "recepção principal".</span><span class="sxs-lookup"><span data-stu-id="7e85b-142">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="7e85b-143">Digite um nome de usuário como "MainReception" ou "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="7e85b-143">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="7e85b-144">Para telefones celulares comuns, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os seus telefones comuns da área.</span><span class="sxs-lookup"><span data-stu-id="7e85b-144">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="7e85b-145">Além disso, você pode pensar em desmarcar a caixa de seleção **fazer com que este usuário altere sua senha quando entrar pela primeira vez** .</span><span class="sxs-lookup"><span data-stu-id="7e85b-145">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="7e85b-146">Atribua as licenças ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7e85b-146">Assign the licenses to the user.</span></span> <span data-ttu-id="7e85b-147">Na mesma página, clique para expandir as **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-147">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="7e85b-148">Habilite o telefone de área comum e escolha um **plano de chamadas domésticas** ou um **plano de chamadas doméstico e internacional**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-148">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="7e85b-150">Para obter mais informações, consulte [Adicionar um usuário](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="7e85b-150">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="7e85b-151">Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="7e85b-151">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="7e85b-152">Use o centro de administração do Skype for Business para atribuir um número ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7e85b-152">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="7e85b-153">No centro de administração do Microsoft 365, **selecione centros** > de administração e**equipes & portal do Skype** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-153">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="7e85b-154">No centro de administração do Skype for Business, selecione**números de telefone**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="7e85b-154">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="7e85b-155">Selecione um número na lista de números de telefone e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="7e85b-155">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="7e85b-156">Na página **atribuir** , na caixa usuário de voz, digite o nome do usuário que usará o telefone e, em seguida, selecione o usuário na lista suspensa **selecionar um usuário de voz** .</span><span class="sxs-lookup"><span data-stu-id="7e85b-156">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="7e85b-157">Na página, você precisa adicionar um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="7e85b-157">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="7e85b-158">Escolha **Pesquisar por cidade**, **Pesquisar por descrição**ou **Pesquisar por local** na lista suspensa e, em seguida, insira a cidade, a descrição ou o local na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="7e85b-158">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="7e85b-159">Depois de Pesquisar, procure em **selecionar endereço de emergência** para selecionar o endereço correto para você.</span><span class="sxs-lookup"><span data-stu-id="7e85b-159">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="7e85b-160">Clique em **Salvar** e seu usuário ficará assim:</span><span class="sxs-lookup"><span data-stu-id="7e85b-160">Click **Save** and your user should look like this:</span></span>

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="7e85b-162">Os usuários só aparecerão se tiverem uma licença do sistema de telefonia aplicada.</span><span class="sxs-lookup"><span data-stu-id="7e85b-162">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="7e85b-163">Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.</span><span class="sxs-lookup"><span data-stu-id="7e85b-163">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="7e85b-164">Para obter mais informações, consulte [como obter números de telefone para seus usuários](/microsoftteams/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="7e85b-164">For more information, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="7e85b-165">Você também pode levar seu número de telefone com outra transportadora e "portar" ou transferi-la para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e85b-165">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="7e85b-166">Veja [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="7e85b-166">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


