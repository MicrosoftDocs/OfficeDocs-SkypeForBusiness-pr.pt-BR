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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar os telefones de área comum para lobbies, áreas de recepção e salas de conferência '
ms.openlocfilehash: 74806d3dfc66c27c144d6c3a4e1ddd5c6c7e7c60
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993601"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="88afc-103">Configurar a licença de Telefone de Área Comum para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88afc-103">Set up the Common Area Phone license for Microsoft Teams</span></span>

<span data-ttu-id="88afc-104">Um telefone de área comum geralmente é colocado em uma área de como um lobby ou outro que está disponível para muitas pessoas para fazer uma chamada; Por exemplo, uma recepção área, lobby ou conferência telefônica.</span><span class="sxs-lookup"><span data-stu-id="88afc-104">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="88afc-105">Telefones de área comum são configurados como dispositivos em vez de usuários e podem entrar automaticamente em uma rede.</span><span class="sxs-lookup"><span data-stu-id="88afc-105">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="88afc-106">Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema telefônico implantar telefones de área comum para sua organização.</span><span class="sxs-lookup"><span data-stu-id="88afc-106">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="88afc-107">Para uma sala de reunião mais completa experiência, incluindo serviços de audioconferência, considere adquirir a licença de sala de reunião dedicada com uma reunião do dispositivo de sala.</span><span class="sxs-lookup"><span data-stu-id="88afc-107">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="88afc-108">As primeiras coisas que você precisa fazer são compra uma licença de telefone de área comum (COBRIR) e certifique-se de que você tiver um telefone de certificados.</span><span class="sxs-lookup"><span data-stu-id="88afc-108">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="88afc-109">Para procurar e saber mais sobre certificados telefones, vá para [dispositivos de equipes da Microsoft](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="88afc-109">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="88afc-110">Etapa 1 - Compre as licenças</span><span class="sxs-lookup"><span data-stu-id="88afc-110">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="88afc-111">No Centro de administração do Office 365, vá para **faturamento** > **Serviços de compra** e, em seguida, expanda **outros planos**.</span><span class="sxs-lookup"><span data-stu-id="88afc-111">In the Office 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de tela mostrando os blocos de telefone de área comum](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="88afc-113">Selecione o **telefone de área comum** > **Compre agora**.</span><span class="sxs-lookup"><span data-stu-id="88afc-113">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="88afc-114">Na página de **check-out** , clique em **Comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="88afc-114">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="88afc-115">Expanda **inscrições de complemento** e clique em para adquirir um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="88afc-115">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="88afc-116">Escolha a **domésticas chamar plano** ou **plano de chamada nacionais e internacional**.</span><span class="sxs-lookup"><span data-stu-id="88afc-116">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="88afc-117">Você não precisa de uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="88afc-117">You don't need a Phone System license.</span></span> <span data-ttu-id="88afc-118">Ela está incluída na licença do Telefone da Área Comum.</span><span class="sxs-lookup"><span data-stu-id="88afc-118">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="88afc-119">Para obter mais informações sobre licenças, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="88afc-119">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="88afc-120">Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças</span><span class="sxs-lookup"><span data-stu-id="88afc-120">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="88afc-121">No Centro de administração do Office 365, vá para **usuários** > **usuários ativos** > **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="88afc-121">In the Office 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="88afc-122">Insira um nome de usuário como "Main" para o primeiro nome e "Recepção" para o segundo nome.</span><span class="sxs-lookup"><span data-stu-id="88afc-122">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="88afc-123">Insira um nome de exibição se ele não gerar automaticamente um como "Main recepção".</span><span class="sxs-lookup"><span data-stu-id="88afc-123">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="88afc-124">Insira um nome de usuário, como "MainReception" ou "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="88afc-124">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="88afc-125">Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comum.</span><span class="sxs-lookup"><span data-stu-id="88afc-125">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="88afc-126">Além disso, você pode achar sobre desmarcar a caixa de seleção **tornar este usuário alterar suas senhas quando eles entrarem pela primeira vez** .</span><span class="sxs-lookup"><span data-stu-id="88afc-126">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="88afc-127">Atribua as licenças para o usuário.</span><span class="sxs-lookup"><span data-stu-id="88afc-127">Assign the licenses to the user.</span></span> <span data-ttu-id="88afc-128">Na mesma página, clique para expandir as **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="88afc-128">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="88afc-129">Ligue o telefone de área comum e escolha um **Domésticas chamar planejar** ou um **nacionais e internacionais chamar planejar**.</span><span class="sxs-lookup"><span data-stu-id="88afc-129">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Atribuição de licença captura de tela mostrando](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="88afc-131">Para obter mais informações, consulte [Adicionar um usuário](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="88afc-131">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="88afc-132">Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="88afc-132">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="88afc-133">Use o Skype para centro de administração de negócios para atribuir um número ao usuário.</span><span class="sxs-lookup"><span data-stu-id="88afc-133">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="88afc-134">No Centro de administração do Microsoft 365, selecione **Admin centrais** > **& equipes Skype** > **portal herdada**.</span><span class="sxs-lookup"><span data-stu-id="88afc-134">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="88afc-135">No Skype para centro de administração de negócios, selecione **voz** > **números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="88afc-135">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="88afc-136">Selecione um número na lista de números de telefone e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="88afc-136">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="88afc-137">Na página **atribuir** , na caixa de usuário de voz, digite o nome do usuário que estarão usando o telefone e selecione o usuário na lista suspensa **Selecione um usuário de voz** .</span><span class="sxs-lookup"><span data-stu-id="88afc-137">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="88afc-138">Na página, você precisa adicionar um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="88afc-138">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="88afc-139">Escolha **pesquisa por cidade**, **pesquisa por descrição**ou **pesquisa por local** na lista suspensa e, em seguida, insira a cidade, descrição ou local na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="88afc-139">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="88afc-140">Depois que você pode pesquisar, procure em **Selecione endereço de emergência** para escolher o certo para você.</span><span class="sxs-lookup"><span data-stu-id="88afc-140">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="88afc-141">Clique em **Salvar** e seu usuário ficará assim:</span><span class="sxs-lookup"><span data-stu-id="88afc-141">Click **Save** and your user should look like this:</span></span>

   ![Atribuição de licença captura de tela mostrando](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="88afc-143">Os usuários serão exibidas apenas se eles têm uma licença de sistema telefônico aplicada.</span><span class="sxs-lookup"><span data-stu-id="88afc-143">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="88afc-144">Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.</span><span class="sxs-lookup"><span data-stu-id="88afc-144">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="88afc-145">Para obter mais informações, consulte [Getting números de telefone para seus usuários](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="88afc-145">For more information, see [Getting phone numbers for your users](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="88afc-146">Você também pode aproveitar o seu número de telefone que você tenha com outra operadora e "porta" ou transferi-la para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="88afc-146">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="88afc-147">Consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="88afc-147">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


