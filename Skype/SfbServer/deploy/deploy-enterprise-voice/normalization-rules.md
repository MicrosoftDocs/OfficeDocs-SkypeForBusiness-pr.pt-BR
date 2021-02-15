---
title: Criar ou modificar uma regra de normalização no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Resumo: Saiba como definir, criar e modificar uma regra de normalização no Skype for Business Server.'
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830761"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="ccb60-103">Criar ou modificar uma regra de normalização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ccb60-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="ccb60-104">**Resumo:** Saiba como definir, criar e modificar uma regra de normalização no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ccb60-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="ccb60-105">Definir, criar e modificar regras de normalização no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ccb60-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="ccb60-106">Para definir uma regra de normalização usando Criar uma Regra de Normalização</span><span class="sxs-lookup"><span data-stu-id="ccb60-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="ccb60-107">Abrir o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ccb60-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="ccb60-108">(Opcional) Siga as etapas em Criar ou modificar um plano de discagem no [Skype for Business Server](dial-plans.md) até a etapa 11 ou Modificar um Plano de Discagem até [a](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) etapa 10.</span><span class="sxs-lookup"><span data-stu-id="ccb60-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="ccb60-109">Em Nova Regra de **Normalização** ou Editar Regra de **Normalização,** digite um nome que descreve o padrão de número que está sendo normalizado em **Name** (por exemplo, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="ccb60-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="ccb60-110">(Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").</span><span class="sxs-lookup"><span data-stu-id="ccb60-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="ccb60-111">Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="ccb60-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="ccb60-112">**Dígitos inativos** (opcional) Especifique os dígitos ins elevadados dos números discados aos quais você deseja que o padrão seja semelhante.</span><span class="sxs-lookup"><span data-stu-id="ccb60-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="ccb60-113">Por exemplo, digite 425 se quiser que o padrão corresponder aos números discados começando com 425.</span><span class="sxs-lookup"><span data-stu-id="ccb60-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="ccb60-114">**Comprimento** Especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponder exatamente a esse tamanho, corresponder aos números discados que têm pelo menos esse tamanho ou corresponder aos números discados de qualquer tamanho.</span><span class="sxs-lookup"><span data-stu-id="ccb60-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="ccb60-115">**Dígitos a serem removidos** (Opcional) Especifique o número de dígitos inativos a serem removidos dos números discados que você deseja que o padrão corresponder.</span><span class="sxs-lookup"><span data-stu-id="ccb60-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="ccb60-116">**Dígitos a serem adicionados** (Opcional) Especifique os dígitos a serem adicionados aos números discados aos quais você deseja que o padrão seja semelhante.</span><span class="sxs-lookup"><span data-stu-id="ccb60-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="ccb60-117">Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="ccb60-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the Pattern **to match** is:</span><span class="sxs-lookup"><span data-stu-id="ccb60-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="ccb60-119">^(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="ccb60-119">^(\d{7})$</span></span>

6. <span data-ttu-id="ccb60-120">Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ccb60-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="ccb60-121">Um valor que representa o número de dígitos especificado no padrão de correspondência.</span><span class="sxs-lookup"><span data-stu-id="ccb60-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="ccb60-122">Por exemplo, se o padrão de correspondência for ^(\d )$ então$1 na regra de conversão representará números discados de {7} sete dígitos.</span><span class="sxs-lookup"><span data-stu-id="ccb60-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="ccb60-123">(Opcional) Digite um valor nos **Dígitos** para adicionar campo para especificar dígitos a serem anexados ao número convertido (por exemplo,+1425).</span><span class="sxs-lookup"><span data-stu-id="ccb60-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="ccb60-124">Por exemplo,  se Pattern para corresponder contiver^(\d )$ como padrão para números discados e a regra de conversão contiver +1425$1 como padrão para números de telefone {7} E.164, a regra normalizará de 5550100 a +14255550100. </span><span class="sxs-lookup"><span data-stu-id="ccb60-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="ccb60-125">(Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="ccb60-p104">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccb60-128">É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ccb60-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ccb60-129">Para obter detalhes, consulte [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="ccb60-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="ccb60-130">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="ccb60-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="ccb60-131">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="ccb60-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="ccb60-132">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccb60-133">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="ccb60-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ccb60-134">Para obter detalhes, [consulte Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="ccb60-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="ccb60-135">Para definir uma regra de normalização manualmente</span><span class="sxs-lookup"><span data-stu-id="ccb60-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="ccb60-136">Abrir o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ccb60-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="ccb60-137">(Opcional) Siga as etapas em [Criar ou modificar um plano de discagem no Skype for Business Server.](dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="ccb60-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="ccb60-138">In **New Normalization Rule** or Edit **Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="ccb60-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="ccb60-139">(Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="ccb60-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="ccb60-140">Em **Criar uma regra de normalização**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="ccb60-141">Digite o seguinte em **Digitar uma expressão regular**:</span><span class="sxs-lookup"><span data-stu-id="ccb60-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="ccb60-142">Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.</span><span class="sxs-lookup"><span data-stu-id="ccb60-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="ccb60-143">Em **Regra de tradução**, especifique um padrão para o formato dos números de telefone E.164 traduzidos.</span><span class="sxs-lookup"><span data-stu-id="ccb60-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="ccb60-144">Por exemplo, se você inserir ^(\d )$ em Corresponder a esse padrão {7} e+1425$1 na regra de conversão, a regra normalizará de 5550100 a +14255550100.  </span><span class="sxs-lookup"><span data-stu-id="ccb60-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="ccb60-145">(Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="ccb60-p107">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="ccb60-148">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="ccb60-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="ccb60-149">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="ccb60-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="ccb60-150">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="ccb60-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccb60-151">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="ccb60-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ccb60-152">Para obter detalhes, [consulte Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="ccb60-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


