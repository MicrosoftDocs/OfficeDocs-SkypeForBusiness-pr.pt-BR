---
title: Criar ou modificar uma regra de normalização no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: saiba como definir, criar e modificar uma regra de normalização no Skype for Business Server.'
ms.openlocfilehash: c206bd20c02053f4e3775f32b1ba61000bb59a63
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767084"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="cf9b1-103">Criar ou modificar uma regra de normalização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cf9b1-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="cf9b1-104">**Resumo:** Saiba como definir, criar e modificar uma regra de normalização no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="cf9b1-105">Definir, criar e modificar regras de normalização no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="cf9b1-106">Para definir uma regra de normalização usando Compilar uma Regra de Normalização</span><span class="sxs-lookup"><span data-stu-id="cf9b1-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="cf9b1-107">Abrir o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cf9b1-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cf9b1-108">Adicionais Siga as etapas em [criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md) por meio da etapa 11 ou [modificar um plano de discagem](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) por meio da etapa 10.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="cf9b1-109">Em **nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreva o padrão de número que está normalizado em **nome** (por exemplo, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="cf9b1-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="cf9b1-110">(Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").</span><span class="sxs-lookup"><span data-stu-id="cf9b1-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cf9b1-111">Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf9b1-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="cf9b1-112">**Dígitos iniciais** (opcional) especifique os dígitos à esquerda dos números discados para os quais você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="cf9b1-113">Por exemplo, type425 se quiser que o padrão corresponda a números discados começando com 425.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="cf9b1-114">**Comprimento** Especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda exatamente a esse comprimento, corresponda aos números discados que tenham pelo menos esse comprimento ou coincidam com os números discados de qualquer comprimento.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="cf9b1-115">**Dígitos a serem** removidos (opcional) especifique o número de dígitos iniciais a serem removidos dos números discados que você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="cf9b1-116">**Dígitos para adicionar** (opcional) especifique os dígitos a serem adicionados aos números discados para os quais você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="cf9b1-117">Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="cf9b1-118">Por exemplo, se você deixar os **dígitos iniciais** vazios, type7 no campo **comprimento** e selecionar **exatamente**e especificar 0 em **dígitos a remover**, a expressão regular resultante no **padrão a ser CORRESP** será:</span><span class="sxs-lookup"><span data-stu-id="cf9b1-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="cf9b1-119">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cf9b1-119">^(\d{7})$</span></span>

6. <span data-ttu-id="cf9b1-120">Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cf9b1-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="cf9b1-121">Um valor que representa o número de dígitos especificado no padrão de correspondência.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="cf9b1-122">Por exemplo, se o padrão correspondente for ^ (\d{7}) $, então $1 na regra de tradução representará os números discados de 7 dígitos.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="cf9b1-123">Adicionais Digite um valor no campo **dígitos para adicionar** para especificar os dígitos a serem anexados ao número traduzido (por exemplo, + 1425).</span><span class="sxs-lookup"><span data-stu-id="cf9b1-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="cf9b1-124">Por exemplo, se **a correspondência de padrão** contiver ^{7}(\d) $ como o padrão para números discados e **regra de tradução** contém + 1425 $1 como o padrão para os números de telefone e. 164, a regra normaliza o 5550100 para + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cf9b1-125">(Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cf9b1-p104">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf9b1-p105">É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte  [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf9b1-p105">You can save a normalization rule that does not yet pass the test and then reconfigure it later. For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="cf9b1-130">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cf9b1-131">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cf9b1-132">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf9b1-133">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cf9b1-134">Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="cf9b1-135">Para definir uma regra de normalização manualmente</span><span class="sxs-lookup"><span data-stu-id="cf9b1-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="cf9b1-136">Abrir o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cf9b1-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cf9b1-137">Adicionais Siga as etapas em [criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cf9b1-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="cf9b1-138">Em **nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreva o padrão de número que está normalizado em **nome** (por exemplo, nomeie a normalização rule5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="cf9b1-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="cf9b1-139">(Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="cf9b1-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cf9b1-140">Em **Compilar uma regra de normalização**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="cf9b1-141">Digite o seguinte em **Digitar uma expressão regular**:</span><span class="sxs-lookup"><span data-stu-id="cf9b1-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="cf9b1-142">Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="cf9b1-143">Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="cf9b1-144">Por exemplo, se você inserir ^ (\d{7}) $ em **coincidir este padrão** e + 1425 $1 na **regra de tradução**, a regra normalizará 5550100 para + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cf9b1-145">(Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cf9b1-p107">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="cf9b1-148">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cf9b1-149">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cf9b1-150">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf9b1-151">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando **Confirmar todos** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cf9b1-152">Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="cf9b1-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


