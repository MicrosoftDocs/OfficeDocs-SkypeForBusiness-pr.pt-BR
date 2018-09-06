---
title: Criar ou modificar uma regra de conversão para apresentação da ID chamada no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumo: Saiba como definir uma regra de conversão usando a compilar uma ferramenta de regra de conversão no Skype para Business Server.'
ms.openlocfilehash: 768538f861ec3c020b02fc9df4498350f9c13a4b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246792"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="c4cbe-103">Criar ou modificar uma regra de conversão para apresentação da ID chamada no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c4cbe-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="c4cbe-104">**Resumo:** Saiba como definir uma regra de conversão usando a compilar uma ferramenta de regra de conversão no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="c4cbe-105">Se você deseja definir uma regra de conversão digitando um conjunto de valores na ferramenta **compilar uma regra de conversão** e habilitando Skype para painel de controle do Business Server gerar o padrão de correspondência correspondente e uma regra de conversão para você, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="c4cbe-106">Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="c4cbe-107">Para obter detalhes, consulte [criar ou modificar uma regra de conversão manualmente](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="c4cbe-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="c4cbe-108">Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão</span><span class="sxs-lookup"><span data-stu-id="c4cbe-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="c4cbe-109">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c4cbe-110">Para começar a definir uma regra de conversão, siga as etapas em [Configure um tronco com mídia ignorar no Skype para Business Server](configure-trunk-with-media-bypass.md) por meio da etapa 10 ou [Configure um tronco sem media bypass no Skype para Business Server](configure-trunk-without-media-bypass.md) até a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c4cbe-111">Em  **Nome** na página  **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c4cbe-112">(Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo US internacional de longa distância.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c4cbe-113">Na seção  **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c4cbe-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="c4cbe-p102">**Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, digite  + nesse campo para corresponder os números no formato E.164 (que começa com +).</span><span class="sxs-lookup"><span data-stu-id="c4cbe-p102">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match. For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="c4cbe-116">**Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="c4cbe-117">Por exemplo, insira 11 e selectAt mínimos na lista suspensa para corresponder os números que estão pelo menos 11 dígitos de comprimento.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="c4cbe-118">**Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="c4cbe-119">Por exemplo, digite 1 para retirar a + desde o início do número.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="c4cbe-p105">**Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite  011 se quiser que 011 seja anexado aos números convertidos quando a regra for aplicada.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-p105">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

    <span data-ttu-id="c4cbe-p106">Os valores inseridos nesses campos são refletidos nos campos  **Padrão a ser correspondido** e  **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo  **Padrão a ser correspondido** será:</span><span class="sxs-lookup"><span data-stu-id="c4cbe-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

    <span data-ttu-id="c4cbe-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="c4cbe-124">^\+(\d{9}\d+)$</span></span>

    <span data-ttu-id="c4cbe-p107">O campo  **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:</span><span class="sxs-lookup"><span data-stu-id="c4cbe-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>

   - <span data-ttu-id="c4cbe-127">Um valor (por exemplo, $1) que representa o número de dígitos no padrão correspondido</span><span class="sxs-lookup"><span data-stu-id="c4cbe-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="c4cbe-128">(Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**</span><span class="sxs-lookup"><span data-stu-id="c4cbe-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

    <span data-ttu-id="c4cbe-129">Usando os valores do exemplo anterior, 011$1 aparece no campo **Regra de conversão**.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

    <span data-ttu-id="c4cbe-130">Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="c4cbe-131">Clique em **OK** para salvar a regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="c4cbe-132">Clique em  **OK** para salvar a configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="c4cbe-133">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c4cbe-134">Sempre que criar ou modificar uma regra de conversão, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c4cbe-135">Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="c4cbe-136">Como definir uma regra de conversão manualmente</span><span class="sxs-lookup"><span data-stu-id="c4cbe-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="c4cbe-137">Abra o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c4cbe-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="c4cbe-138">Para começar a definir uma regra de conversão, siga as etapas em [Configure um tronco com mídia ignorar no Skype para Business Server](configure-trunk-with-media-bypass.md) por meio da etapa 10 ou [Configure um tronco sem media bypass no Skype para Business Server](configure-trunk-without-media-bypass.md) até a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c4cbe-139">No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c4cbe-140">(Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo longa distância internacional EUA discando.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c4cbe-141">Clique em  **Editar** na parte inferior da seção  **Compilar uma Regra de Conversão**.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="c4cbe-142">Digite o seguinte em  **Digitar uma expressão regular**:</span><span class="sxs-lookup"><span data-stu-id="c4cbe-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="c4cbe-143">No campo  **Corresponder a este padrão**, especifique o padrão que será usado para corresponder aos números a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="c4cbe-144">No campo  **Regra de conversão**, especifique o padrão para o formato dos números convertidos.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

    <span data-ttu-id="c4cbe-145">Por exemplo, se você inserir ^\+(\d{9}\d+)$ em **corresponder este padrão** and011$ 1 em **regra de conversão**, a regra converterá + 441235551010 em 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="c4cbe-146">Clique em  **OK** para salvar a regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="c4cbe-147">Clique em  **OK** para salvar a configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="c4cbe-148">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4cbe-149">Sempre que criar ou modificar uma regra de conversão, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c4cbe-150">Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="c4cbe-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4cbe-151">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c4cbe-151">See also</span></span>

[<span data-ttu-id="c4cbe-152">Configurar um tronco com bypass de mídia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c4cbe-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="c4cbe-153">Configurar um tronco sem bypass de mídia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c4cbe-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="c4cbe-154">Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="c4cbe-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="c4cbe-155">Implantar o bypass de mídia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c4cbe-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

