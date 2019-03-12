---
title: Configurar Créditos de Comunicação para sua organização
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: afe1ce61a5c5f137b5123cb530094d6a651ecf7f
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541780"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="2bef5-103">Configurar Créditos de Comunicação para sua organização</span><span class="sxs-lookup"><span data-stu-id="2bef5-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="2bef5-104">Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2bef5-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="2bef5-105">Além disso, é recomendável que você configure créditos de comunicações para seus planos de chamada (doméstico ou internacional) e audioconferências usuários que precisam ter a capacidade de discar para **qualquer destino**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="2bef5-106">Muitos países/regiões são incluídos, mas alguns destinos não podem ser incluídos em suas assinaturas chamar planejar ou conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="2bef5-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="2bef5-107">Se você não configurar créditos de comunicação de cobrança e atribuir uma licença **Créditos de comunicações** para seus usuários e executar check-out de minutos para sua organização (dependendo do seu plano de chamada ou conferência de áudio plano em seu país/região), esses usuários não será possível fazer chamadas ou discar a partir de reuniões de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="2bef5-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="2bef5-108">Você pode obter mais informações, incluindo recomendado, as quantidades de financiamento lendo [Cite Communications créditos?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="2bef5-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bef5-109">Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="2bef5-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="2bef5-110">Etapa 1: Atribuir uma licença de conferência de áudio e chamar planejar para seus usuários</span><span class="sxs-lookup"><span data-stu-id="2bef5-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="2bef5-111">Quando você entrar, você obtém um determinado número de minutos dependendo do seu país/região.</span><span class="sxs-lookup"><span data-stu-id="2bef5-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="2bef5-112">Você pode ver o número de minutos, você receberá a pesquisa para o país ou região [aqui](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2bef5-112">You can see the number of minutes you will get search for the country or region [here](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> <span data-ttu-id="2bef5-113">Depois de usar esses minutos, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="2bef5-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="2bef5-114">Para evitar que isso aconteça, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="2bef5-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="2bef5-115">Para fazer isso, **você precisa atribuir uma conferência de áudio ou uma licença de sistema telefônico** para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2bef5-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="2bef5-116">Atribua uma licença de **Conferência de áudio** para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2bef5-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="2bef5-117">Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2bef5-117">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="2bef5-118">Depois de atribuir essa licença, você precisará configurar serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2bef5-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="2bef5-119">Para obter instruções detalhadas, consulte [tente ou adquirir audioconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2bef5-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="2bef5-120">Atribua o **Sistema telefônico** e uma licença de chamar planejar local ou nacionais e internacional para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2bef5-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="2bef5-121">Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2bef5-121">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2bef5-122">Embora não é obrigatório para créditos de comunicações, você ainda precisará também atribuir um **Domésticas chamar planejar** ou uma licença **nacionais e internacionais chamar planejar** .</span><span class="sxs-lookup"><span data-stu-id="2bef5-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="2bef5-123">Após atribuir essas licenças, você deverá obter os números de telefone da sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="2bef5-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="2bef5-124">Para obter instruções detalhadas, consulte [Configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2bef5-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="2bef5-125">Para obter mais informações, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="2bef5-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="2bef5-126">Etapa 2: Configurar os créditos de comunicações para sua organização</span><span class="sxs-lookup"><span data-stu-id="2bef5-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="2bef5-127">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="2bef5-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2bef5-128">No painel de navegação à esquerda do Centro de administração do Office 365, vá para **faturamento** > **assinaturas** > **Adicionar assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>

3. <span data-ttu-id="2bef5-129">Expanda **inscrições de complemento**e escolha **Communications créditos** > **Compre agora**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-129">Expand **Add-on subscriptions**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
4. <span data-ttu-id="2bef5-130">Na página de inscrição **Créditos de comunicações** , preencha as informações e clique em **Avançar**:</span><span class="sxs-lookup"><span data-stu-id="2bef5-130">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="2bef5-131">**Adicionar fundos** Insira o valor que você deseja adicionar à sua conta.</span><span class="sxs-lookup"><span data-stu-id="2bef5-131">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="2bef5-132">Se você não habilitar o autocarga, depois que essas fundos são esgotados, recursos que são habilitados usando comunicações créditos de chamada será interrompida (por exemplo, o serviço de chamada gratuito entrado).</span><span class="sxs-lookup"><span data-stu-id="2bef5-132">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="2bef5-133">Para evitar ter que alimentar manualmente seu saldo créditos de comunicações de cada vez que sua proporção atinge 0 (zero), é recomendável que você habilita o recurso de autocarga.</span><span class="sxs-lookup"><span data-stu-id="2bef5-133">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="2bef5-134">**Recarga automática** A habilitação da recarga automática recarregará sua conta automaticamente quando o saldo ficar abaixo do limite definido.</span><span class="sxs-lookup"><span data-stu-id="2bef5-134">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="2bef5-135">É recomendável que você use a configuração de **Autocarga** para evitar qualquer interrupção do serviço deve seu saldo Communications créditos atingir 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="2bef5-135">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="2bef5-136">Você será enviado um email quando as transações de carga tiver êxito, quando as transações de carga falham (por exemplo, um cartão de crédito expirado) e quando seu saldo Communications créditos atinge 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="2bef5-136">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="2bef5-137">**Recarregar a quantidade** Insira o valor na caixa **recarregar com** ser adicionada à sua conta, uma vez que ele atinge a quantidade de gatilho abaixo.</span><span class="sxs-lookup"><span data-stu-id="2bef5-137">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="2bef5-138">**Quantidade de gatilho** Insira o valor na caixa **quando o equilíbrio fica abaixo** que será usada ao ' *gatilho* ' a carga de automático.</span><span class="sxs-lookup"><span data-stu-id="2bef5-138">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="2bef5-139">Depois que o seu saldo cair abaixo deste valor, a quantidade de carga será adicionada automaticamente à sua conta.</span><span class="sxs-lookup"><span data-stu-id="2bef5-139">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="2bef5-140">Fundos serão aplicados somente ao Communications créditos na Microsoft publicado taxas quando os serviços são usados.</span><span class="sxs-lookup"><span data-stu-id="2bef5-140">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="2bef5-141">Os fundos não usados no prazo de 12 meses a contar da data de compra expirarão e serão cancelados.</span><span class="sxs-lookup"><span data-stu-id="2bef5-141">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
5. <span data-ttu-id="2bef5-142">Insira suas informações de pagamento e clique em **Fazer pedido**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-142">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="2bef5-143">Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento.</span><span class="sxs-lookup"><span data-stu-id="2bef5-143">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="2bef5-144">Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento.</span><span class="sxs-lookup"><span data-stu-id="2bef5-144">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="2bef5-145">Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="2bef5-145">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="2bef5-146">Cada organização terá o uso de diferente do volume de chamada planejar e taxas a serem considerados.</span><span class="sxs-lookup"><span data-stu-id="2bef5-146">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="2bef5-147">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="2bef5-147">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="2bef5-148">As organizações que já usam Skype para Business Online já como seu provedor de serviços podem obter dados de uso, revisá-lo do **Skype para centro de administração de negócios** > **relatórios** > relatório de**detalhes de uso do PSTN** .</span><span class="sxs-lookup"><span data-stu-id="2bef5-148">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="2bef5-149">Quando você estiver configurando créditos de comunicações, você precisará investigue o uso de chamada para sua organização determinar os valores que você precisará colocar em.</span><span class="sxs-lookup"><span data-stu-id="2bef5-149">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="2bef5-150">Você pode obter informações de uso de chamadas examinando o relatório **Detalhes de uso de PSTN**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-150">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="2bef5-151">Este relatório permite exportar os registros de dados de chamadas para o Excel, se você deseja exportar os dados para armazenamento ou criar relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="2bef5-151">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="2bef5-152">Para ver o uso, consulte [Skype para relatório de uso de PSTN de negócios](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="2bef5-152">To see usage, see [Skype for Business PSTN usage report](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="2bef5-153">Etapa 3: Atribuir uma licença de comunicações créditos aos usuários</span><span class="sxs-lookup"><span data-stu-id="2bef5-153">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="2bef5-154">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="2bef5-154">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2bef5-155">No painel de navegação à esquerda do Centro de administração do Office 365, vá para **usuários** > **usuários ativos**e selecione um ou mais usuários da lista.</span><span class="sxs-lookup"><span data-stu-id="2bef5-155">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="2bef5-156">No painel Ação em **Licenças de**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-156">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="2bef5-157">Na página **licenças do produto** , alternar **Créditos de comunicações** para **em** para atribuir essa licença e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-157">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2bef5-158">Mesmo se você tiver usuários que receberem uma licença **Enterprise E5** , ainda é recomendado que você faça isso.</span><span class="sxs-lookup"><span data-stu-id="2bef5-158">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="2bef5-159">Quer saber mais sobre planos e preços?</span><span class="sxs-lookup"><span data-stu-id="2bef5-159">Want to know about plans and pricing?</span></span>

<span data-ttu-id="2bef5-160">Você pode ver os planos e preços do visitando um dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="2bef5-160">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="2bef5-161">Planos de chamadas</span><span class="sxs-lookup"><span data-stu-id="2bef5-161">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="2bef5-162">Planos de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="2bef5-162">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="2bef5-163">Planos de sistema de telefone</span><span class="sxs-lookup"><span data-stu-id="2bef5-163">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="2bef5-164">Você também pode ver informações entrando [no Centro de administração do Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e pretende **faturamento** > **assinaturas** > **Adicionar assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="2bef5-164">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="2bef5-165">Para ver uma tabela com a licença ou licenças que são necessárias para cada recurso, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2bef5-165">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2bef5-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2bef5-166">Related topics</span></span>

- [<span data-ttu-id="2bef5-167">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2bef5-167">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="2bef5-168">Configurar a caixa postal do Sistema de Telefonia - Ajuda para o administrador</span><span class="sxs-lookup"><span data-stu-id="2bef5-168">Set up Phone System voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="2bef5-169">[Configurar Planos de Chamadas](set-up-calling-plans.md) e [Planos de Chamadas para o Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="2bef5-169">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="2bef5-170">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="2bef5-170">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 