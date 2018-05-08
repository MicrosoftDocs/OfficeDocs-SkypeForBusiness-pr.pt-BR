---
title: Criar ou modificar uma regra de normalização no Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumo: Saiba como definir, criar e modificar uma regra de normalização no Skype para Business Server 2015.'
ms.openlocfilehash: 5ee0b138d118d0c437255cb3e90321019119aedf
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business-2015"></a><span data-ttu-id="40c3b-103">Criar ou modificar uma regra de normalização no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="40c3b-103">Create or modify a normalization rule in Skype for Business 2015</span></span>
 
<span data-ttu-id="40c3b-104">**Resumo:** Saiba como definir, criar e modificar uma regra de normalização no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="40c3b-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="40c3b-105">Definir, criar e modificar as regras de normalização no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="40c3b-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="40c3b-106">Para definir uma regra de normalização usando Compilar uma Regra de Normalização</span><span class="sxs-lookup"><span data-stu-id="40c3b-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="40c3b-107">Abra o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="40c3b-107">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="40c3b-108">(Opcional) Siga as etapas em [criar ou modificar um plano de discagem no Skype para Business Server 2015](dial-plans.md) por meio da etapa 11 ou [Modify a Dial Plan](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) até a etapa 10.</span><span class="sxs-lookup"><span data-stu-id="40c3b-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) through step 11 or [Modify a Dial Plan](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>
    
3. <span data-ttu-id="40c3b-109">Na **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **nome** (por exemplo, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="40c3b-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>
    
4. <span data-ttu-id="40c3b-110">(Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").</span><span class="sxs-lookup"><span data-stu-id="40c3b-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="40c3b-111">Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="40c3b-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="40c3b-112">**Dígitos iniciais** (Opcional) Especifica os dígitos dos números discados que você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="40c3b-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="40c3b-113">Por exemplo, type425 se quiser que o padrão corresponda discado números que começam com 425.</span><span class="sxs-lookup"><span data-stu-id="40c3b-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
   - <span data-ttu-id="40c3b-114">**Comprimento** Especifique o número de dígitos no padrão correspondido e selecione se você deseja que o padrão para corresponder a esse comprimento exatamente, correspondência discado números que são pelo menos esse comprimento ou números de qualquer tamanho de discados de correspondência.</span><span class="sxs-lookup"><span data-stu-id="40c3b-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
   - <span data-ttu-id="40c3b-115">**Dígitos a serem removidos** (Opcional) Especifique o número de dígitos a serem removidas dos números discados aos iniciais você deseja que o padrão para corresponder.</span><span class="sxs-lookup"><span data-stu-id="40c3b-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
   - <span data-ttu-id="40c3b-116">**Dígitos a adicionar** (Opcional) Especifica os dígitos a ser adicionado à números discados que você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="40c3b-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="40c3b-117">Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="40c3b-118">Por exemplo, se você deixar type7 de **dígitos iniciando** vazio, no campo de **comprimento** e selecione **exatamente**e especifica 0 em **dígitos a serem removidos**, a expressão regular resultante no **padrão para corresponder** é:</span><span class="sxs-lookup"><span data-stu-id="40c3b-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="40c3b-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="40c3b-119">^(\d{7})$</span></span>
    
6. <span data-ttu-id="40c3b-120">Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="40c3b-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
   - <span data-ttu-id="40c3b-121">Um valor que representa o número de dígitos especificado no padrão de correspondência.</span><span class="sxs-lookup"><span data-stu-id="40c3b-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="40c3b-122">Por exemplo, se o padrão de correspondência ^(\d{7})$ e$ 1 na tradução dos números discados de 7 dígitos representa da regra.</span><span class="sxs-lookup"><span data-stu-id="40c3b-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>
    
   - <span data-ttu-id="40c3b-123">(Opcional) Digite um valor no campo **dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido (por exemplo, + 1425).</span><span class="sxs-lookup"><span data-stu-id="40c3b-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>
    
    <span data-ttu-id="40c3b-124">Por exemplo, se contiver **padrão para corresponder** ^(\d{7})$ como o padrão para números discados aos quais e contém **a regra de conversão** + 1425$ 1 como o padrão para e. 164 números de telefone, a regra normaliza 5550100 para + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="40c3b-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="40c3b-125">(Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="40c3b-p104">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40c3b-128">É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente.</span><span class="sxs-lookup"><span data-stu-id="40c3b-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="40c3b-129">Para obter detalhes, consulte [Testar roteamento de voz](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="40c3b-129">For details, see [Test Voice Routing](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span> 
  
9. <span data-ttu-id="40c3b-130">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="40c3b-130">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="40c3b-131">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="40c3b-131">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="40c3b-132">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="40c3b-133">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="40c3b-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="40c3b-134">Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios 2015](voice-route-config-changes.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="40c3b-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="40c3b-135">Para definir uma regra de normalização manualmente</span><span class="sxs-lookup"><span data-stu-id="40c3b-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="40c3b-136">Abra o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="40c3b-136">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="40c3b-137">(Opcional) Siga as etapas em [criar ou modificar um plano de discagem no Skype para Business Server 2015](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="40c3b-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md).</span></span> 
    
3. <span data-ttu-id="40c3b-138">Na **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **nome** (por exemplo, nome rule5DigitExtension a normalização).</span><span class="sxs-lookup"><span data-stu-id="40c3b-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>
    
4. <span data-ttu-id="40c3b-139">(Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="40c3b-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="40c3b-140">Em **Compilar uma regra de normalização**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-140">In **Build a Normalization Rule**, click **Edit**.</span></span>
    
6. <span data-ttu-id="40c3b-141">Digite o seguinte em **Digitar uma expressão regular**:</span><span class="sxs-lookup"><span data-stu-id="40c3b-141">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="40c3b-142">Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.</span><span class="sxs-lookup"><span data-stu-id="40c3b-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
   - <span data-ttu-id="40c3b-143">Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.</span><span class="sxs-lookup"><span data-stu-id="40c3b-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="40c3b-144">Por exemplo, se você digitar ^(\d{7})$ em **corresponder este padrão** e + 1425$ 1 em **regra de conversão**, a regra normaliza 5550100 para + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="40c3b-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="40c3b-145">(Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="40c3b-p107">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
9. <span data-ttu-id="40c3b-148">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="40c3b-148">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="40c3b-149">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="40c3b-149">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="40c3b-150">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="40c3b-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40c3b-151">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="40c3b-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="40c3b-152">Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios 2015](voice-route-config-changes.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="40c3b-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

