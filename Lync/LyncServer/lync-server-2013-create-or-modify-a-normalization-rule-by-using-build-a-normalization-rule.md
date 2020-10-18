---
title: Criar ou modificar uma regra de normalização usando a criação de uma regra de normalização
description: Criar ou modificar uma regra de normalização usando compilar uma regra de normalização.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 824936359c070090ad4225a3ead6e8e46fe14785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574597"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="928ba-103">Criar ou modificar uma regra de normalização usando a criação de uma regra de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="928ba-103">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="928ba-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="928ba-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="928ba-105">Complete as etapas a seguir se quiser criar ou modificar uma regra de normalização no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="928ba-105">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="928ba-106">Como alternativa, se você quiser criar ou modificar uma regra de normalização manualmente, confira [criar ou modificar uma regra de normalização manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="928ba-106">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="928ba-107">Para definir uma regra usando Compilar uma Regra de Normalização</span><span class="sxs-lookup"><span data-stu-id="928ba-107">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="928ba-108">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="928ba-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="928ba-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="928ba-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="928ba-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="928ba-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="928ba-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="928ba-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="928ba-112">Opcion Siga as etapas em [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) até a etapa 11 ou [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) até a etapa 10.</span><span class="sxs-lookup"><span data-stu-id="928ba-112">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="928ba-113">Em **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="928ba-113">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="928ba-114">(Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").</span><span class="sxs-lookup"><span data-stu-id="928ba-114">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="928ba-115">Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="928ba-115">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="928ba-116">**Dígitos iniciais**     Opcion Especifique os dígitos à esquerda dos números discados que você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="928ba-116">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="928ba-117">Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.</span><span class="sxs-lookup"><span data-stu-id="928ba-117">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="928ba-118">**Comprimento**     Especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda exatamente a esse tamanho, coincidir números discados com pelo menos esse comprimento ou coincidir números discados de qualquer tamanho.</span><span class="sxs-lookup"><span data-stu-id="928ba-118">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="928ba-119">**Dígitos a serem removidos**     Opcion Especifique o número de dígitos iniciais a serem removidos dos números discados que você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="928ba-119">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="928ba-120">**Dígitos a serem adicionados**     Opcion Especifique os dígitos a serem adicionados aos números discados aos quais você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="928ba-120">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="928ba-p105">Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar **Dígitos iniciais** vazio, digite **7** no campo **Tamanho** e selecione **Exatamente** e especifique **0** em **Dígitos a serem removidos**, a expressão regular resultante em **Padrão a ser correspondido** será:</span><span class="sxs-lookup"><span data-stu-id="928ba-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="928ba-123">**^ ( \\ d {7} ) $**</span><span class="sxs-lookup"><span data-stu-id="928ba-123">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="928ba-124">Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="928ba-124">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="928ba-125">Um valor que representa o número de dígitos especificado no padrão de correspondência.</span><span class="sxs-lookup"><span data-stu-id="928ba-125">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="928ba-126">Por exemplo, se o padrão de correspondência for **^ ( \\ d {7} ) $** , **$1** na regra de conversão representa números discados de sete dígitos.</span><span class="sxs-lookup"><span data-stu-id="928ba-126">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="928ba-127">(Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).</span><span class="sxs-lookup"><span data-stu-id="928ba-127">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="928ba-128">Por exemplo, se o **padrão a ser correspondido** contiver **^ ( \\ d {7} ) $** como o padrão para números discados e a **regra de conversão** contém **+ 1425 $1** como o padrão para números de telefone e. 164, a regra normaliza 5550100 para + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="928ba-128">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="928ba-129">(Opcional) Se a regra de normalização resultar em um número de telefone interno em sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="928ba-129">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="928ba-p107">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="928ba-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="928ba-132">É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente.</span><span class="sxs-lookup"><span data-stu-id="928ba-132">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="928ba-133">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="928ba-133">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="928ba-134">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="928ba-134">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="928ba-135">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="928ba-135">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="928ba-136">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="928ba-136">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="928ba-137">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando <STRONG>Confirmar todos</STRONG> para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="928ba-137">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="928ba-138">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="928ba-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="928ba-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="928ba-139">See Also</span></span>


[<span data-ttu-id="928ba-140">Criar ou modificar uma regra de normalização manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="928ba-140">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="928ba-141">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="928ba-141">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="928ba-142">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="928ba-142">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="928ba-143">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="928ba-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="928ba-144">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="928ba-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

