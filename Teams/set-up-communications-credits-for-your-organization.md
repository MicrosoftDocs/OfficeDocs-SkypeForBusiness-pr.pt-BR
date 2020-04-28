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
- M365-voice
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
ms.openlocfilehash: 8deb0d00365803ff8ae585f8f6d4dfefbf72108f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905583"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="cdfe3-103">Configurar Créditos de Comunicação para sua organização</span><span class="sxs-lookup"><span data-stu-id="cdfe3-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="cdfe3-104">Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="cdfe3-105">Além disso, recomendamos que você configure créditos de comunicações para seus planos de chamadas (domésticos ou internacionais) e usuários de audioconferência que precisem da capacidade de discar para **qualquer destino**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="cdfe3-106">Muitos países/regiões estão incluídos, mas alguns destinos podem não ser incluídos no seu plano de chamadas ou assinaturas de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="cdfe3-107">Se você não configurar a cobrança de créditos de comunicações e atribuir uma licença de **créditos de comunicações** aos seus usuários e estiver em minutos para a sua organização (dependendo do seu plano de chamadas ou plano de audioconferência em seu país/região), esses usuários não poderão fazer chamadas nem discar de reuniões de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="cdfe3-108">Você pode obter mais informações, incluindo os valores de financiamento recomendados, lendo [o que são créditos de comunicações?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="cdfe3-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdfe3-109">Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="cdfe3-110">Etapa 1: atribuir uma conferência de áudio ou um plano de chamadas a seus usuários</span><span class="sxs-lookup"><span data-stu-id="cdfe3-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="cdfe3-111">Ao se inscrever, você recebe um determinado número de minutos, dependendo do seu país/região.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="cdfe3-112">Você pode procurar seu país ou região na [lista disponibilidade de país ou região para conferências de áudio e planos de chamada](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) para ver o número de minutos que receberá.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="cdfe3-113">Depois de usar esses minutos, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="cdfe3-114">Para evitar que isso aconteça, você precisa configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="cdfe3-115">Para fazer isso, **você precisa atribuir uma conferência de áudio ou uma licença do sistema de telefone** para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="cdfe3-116">Atribua uma licença de **audioconferência** a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="cdfe3-117">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-117">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="cdfe3-118">Depois de atribuir essa licença, você precisará configurar a conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="cdfe3-119">Para obter instruções passo a passo, consulte [experimentar ou comprar o áudio videoconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="cdfe3-120">Atribua um **sistema telefônico** e uma licença de plano de chamadas **domésticas ou domésticas e internacionais** para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="cdfe3-121">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-121">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cdfe3-122">Embora isso não seja obrigatório para créditos de comunicações, você ainda precisa atribuir um **plano de chamadas domésticas** ou uma licença de **plano de chamadas doméstica e internacional** .</span><span class="sxs-lookup"><span data-stu-id="cdfe3-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="cdfe3-123">Após atribuir essas licenças, você deverá obter os números de telefone da sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="cdfe3-124">Para obter instruções passo a passo, consulte [configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="cdfe3-125">Para obter mais informações, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="cdfe3-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="cdfe3-126">Etapa 2: configurar créditos de comunicações para sua organização</span><span class="sxs-lookup"><span data-stu-id="cdfe3-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="cdfe3-127">Entre no novo centro de administração do Microsoft 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-127">Sign in to the new Microsoft 365 admin center with your work or school account.</span></span>
    
2. <span data-ttu-id="cdfe3-128">Na navegação à esquerda do centro de administração do Microsoft 365, vá para**serviços de compra**de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="cdfe3-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="cdfe3-129">Role para baixo e **selecione Complementos**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="cdfe3-130">Selecione **créditos de comunicações**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="cdfe3-131">Na página de assinatura **créditos de comunicação** , preencha as informações e clique em **Avançar**:</span><span class="sxs-lookup"><span data-stu-id="cdfe3-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="cdfe3-132">**Adicionar fundos** Digite o valor que você deseja adicionar à sua conta.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="cdfe3-133">Se você não habilitar a recarga automática, uma vez que esses fundos sejam esgotados, os recursos de chamada habilitados usando créditos de comunicações serão interrompidos (como serviço de chamadas de entrada grátis).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="cdfe3-134">Para evitar a necessidade de reabastecer manualmente o saldo dos créditos de comunicações cada vez que seu saldo atingir 0 (zero), recomendamos que você ative o recurso de recarga automática.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="cdfe3-135">**Recarga automática** A habilitação da recarga automática recarregará sua conta automaticamente quando o saldo ficar abaixo do limite definido.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="cdfe3-136">É recomendável que você use a configuração de **recarga automática** para evitar qualquer interrupção do serviço caso o saldo dos créditos de comunicações atinja 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="cdfe3-137">Você receberá um email quando o recarregamento das transações for bem-sucedido, quando o recarregamento de transações falhar (como um cartão de crédito expirado) e quando o saldo dos créditos de comunicações atingir 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="cdfe3-138">**Valor da recarga** Digite o valor na caixa **recarregar com** que você deseja adicionar à sua conta quando ele atingir o valor de gatilho abaixo.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="cdfe3-139">**Valor do gatilho** Digite o valor de **quando o saldo ficar abaixo** de a caixa que será usada para ' *disparar* ' a recarga automática.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="cdfe3-140">Quando o saldo ficar abaixo desse valor, o valor da recarga será adicionado automaticamente à sua conta.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="cdfe3-141">Os fundos serão aplicados somente aos créditos de comunicação nas tarifas publicadas pela Microsoft quando os serviços forem usados.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="cdfe3-142">Os fundos não usados no prazo de 12 meses a contar da data de compra expirarão e serão cancelados.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="cdfe3-143">A cobrança mensal dos créditos de comunicação só será aplicada se o fundo se tiver sido usado, para saber como verificar o uso mensal, ler o [relatório de uso de PSTN do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="cdfe3-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="cdfe3-144">Insira suas informações de pagamento e clique em **Fazer pedido**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="cdfe3-145">Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="cdfe3-146">Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="cdfe3-147">Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="cdfe3-148">Cada organização terá um uso diferente de taxas e volumes do plano de chamadas a serem considerados.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="cdfe3-149">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="cdfe3-150">As organizações que já usam o Skype for Business online já que o provedor de serviços pode obter dados de uso, revisando-as no >  **centro de administração do Skype for Business\*\*\*\*relata** > o relatório de**detalhes de uso de PSTN** .</span><span class="sxs-lookup"><span data-stu-id="cdfe3-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="cdfe3-151">Ao configurar créditos de comunicações, você precisará investigar o uso da chamada para a sua organização para determinar os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="cdfe3-152">Você pode obter informações de uso de chamadas examinando o relatório **Detalhes de uso de PSTN**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="cdfe3-153">Este relatório permite exportar os registros de dados de chamadas para o Excel se você precisar armazenar os dados ou criar relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="cdfe3-154">Para saber como ver o uso, leia o [relatório de uso de PSTN do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-154">To learn how to see usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="cdfe3-155">Etapa 3: atribuir uma licença de créditos de comunicações aos usuários</span><span class="sxs-lookup"><span data-stu-id="cdfe3-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="cdfe3-156">Entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-156">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="cdfe3-157">Na navegação à esquerda do centro de administração do Microsoft 365, vá **para** > usuários**ativos**do usuário e selecione um ou mais usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="cdfe3-158">Escolha **licenças e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="cdfe3-159">Alterne os **créditos de comunicações** para **ativado** para atribuir a licença e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cdfe3-160">Mesmo que você tenha usuários atribuídos a uma licença **Enterprise E5** , ainda é recomendável que você faça isso.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="cdfe3-161">Quer saber mais sobre planos e preços?</span><span class="sxs-lookup"><span data-stu-id="cdfe3-161">Want to know about plans and pricing?</span></span>

<span data-ttu-id="cdfe3-162">Você pode ver os planos e preços visitando um dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="cdfe3-162">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="cdfe3-163">Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="cdfe3-163">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="cdfe3-164">Planos de audioconferência</span><span class="sxs-lookup"><span data-stu-id="cdfe3-164">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="cdfe3-165">Planos de sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="cdfe3-165">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="cdfe3-166">Você também pode ver as informações conectando- [se ao centro de administração do Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e indo**fazer assinaturas de** >  **cobrança** > **adicionar assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="cdfe3-166">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="cdfe3-167">Para ver uma tabela com as licenças ou licenças necessárias para cada recurso, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe3-167">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cdfe3-168">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cdfe3-168">Related topics</span></span>

- [<span data-ttu-id="cdfe3-169">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cdfe3-169">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="cdfe3-170">Configurar a Caixa Postal na Nuvem - Ajuda da administração</span><span class="sxs-lookup"><span data-stu-id="cdfe3-170">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="cdfe3-171">[Configurar Planos de Chamadas](set-up-calling-plans.md) e [Planos de Chamadas para o Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="cdfe3-171">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="cdfe3-172">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="cdfe3-172">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
