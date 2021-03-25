---
title: Configurar Créditos de comunicação da sua organização
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
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117099"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="fa6ed-103">Configurar Créditos de comunicação da sua organização</span><span class="sxs-lookup"><span data-stu-id="fa6ed-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="fa6ed-104">Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="fa6ed-105">Além disso, recomendamos configurar créditos de comunicação para seus planos de chamada (domésticos ou internacionais) e usuários de Audioconferência que precisam da capacidade de discar para **qualquer destino**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="fa6ed-106">Muitos países/regiões estão incluídos, mas alguns destinos podem não estar incluídos em seu Plano de Chamada ou assinaturas de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="fa6ed-107">Se você não configurar a cobrança de Créditos de Comunicações e atribuir uma licença de **Créditos** de Comunicação aos usuários e ficar sem minutos para sua organização (dependendo do plano de chamada ou do plano de Audioconferência em seu país/região), esses usuários não poderão fazer chamadas ou discar em reuniões de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="fa6ed-108">Você pode obter mais informações, incluindo valores de financiamento recomendados, lendo [O que são créditos de comunicação?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="fa6ed-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa6ed-109">Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="fa6ed-110">Etapa 1: Atribuir uma licença de Audioconferência ou Plano de Chamada aos usuários</span><span class="sxs-lookup"><span data-stu-id="fa6ed-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="fa6ed-111">Ao se inscrever, você tem um determinado número de minutos, dependendo do seu país/região.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="fa6ed-112">Você pode pesquisar seu país ou região na lista de disponibilidade do país ou região para Planos de [Audioconferência](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) e Chamada para ver o número de minutos que você receberá.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="fa6ed-113">Depois de usar esses minutos, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="fa6ed-114">Para evitar que isso aconteça, você precisa configurar Créditos de Comunicação.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="fa6ed-115">Para fazer isso, **você precisa atribuir uma licença de Audioconferência ou Sistema de Telefonia** aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="fa6ed-116">Atribua **uma licença de Audioconferência** aos usuários.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="fa6ed-117">Consulte [Atribuir licenças de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="fa6ed-117">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    <span data-ttu-id="fa6ed-118">Depois de atribuir essa licença, você precisará configurar a audioconferência.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="fa6ed-119">Para obter instruções passo a passo, consulte [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="fa6ed-120">Atribua **o Sistema de** Telefonia e uma licença do **Plano** de Chamadas Doméstico ou Doméstico e Internacional aos usuários.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="fa6ed-121">Consulte [Atribuir licenças de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="fa6ed-121">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa6ed-122">Embora não seja necessário para Créditos de Comunicação, você  ainda precisa atribuir um Plano de Chamada Doméstica ou uma licença do Plano de Chamada Doméstico e **Internacional.**</span><span class="sxs-lookup"><span data-stu-id="fa6ed-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="fa6ed-123">Após atribuir essas licenças, você deverá obter os números de telefone da sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="fa6ed-124">Para obter instruções passo a passo, consulte [Configurar Planos de Chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="fa6ed-125">Para obter mais informações, consulte [Licenciamento de complementos do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="fa6ed-125">For more information, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="fa6ed-126">Etapa 2: Configurar créditos de comunicações para sua organização</span><span class="sxs-lookup"><span data-stu-id="fa6ed-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="fa6ed-127">Entre no Centro de administração do [Microsoft 365](https://portal.office.com/Adminportal) com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="fa6ed-128">Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Cobrança**  >  **de Serviços de Compra.**</span><span class="sxs-lookup"><span data-stu-id="fa6ed-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="fa6ed-129">Role para baixo e selecione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="fa6ed-130">Selecione **Créditos de Comunicação**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="fa6ed-131">Na página **assinatura Créditos de** Comunicação, preencha suas informações e clique em **Próximo**:</span><span class="sxs-lookup"><span data-stu-id="fa6ed-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="fa6ed-132">**Adicionar fundos** Insira o valor que você deseja adicionar à sua conta.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="fa6ed-133">Se você não habilitar a recarga automática, depois que esses fundos são esgotados, os recursos de chamada habilitados usando Créditos de Comunicação serão interrompidos (como o serviço de chamada gratuita de entrada).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="fa6ed-134">Para evitar a reposição manual do saldo de Créditos de Comunicações sempre que o saldo atingir 0 (zero), recomendamos que você habilita o recurso de recarga automática.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="fa6ed-135">**Recarga automática** A habilitação da recarga automática recarregará sua conta automaticamente quando o saldo ficar abaixo do limite definido.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="fa6ed-136">É recomendável que você use a **configuração** de Recarga Automática para evitar qualquer interrupção do serviço caso o saldo de Créditos de Comunicação atinja 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="fa6ed-137">Você receberá um email quando as transações de recarga for bem-sucedidas, quando as transações de recarga falharem (como um cartão de crédito expirado) e quando o saldo de Créditos de Comunicação atingir 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="fa6ed-138">**Quantidade de recarga** Insira o valor na caixa **Recarregar com** que você deseja adicionar à sua conta depois que ele atingir a quantidade de gatilho abaixo.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="fa6ed-139">**Quantidade de gatilho** Insira a quantidade em **Quando o saldo ficar abaixo** da caixa que será usada para ' *disparar*  ' a recarga automática.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="fa6ed-140">Quando o saldo ficar abaixo desse valor, o valor da recarga será adicionado automaticamente à sua conta.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="fa6ed-141">Os fundos serão aplicados somente aos Créditos de Comunicação às taxas publicadas da Microsoft quando os serviços são usados.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="fa6ed-142">Os fundos não usados no prazo de 12 meses a contar da data de compra expirarão e serão cancelados.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="fa6ed-143">A cobrança mensal de Créditos de Comunicação só será aplicada se o fundo alloted tiver sido usado, para saber como verificar seu uso mensal, leia Relatório de uso do [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fa6ed-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="fa6ed-144">Insira suas informações de pagamento e clique em **Fazer pedido**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="fa6ed-145">Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="fa6ed-146">Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="fa6ed-147">Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="fa6ed-148">Cada organização terá um uso diferente de volume e taxas do Plano de Chamada a considerar.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="fa6ed-149">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="fa6ed-150">As organizações que já usam o Skype for Business Online como provedor de serviços podem obter dados de uso revisá-los no relatório de detalhes de uso do  >    >  **PSTN** do Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="fa6ed-151">Ao configurar os Créditos de Comunicação, você precisará investigar o uso de chamada para sua organização para determinar os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="fa6ed-152">Você pode obter informações de uso de chamadas examinando o relatório **Detalhes de uso de PSTN**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="fa6ed-153">Este relatório permite exportar os registros de dados de chamada para o Excel se precisar armazenar os dados ou criar relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="fa6ed-154">Para saber como ver o uso, leia o relatório de uso [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-154">To learn how to see usage, read [PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="fa6ed-155">Etapa 3: Atribuir uma licença de Créditos de Comunicação aos usuários</span><span class="sxs-lookup"><span data-stu-id="fa6ed-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="fa6ed-156">Entre no Centro de administração do [Microsoft 365](https://portal.office.com/Adminportal) com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="fa6ed-157">Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Usuários**  >  **Usuários ativos** e selecione um usuário na lista.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="fa6ed-158">Escolha **Licenças e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="fa6ed-159">Alterne **créditos de comunicações** **para On** para atribuir essa licença e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa6ed-160">Mesmo que você tenha usuários que tenham uma licença **enterprise E5,** ainda é recomendável que você faça isso.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="fa6ed-161">Você pode usar o [Powershell](/powershell/module/skype/?view=skype-ps) para atribuir licenças e aplicativos a vários usuários com um comando.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-161">You can use [Powershell](/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="fa6ed-162">Quer saber mais sobre planos e preços?</span><span class="sxs-lookup"><span data-stu-id="fa6ed-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="fa6ed-163">Você pode ver os planos e os preços visitando um dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="fa6ed-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="fa6ed-164">Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="fa6ed-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="fa6ed-165">Planos de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="fa6ed-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="fa6ed-166">Planos do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="fa6ed-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="fa6ed-167">Você também pode ver informações ao entrar no Centro de administração do [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e ir para **Cobrança**  >  **de Assinaturas**  >  **Adicionar assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="fa6ed-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="fa6ed-168">Para ver uma tabela com a licença ou licenças que você precisará para cada recurso, consulte [Licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="fa6ed-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fa6ed-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fa6ed-169">Related topics</span></span>

- [<span data-ttu-id="fa6ed-170">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fa6ed-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="fa6ed-171">Configurar a Caixa Postal na Nuvem - Ajuda da administração</span><span class="sxs-lookup"><span data-stu-id="fa6ed-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="fa6ed-172">[Configurar planos de chamada e](set-up-calling-plans.md) planos de chamada para o Microsoft [365 ou Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="fa6ed-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="fa6ed-173">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="fa6ed-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
