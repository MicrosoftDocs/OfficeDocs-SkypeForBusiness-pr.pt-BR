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
ms.openlocfilehash: cb6cf1ed66f07ba618c74a47bc2c435229b235ec
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779208"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="9844e-103">Configurar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="9844e-103">Set up common area phones</span></span>
<span data-ttu-id="9844e-104">Um CAP (telefone de área comum) é normalmente colocado em áreas como saguões ou outras áreas disponíveis para muitas pessoas.</span><span class="sxs-lookup"><span data-stu-id="9844e-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="9844e-105">Por exemplo, telefones de áreas de recepção, interfones ou telefones de salas de reunião, os CAPs são configurados como dispositivos em vez de usuários e se conectam automaticamente a uma rede.</span><span class="sxs-lookup"><span data-stu-id="9844e-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="9844e-106">Nas etapas a seguir, ajudaremos você a configurar uma conta para o Sistema de Telefonia com planos de chamada, de modo que você possa implantar esses tipos de telefones na sua organização.</span><span class="sxs-lookup"><span data-stu-id="9844e-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="9844e-107">Pré-requisitos para telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="9844e-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="9844e-108">A primeira coisa a ser feita é confirmar que você já:</span><span class="sxs-lookup"><span data-stu-id="9844e-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="9844e-109">Comprou a licença do Telefone de Área Comum e um Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="9844e-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="9844e-110">Pesquisou e comprou telefones aprovados (veja a lista [aqui](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="9844e-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
 - <span data-ttu-id="9844e-111">Atualizou o firmware em seus telefones (veja o firmware suportado [neste tópico](getting-phones-for-skype-for-business-online.md)).</span><span class="sxs-lookup"><span data-stu-id="9844e-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="9844e-112">Você pode verificar o firmware do seu telefone da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9844e-112">You can check the firmware on you phone by doing this:</span></span>
    - <span data-ttu-id="9844e-113">**Telefones Polycom VVX**: acesse **configurações** > **Status** > **plataforma** > **aplicativo** > **principal**.</span><span class="sxs-lookup"><span data-stu-id="9844e-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="9844e-114">**Telefones Yealink**: Ir para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="9844e-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="9844e-115">**Telefones AudioCodes**: vá para o **Menu** > **Status do dispositivo** > **versão de Firmware** na tela de início.</span><span class="sxs-lookup"><span data-stu-id="9844e-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    - <span data-ttu-id="9844e-116">**Telefones de edição de telefone do Lync (LPE)**: vá para o **Menu** > **Informações do sistema** , na tela de início.</span><span class="sxs-lookup"><span data-stu-id="9844e-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="9844e-117">As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9844e-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="9844e-118">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="9844e-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="9844e-119">Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="9844e-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="9844e-120">Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e definindo o parâmetro *EnableDeviceUpdate* para `false`.</span><span class="sxs-lookup"><span data-stu-id="9844e-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="9844e-121">Configuração de um telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="9844e-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="9844e-122">Você precisará seguir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9844e-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="9844e-123">Etapa 1 - Compre as licenças</span><span class="sxs-lookup"><span data-stu-id="9844e-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="9844e-124">No centro de administração do Office 365, acesse **Faturamento** > **Serviços de compra** e adicione **Outros planos**.</span><span class="sxs-lookup"><span data-stu-id="9844e-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="9844e-126">Clique em **Telefone de Área Comum** > **Comprar agora** > na página **Finalizar compra** clique em **Comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="9844e-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="9844e-127">Clique em expandir **Assinaturas de complementos** e depois clique em comprar um Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="9844e-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="9844e-128">Escolha a **domésticas chamar plano** ou **plano de chamada nacionais e internacional**.</span><span class="sxs-lookup"><span data-stu-id="9844e-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="9844e-129">Você não precisa de uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="9844e-129">You don't need a Phone System license.</span></span> <span data-ttu-id="9844e-130">Ela está incluída na licença do **Telefone da Área Comum**.</span><span class="sxs-lookup"><span data-stu-id="9844e-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="9844e-131">Para mais informações sobre licenças, veja [Licenciamento de complementos do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="9844e-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="9844e-132">Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças</span><span class="sxs-lookup"><span data-stu-id="9844e-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="9844e-133">No centro de administração do Office 365, acesse **Usuários** > **Usuários Ativos** > **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="9844e-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="9844e-134">Coloque um **Nome de usuário** como "Principal" para o primeiro nome e "Recepção" para o segundo nome.</span><span class="sxs-lookup"><span data-stu-id="9844e-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="9844e-135">Coloque um **Nome para exibição** se "Recepção Principal"não for gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9844e-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="9844e-136">Coloque um **Nome de usuário** como "RecepçãoPrincipal" ou "LobbyPrincipal".</span><span class="sxs-lookup"><span data-stu-id="9844e-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="9844e-137">Para telefones de área comum, você pode definir uma senha manualmente ou usar a mesma senha para todos os telefones.</span><span class="sxs-lookup"><span data-stu-id="9844e-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="9844e-138">Além disso, você pode desmarcar **Fazer com que esse usuário mude a senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="9844e-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="9844e-139">ESPERE!!</span><span class="sxs-lookup"><span data-stu-id="9844e-139">WAIT!!</span></span> <span data-ttu-id="9844e-140">Não clique em **Adicionar**!!</span><span class="sxs-lookup"><span data-stu-id="9844e-140">Don't click **Add**!!</span></span> <span data-ttu-id="9844e-141">Se você clicou em **Adicionar**, faça isto: acesse o Centro de administração do Office 365 > **Usuários** > **Usuários ativos** e encontre o usuário.</span><span class="sxs-lookup"><span data-stu-id="9844e-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="9844e-142">Em seguida, na página de propriedades do usuário, clique em **Licenças de produtos** e em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9844e-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="9844e-143">Na página **Licenças de produtos**, ative **Telefone de Área Comum** e escolha um **Plano de Chamadas Domésticas** ou um **Plano de Chamadas Domésticas e Internacionais**.</span><span class="sxs-lookup"><span data-stu-id="9844e-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="9844e-144">Se você ainda estiver nessa página, atribua as licenças a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="9844e-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="9844e-145">Na mesma página, clique para expandir as **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="9844e-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="9844e-146">Ative o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9844e-146">Turn on the following:</span></span>
    - <span data-ttu-id="9844e-147">Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="9844e-147">Common Area Phone</span></span>
    - <span data-ttu-id="9844e-148">Você precisa escolher um **Plano de Chamadas Domésticas** ou um **Plano de Chamadas Domésticas e Internacionais**.</span><span class="sxs-lookup"><span data-stu-id="9844e-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

    <span data-ttu-id="9844e-149">A atribuição das licenças ficará assim:</span><span class="sxs-lookup"><span data-stu-id="9844e-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="9844e-151">Só para você saber, o Skype for Business Plan 2 está incluído na licença do **Telefone de Área Comum**.</span><span class="sxs-lookup"><span data-stu-id="9844e-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="9844e-152">Para mais detalhes, veja [Adicionar um usuário](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="9844e-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="9844e-153">Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum</span><span class="sxs-lookup"><span data-stu-id="9844e-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="9844e-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png)  Atribua um número de telefone ao usuário usando o ** Centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="9844e-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="9844e-155">No Centro de administração do Office 365 > **Admin centrais** > **Skype para negócios**.</span><span class="sxs-lookup"><span data-stu-id="9844e-155">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="9844e-156">No **Centro de administração do Skype for Business** >  **Voz** > **Números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="9844e-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="9844e-157">Selecione um número na lista de números de telefone e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="9844e-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="9844e-158">Na página **Atribuir**, na caixa **Usuário de voz** digite o nome do usuário usado para o telefone e, em seguida, selecione o usuário no menu suspenso **Selecionar um usuário de voz**.</span><span class="sxs-lookup"><span data-stu-id="9844e-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="9844e-159">Na página, você precisa adicionar um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="9844e-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="9844e-160">Depois de pesquisar, acesse **Selecionar endereço de emergência** para escolher o endereço certo para você.</span><span class="sxs-lookup"><span data-stu-id="9844e-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="9844e-161">Clique em **Salvar** e seu usuário ficará assim:</span><span class="sxs-lookup"><span data-stu-id="9844e-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="9844e-163">Os usuários só aparecerão se tiverem uma licença do **Sistema de Telefonia** aplicada.</span><span class="sxs-lookup"><span data-stu-id="9844e-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="9844e-164">Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.</span><span class="sxs-lookup"><span data-stu-id="9844e-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="9844e-165">Para mais detalhes, veja [Obtenção de números de telefone para seus usuários](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="9844e-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="9844e-166">Se você está se perguntando, também é possível usar o número de telefone de outra operadora e "*fazer a portabilidade*" ou transferi-lo para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="9844e-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="9844e-167">Consulte, [transferir os números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="9844e-167">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="9844e-168">Etapa 4 - Configurar seu telefone</span><span class="sxs-lookup"><span data-stu-id="9844e-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="9844e-169">**Configuração do modo em um telefone**</span><span class="sxs-lookup"><span data-stu-id="9844e-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="9844e-170">O telefone ou telefones que você possui devem ter o **Modo de Telefone de Área Comum** ligado.</span><span class="sxs-lookup"><span data-stu-id="9844e-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="9844e-171">É melhor conferir para ver se está tudo certo.</span><span class="sxs-lookup"><span data-stu-id="9844e-171">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="9844e-172">**Veja um exemplo de como configurar um telefone Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="9844e-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="9844e-173">Habilite o modo Telefone de Área Comum para o Polycom VVX seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9844e-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="9844e-174">No seu navegador, conecte-se à interface da Web para habilitar o modo CAP.</span><span class="sxs-lookup"><span data-stu-id="9844e-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="9844e-175">Depois acesse **Configuração** e na opção **Configuração do Skype for Business**, selecione **Telefone de Área Comum**.</span><span class="sxs-lookup"><span data-stu-id="9844e-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="9844e-176">Clique em **Sim** para salvar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="9844e-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="9844e-177">Agora que o modo CAP está habilitado, configure o telefone usando o vídeo do telefone.</span><span class="sxs-lookup"><span data-stu-id="9844e-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="9844e-178">O vídeo deve mostrar que **o CaAP está habilitado**.</span><span class="sxs-lookup"><span data-stu-id="9844e-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="9844e-179">Em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9844e-179">Then do the following:</span></span>

    1. <span data-ttu-id="9844e-180">Clique em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="9844e-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="9844e-181">Selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="9844e-181">Select **Advanced**.</span></span>
    3. <span data-ttu-id="9844e-182">Insira a senha.</span><span class="sxs-lookup"><span data-stu-id="9844e-182">Enter the password.</span></span>
    4. <span data-ttu-id="9844e-183">Em **Configurações de administração**, selecione **Configurações do Telefone de Área Comum**.</span><span class="sxs-lookup"><span data-stu-id="9844e-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="9844e-184">Habilite o **CAP** e o **Modo de Administração do CAP**.</span><span class="sxs-lookup"><span data-stu-id="9844e-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="9844e-185">Clique em **Salvar configurações**.</span><span class="sxs-lookup"><span data-stu-id="9844e-185">Click **Save Config**.</span></span>

- <span data-ttu-id="9844e-186">Agora seu telefone está pronto para que você possa entrar na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="9844e-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="9844e-187">Entre selecionando **Configurações** > **Recursos** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="9844e-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="9844e-188">Selecione **Credenciais do usuário**e depois **Entrada na Web (CAP)** para gerar um código.</span><span class="sxs-lookup"><span data-stu-id="9844e-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="9844e-189">Acesse o [portal de configuração](https://aka.ms/skypecap) e entre como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="9844e-189">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="9844e-190">Insira o nome de exibição (p. ex., Recepção Principal).</span><span class="sxs-lookup"><span data-stu-id="9844e-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="9844e-191">Se a caixa de seleção **Pesquisar apenas Telefones de Área Comum** estiver marcada, desmarque e pesquise novamente.</span><span class="sxs-lookup"><span data-stu-id="9844e-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="9844e-192">Na janela de código de pareamento, insira o código exibido no telefone e clique em **Provisão**.</span><span class="sxs-lookup"><span data-stu-id="9844e-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="9844e-193">Após essa última etapa, é possível entrar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9844e-193">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="9844e-194">O site de configuração do CAP informa que ele redefinirá a senha da conta CAP para uma senha aleatória.</span><span class="sxs-lookup"><span data-stu-id="9844e-194">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="9844e-195">Observe que a conta à qual o CAP está se referindo é a conta do Active Directory do Azure (AAD).</span><span class="sxs-lookup"><span data-stu-id="9844e-195">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="9844e-196">Se você criou a conta somente no AAD, então o processo é direto.</span><span class="sxs-lookup"><span data-stu-id="9844e-196">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="9844e-197">Se você tiver sincronizado um Active Directory local para o AAD, anote as credenciais que estiver usando e que serão alteradas pela configuração do CAP.</span><span class="sxs-lookup"><span data-stu-id="9844e-197">If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="9844e-198">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9844e-198">Related topics</span></span>

- <span data-ttu-id="9844e-199">Saiba mais sobre os telefones disponíveis em [Implantação de telefones do Skype for Business Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="9844e-199">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="9844e-200">Obtendo telefones para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9844e-200">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


