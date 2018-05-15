---
title: Configurar telefones de área comum
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="2f076-103">Configurar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="2f076-103">Set up common area phones</span></span>
<span data-ttu-id="2f076-104">Um telefone de área comum (COBRIR) geralmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas.</span><span class="sxs-lookup"><span data-stu-id="2f076-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="2f076-105">Por exemplo, um telefone de área de recepção, porta telefone ou sala de reunião telefone, maiusculas são configuradas como dispositivos em vez de usuários e entrar automaticamente em uma rede.</span><span class="sxs-lookup"><span data-stu-id="2f076-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="2f076-106">Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema telefônico com planos de chamada para que você possa implantar esses tipos de telefones para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2f076-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="2f076-107">Pré-requisitos para telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="2f076-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="2f076-108">A primeira coisa que você precisa fazer é confirmar que você tem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f076-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="2f076-109">Adquirir a licença de telefone de área comum e um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="2f076-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="2f076-110">Pesquisar e comprar telefones aprovadas (exibir a lista [aqui](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="2f076-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="2f076-111">Atualize o firmware em seus telefones (consulte suportada firmware [neste tópico](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="2f076-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="2f076-112">Você pode verificar o firmware no telefone você ao fazer isso:</span><span class="sxs-lookup"><span data-stu-id="2f076-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="2f076-113">**Telefones Polycom VVX**: acesse **configurações** > **Status** > **plataforma** > **aplicativo** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="2f076-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="2f076-114">**Telefones Yealink**: Ir para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="2f076-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="2f076-115">**Telefones AudioCodes**: vá para o **Menu** > **Status do dispositivo** > **versão de Firmware** na tela de início.</span><span class="sxs-lookup"><span data-stu-id="2f076-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="2f076-116">**Telefones de edição de telefone do Lync (LPE)**: vá para o **Menu** > **Informações do sistema** , na tela de início.</span><span class="sxs-lookup"><span data-stu-id="2f076-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="2f076-117">As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2f076-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="2f076-118">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f076-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="2f076-119">Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="2f076-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="2f076-120">Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e definindo o parâmetro *EnableDeviceUpdate* para `false`.</span><span class="sxs-lookup"><span data-stu-id="2f076-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="2f076-121">Configurando um telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="2f076-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="2f076-122">Você precisará devem seguir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2f076-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="2f076-123">Configurar sua conta de usuário para o telefone</span><span class="sxs-lookup"><span data-stu-id="2f076-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="2f076-124">Etapa 1 - adquirir as licenças</span><span class="sxs-lookup"><span data-stu-id="2f076-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="2f076-125">No Centro de administração do Office 365, vá para **faturamento** > **Serviços de compra**, e adicionar **outros planos**.</span><span class="sxs-lookup"><span data-stu-id="2f076-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![COBRIR-license.png](../../images/cap-license.png)
2. <span data-ttu-id="2f076-127">Clique no **Telefone de área comum** > **Compre agora** > no clique página **check-out** em **Compre agora**.</span><span class="sxs-lookup"><span data-stu-id="2f076-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="2f076-128">Clique em expandir **inscrições de complemento** e clique em comprar um plano de chamar.</span><span class="sxs-lookup"><span data-stu-id="2f076-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="2f076-129">Escolha a **domésticas chamar plano** ou **plano de chamada nacionais e internacional**.</span><span class="sxs-lookup"><span data-stu-id="2f076-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="2f076-130">Você não precisa de uma licença de sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="2f076-130">You don't need a Phone System license.</span></span> <span data-ttu-id="2f076-131">Ele tiver incluído com a licença do **Telefone de área comum** .</span><span class="sxs-lookup"><span data-stu-id="2f076-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="2f076-132">Para obter mais informações sobre licenças, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2f076-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="2f076-133">Etapa 2 - criar uma nova conta de usuário para o telefone e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="2f076-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="2f076-134">No Centro de administração do Office 365, vá para **usuários** > **Usuários ativos** > **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="2f076-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="2f076-135">Coloque um **nome de usuário** , como "Main" para o primeiro nome e "Recepção" para o segundo nome.</span><span class="sxs-lookup"><span data-stu-id="2f076-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="2f076-136">Colocar um **nome para exibição** , se ele não gerar automaticamente um como "Main recepção".</span><span class="sxs-lookup"><span data-stu-id="2f076-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="2f076-137">Colocar um **nome de usuário** , como "MainReception" ou "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="2f076-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="2f076-138">Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comum.</span><span class="sxs-lookup"><span data-stu-id="2f076-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="2f076-139">Além disso, você pode achar sobre unselecting **tornar este usuário alterar suas senhas quando eles entrarem pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="2f076-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="2f076-140">AGUARDE!!</span><span class="sxs-lookup"><span data-stu-id="2f076-140">WAIT!!</span></span> <span data-ttu-id="2f076-141">Não clique em **Adicionar**!!</span><span class="sxs-lookup"><span data-stu-id="2f076-141">Don't click **Add**!!</span></span> <span data-ttu-id="2f076-142">Ah, se você clicou em **Add** o fazer isso: Centro de administração do Office 365 > **usuários** > **usuários ativos** e, em seguida, localizar o usuário.</span><span class="sxs-lookup"><span data-stu-id="2f076-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="2f076-143">Na página de propriedades do usuário, clique em **licenças do produto** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2f076-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="2f076-144">Na página **licenças do produto** , ligue o **Telefone de área comum** e escolher um **Domésticas chamar planejar** ou um doméstico e **Internacional chamar planejar**.</span><span class="sxs-lookup"><span data-stu-id="2f076-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="2f076-145">Se você ainda está lá, atribua as licenças para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="2f076-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="2f076-146">Na mesma página, clique para expandir a **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="2f076-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="2f076-147">Ative o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f076-147">Turn on the following:</span></span>
    - <span data-ttu-id="2f076-148">Telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="2f076-148">Common Area Phone</span></span>
    - <span data-ttu-id="2f076-149">Em seguida, você precisará selecionar um **Domésticas chamar planejar** ou um doméstico e **Internacional chamar planejar**.</span><span class="sxs-lookup"><span data-stu-id="2f076-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="2f076-150">Atribuir as licenças terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="2f076-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="2f076-152">Para que você sabe, Skype para negócios plano 2 está incluído com a licença do **Telefone de área comum** .</span><span class="sxs-lookup"><span data-stu-id="2f076-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="2f076-153">Para obter mais detalhes, consulte [Adicionar um usuário](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="2f076-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="2f076-154">Etapa 3 - atribuir um número de telefone ao usuário</span><span class="sxs-lookup"><span data-stu-id="2f076-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="2f076-155">![logotipo-sfb-30x30.png](../../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="2f076-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="2f076-156">No Centro de administração do Office 365 > **Admin centrais** > **Skype para negócios**.</span><span class="sxs-lookup"><span data-stu-id="2f076-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="2f076-157">No **Skype para centro de administração de negócios** >  **voz** > **números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="2f076-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="2f076-158">Selecione um número da lista de números de telefone e clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="2f076-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="2f076-159">Na página **atribuir** , na caixa **usuário de voz** , digite o nome do usuário que é usado para o telefone, então, selecione o usuário em **Selecione um usuário de voz** a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2f076-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="2f076-160">Enquanto estiver na página, você precisará adicionar um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="2f076-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="2f076-161">Depois que você pode pesquisar, procure sob o **Selecione endereço de emergência** para escolher o certo para você.</span><span class="sxs-lookup"><span data-stu-id="2f076-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="2f076-162">Clique em **Salvar** e o usuário deve se parecer com isso:</span><span class="sxs-lookup"><span data-stu-id="2f076-162">Click **Save** and your user should look like this:</span></span>

    ![cobrir-usuário-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="2f076-164">Os usuários serão exibidas apenas se eles têm uma licença de **Sistema telefônico** aplicada.</span><span class="sxs-lookup"><span data-stu-id="2f076-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="2f076-165">Se você acabou de fazer isso, em seguida, em alguns casos, levará um pouco para o usuário seja mostrada na lista.</span><span class="sxs-lookup"><span data-stu-id="2f076-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="2f076-166">Para mais informações, consulte [Getting números de telefone para seus usuários](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="2f076-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="2f076-167">Se você está se perguntando, você também pode tirar seu número de telefone que você tenha com outra operadora e "*porta*" ou transferi-los em para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f076-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="2f076-168">Consulte, [transferir os números de telefone para o Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2f076-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="2f076-169">Etapa 4 - Configurando seu telefone</span><span class="sxs-lookup"><span data-stu-id="2f076-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="2f076-170">**Definindo o modo em um telefone**</span><span class="sxs-lookup"><span data-stu-id="2f076-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="2f076-171">O telefone ou telefones que você tiver devem ter ativado o modo de telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="2f076-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="2f076-172">Você talvez queira verificação de que para certificar-se de que eles fazem.</span><span class="sxs-lookup"><span data-stu-id="2f076-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="2f076-173">**Aqui está um exemplo de como configurar um telefone Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="2f076-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="2f076-174">Habilite o modo de telefone de área comum para o VVX Polycom seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2f076-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="2f076-175">No seu navegador, conecte-se para a interface da web para que você pode ativar o modo de COBRIR.</span><span class="sxs-lookup"><span data-stu-id="2f076-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="2f076-176">Vá para **configuração** e na opção **Skype para configuração de negócios** , selecione o **Telefone de área comum**.</span><span class="sxs-lookup"><span data-stu-id="2f076-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="2f076-177">Clique em **Sim** para salvar as configurações.</span><span class="sxs-lookup"><span data-stu-id="2f076-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="2f076-178">Agora que o modo de COBRIR estiver habilitado, configure o telefone usando a exibição do telefone.</span><span class="sxs-lookup"><span data-stu-id="2f076-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="2f076-179">A exibição deve mostrar **CaAP está habilitado**.</span><span class="sxs-lookup"><span data-stu-id="2f076-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="2f076-180">Em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f076-180">Then do the following:</span></span>

    1. <span data-ttu-id="2f076-181">Clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="2f076-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="2f076-182">Selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="2f076-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="2f076-183">Insira a senha.</span><span class="sxs-lookup"><span data-stu-id="2f076-183">Enter the password.</span></span>
    4. <span data-ttu-id="2f076-184">Nas **configurações de administração**, selecione **Configurações de telefone de área comum**.</span><span class="sxs-lookup"><span data-stu-id="2f076-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="2f076-185">Habilite **COBRIR** e **modo COBRIR Admin**.</span><span class="sxs-lookup"><span data-stu-id="2f076-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="2f076-186">Clique em **Salvar o arquivo Config**.</span><span class="sxs-lookup"><span data-stu-id="2f076-186">Click **Save Config**.</span></span>

- <span data-ttu-id="2f076-187">Okey, agora o telefone estiver pronto para que possa entrar na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="2f076-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="2f076-188">Entrar, selecionando **configurações** > **recursos** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="2f076-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="2f076-189">Selecione **As credenciais do usuário**e selecione **entrar na web (COBRIR)** para gerar um código.</span><span class="sxs-lookup"><span data-stu-id="2f076-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="2f076-190">Vá para o [portal de provisionamento](http://aka.ms/skypecap)e entrar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f076-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="2f076-191">Insira o nome de exibição (por exemplo, Main recepção).</span><span class="sxs-lookup"><span data-stu-id="2f076-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="2f076-192">Se a **pesquisa para telefones de área comum só** está selecionada, desmarque a caixa de seleção e pesquisar novamente.'</span><span class="sxs-lookup"><span data-stu-id="2f076-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="2f076-193">Na janela de código de emparelhamento, insira o código exibido no telefone e clique em **fornecimento**.</span><span class="sxs-lookup"><span data-stu-id="2f076-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="2f076-194">Após essa última etapa, o telefone deve entrar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f076-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="2f076-195">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2f076-195">Related topics</span></span>

- <span data-ttu-id="2f076-196">Saiba mais sobre os telefones disponíveis em [Implantando Skype para telefones Business Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="2f076-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="2f076-197">Obter telefones para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2f076-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


