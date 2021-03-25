---
title: Configurar a licença do Telefone de Área Comum
ms.author: serdars
author: SerdarSoysal
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
description: 'Saiba como configurar Telefones de Área Comum para lobbies, áreas de recepção e salas de conferência '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117109"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="a307e-103">Configurar a licença de Telefone de Área Comum para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a307e-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="a307e-104">Telefones de área comum não suportam caixa postal.</span><span class="sxs-lookup"><span data-stu-id="a307e-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="a307e-105">Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, lobby ou telefone de conferência.</span><span class="sxs-lookup"><span data-stu-id="a307e-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="a307e-106">Telefones de área comum são assinados com contas vinculadas a uma licença de Telefone de Área Comum.</span><span class="sxs-lookup"><span data-stu-id="a307e-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="a307e-107">A política TeamsIPPhone também deve ser adequadamente definida para que o telefone tenha uma experiência de usuário de área comum.</span><span class="sxs-lookup"><span data-stu-id="a307e-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="a307e-108">Nas etapas abaixo, ajudaremos você a configurar uma conta para o Sistema de Telefonia para implantar telefones de área comum para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a307e-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="a307e-109">Para obter uma experiência de sala de reunião mais completa, incluindo audioconferência, considere comprar a licença da Sala de Reunião dedicada com um dispositivo de sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="a307e-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="a307e-110">Primeiro, você precisa comprar uma licença de Telefone de Área Comum (CAP) e certificar-se de ter um telefone certificado.</span><span class="sxs-lookup"><span data-stu-id="a307e-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="a307e-111">Para pesquisar e saber mais sobre telefones certificados, acesse dispositivos [do Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="a307e-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="a307e-112">Etapa 1 - Compre as licenças</span><span class="sxs-lookup"><span data-stu-id="a307e-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="a307e-113">No Centro de administração do Microsoft 365, vá para **Serviços de** Compra de Cobrança e  >   **expanda Outros planos.**</span><span class="sxs-lookup"><span data-stu-id="a307e-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de tela mostrando o tile Common Area Phone](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="a307e-115">Selecione **Common Area Phone** Buy  >  **now**.</span><span class="sxs-lookup"><span data-stu-id="a307e-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="a307e-116">Na página Checkout, clique em **Comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="a307e-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="a307e-117">Expanda **assinaturas de complemento e** clique para comprar um Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="a307e-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="a307e-118">Escolha o Plano **de Chamada Doméstica** ou o Plano de Chamada Doméstico e **Internacional.**</span><span class="sxs-lookup"><span data-stu-id="a307e-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="a307e-119">Se você estiver usando o Roteamento Direto do Sistema de Telefonia da Microsoft, não precisará de uma licença de Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="a307e-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="a307e-120">Você não precisa adicionar uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="a307e-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="a307e-121">Ela está incluída na licença do Telefone da Área Comum.</span><span class="sxs-lookup"><span data-stu-id="a307e-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="a307e-122">Para obter mais informações sobre licenças, consulte [Licenciamento de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="a307e-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="a307e-123">A licença Common Area Phone dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="a307e-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="a307e-124">Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="a307e-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="a307e-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a307e-125">Skype for Business</span></span> |   <span data-ttu-id="a307e-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="a307e-126">&#x2714;</span></span> |
|<span data-ttu-id="a307e-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a307e-127">Microsoft Teams</span></span> |   <span data-ttu-id="a307e-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="a307e-128">&#x2714;</span></span> |
|<span data-ttu-id="a307e-129">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="a307e-129">Phone System</span></span> |    <span data-ttu-id="a307e-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="a307e-130">&#x2714;</span></span> |
|<span data-ttu-id="a307e-131">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="a307e-131">Audio Conferencing</span></span> |       <span data-ttu-id="a307e-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="a307e-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="a307e-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a307e-133">Microsoft Intune</span></span> |    <span data-ttu-id="a307e-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="a307e-134">&#x2718;</span></span> |
|<span data-ttu-id="a307e-135">Disponibilidade Mundial</span><span class="sxs-lookup"><span data-stu-id="a307e-135">Worldwide Availability</span></span> |       <span data-ttu-id="a307e-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="a307e-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="a307e-137">Disponibilidade do Canal</span><span class="sxs-lookup"><span data-stu-id="a307e-137">Channel Availability</span></span> |    <span data-ttu-id="a307e-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="a307e-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="a307e-139">&sup1; Os Telefones de Área Comum podem ingressar em conferências de áudio por meio do número de discagem fornecido pelo organizador da reunião</span><span class="sxs-lookup"><span data-stu-id="a307e-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="a307e-140">&sup2; Não disponível em nuvens soberanas</span><span class="sxs-lookup"><span data-stu-id="a307e-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="a307e-141">Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças</span><span class="sxs-lookup"><span data-stu-id="a307e-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="a307e-142">No Centro de administração do Microsoft 365, vá para usuários  >  **ativos**  >  **adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="a307e-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="a307e-143">Insira um nome de usuário como "Main" para o primeiro nome e "Recepção" para o segundo nome.</span><span class="sxs-lookup"><span data-stu-id="a307e-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="a307e-144">Insira um nome de exibição se ele não gerar automaticamente um como "Recepção Principal".</span><span class="sxs-lookup"><span data-stu-id="a307e-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="a307e-145">Insira um nome de usuário como "MainReception" ou "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="a307e-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="a307e-146">Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comum.</span><span class="sxs-lookup"><span data-stu-id="a307e-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="a307e-147">Além disso, você pode pensar em limpar a caixa de seleção Fazer com que **esse usuário altere** a senha ao entrar pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="a307e-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="a307e-148">Atribua as licenças ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a307e-148">Assign the licenses to the user.</span></span> <span data-ttu-id="a307e-149">Na mesma página, clique para expandir as **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="a307e-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="a307e-150">A turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a Domestic and International Calling **Plan**.</span><span class="sxs-lookup"><span data-stu-id="a307e-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="a307e-152">Se você estiver usando o Roteamento Direto do Sistema de Telefonia da Microsoft, não será necessário atribuir uma licença de Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="a307e-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="a307e-153">Para obter mais informações, [consulte Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="a307e-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="a307e-154">Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="a307e-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="a307e-155">Use o centro de administração do Teams para atribuir um número ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a307e-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="a307e-156">No centro de administração do Teams, selecione **Números de Telefone** de  >  **Voz**.</span><span class="sxs-lookup"><span data-stu-id="a307e-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="a307e-157">Selecione um número na lista de números de telefone e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="a307e-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="a307e-158">Na página **Atribuir,** na caixa Usuário voz, digite o nome do usuário que estará usando  o telefone e selecione o usuário na listada Selecionar um usuário de voz.</span><span class="sxs-lookup"><span data-stu-id="a307e-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="a307e-159">Em seguida, você precisa adicionar um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="a307e-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="a307e-160">Escolha **Pesquisar por cidade,** **Pesquisar** por descrição ou Pesquisar por local na listada e insira a cidade, a descrição ou o local na caixa de texto. </span><span class="sxs-lookup"><span data-stu-id="a307e-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="a307e-161">Depois de pesquisar, procure em **Selecionar endereço de emergência** para escolher o endereço certo para você.</span><span class="sxs-lookup"><span data-stu-id="a307e-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="a307e-162">Clique em **Salvar** e seu usuário ficará assim:</span><span class="sxs-lookup"><span data-stu-id="a307e-162">Click **Save** and your user should look like this:</span></span>

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="a307e-164">Os usuários só aparecerão se eles têm uma licença do Sistema de Telefonia aplicada.</span><span class="sxs-lookup"><span data-stu-id="a307e-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="a307e-165">Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.</span><span class="sxs-lookup"><span data-stu-id="a307e-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="a307e-166">Para obter mais informações, consulte [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="a307e-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="a307e-167">Você também pode levar seu número de telefone que você tem com outra operadora e "porta" ou transferi-lo para o Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="a307e-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a307e-168">Consulte [Transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a307e-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>