---
title: 'Lync Server 2013: Modificar um plano de discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd6cc46d6e3317ca678b20e86c546db7dcc94fcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="c1b7a-102">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1b7a-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1b7a-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c1b7a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c1b7a-104">Para modificar um plano de discagem existente, siga as etapas do procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="c1b7a-105">Se você quiser criar um novo plano de discagem, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="c1b7a-106">Para modificar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="c1b7a-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="c1b7a-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c1b7a-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c1b7a-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1b7a-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1b7a-111">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em  **Plano de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="c1b7a-112">Na página **Plano de Discagem**, dê um duplo clique no nome de um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1b7a-p104">O escopo e o nome do plano de discagem foram definidos quando o plano de discagem foi criado. Eles não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="c1b7a-115">(Opcional) Em **Editar Plano de Discagem**, edite o campo **Nome simples**, que é pré-preenchido com o mesmo nome que aparece no campo  **Nome** para especificar um nome mais descritivo que reflita o site, serviço ou usuário para o qual o plano de discagem se aplica.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1b7a-116">O <STRONG>nome simples</STRONG> deve ser exclusivo entre todos os planos de discagem na implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="c1b7a-117">Ele não pode exceder 256 caracteres Unicode, e cada um deles pode ser um caractere alfabético ou numérico, um hífen (-), um ponto (.), um sinal de adição (+) ou um sublinhado (_).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="c1b7a-118">Espaços não são permitidos no campo <STRONG>Nome simples</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="c1b7a-119">(Opcional) No campo **Descrição**, digite informações descritivas sobre o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="c1b7a-p106">(Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1b7a-122">As regiões de conferência d discagem são necessárias para associar números de acesso de conferência discada a um ou mais planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="c1b7a-123">(Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se usuários precisarem discar um ou mais dígitos primeiro para obter uma linha externa (por exemplo, 9).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="c1b7a-124">Você pode digitar um valor de prefixo de até quatro caracteres (ou seja, \# \*,, e 0-9).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1b7a-125">Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="c1b7a-126">Associe e configure regras de normalização para o plano de discagem:</span><span class="sxs-lookup"><span data-stu-id="c1b7a-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="c1b7a-127">Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="c1b7a-128">Na caixa de diálogo **Selecionar Regras de Normalização**, destaque as regras que deseja associar ao plano de discagem e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="c1b7a-129">Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="c1b7a-130">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="c1b7a-131">Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="c1b7a-132">Para obter detalhes sobre a edição da regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="c1b7a-133">Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="c1b7a-134">Para obter detalhes sobre como editar a cópia, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7a-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="c1b7a-135">Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1b7a-136">Cada plano de discagem deve ter no mínimo uma regra de normalização associada.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="c1b7a-137">Para obter detalhes sobre como determinar todas as regras de normalização que um plano de discagem requer, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="c1b7a-p113">Verifique se as regras de normalização do plano de discagem estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1b7a-140">O Lync Server percorre a lista de regras de normalização da parte superior para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="c1b7a-141">Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="c1b7a-142">O padrão <STRONG>manter toda</STRONG> a regra de normalização <STRONG>^{11}(\d) $</STRONG> corresponde a qualquer número de 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="c1b7a-143">Se, por exemplo, você adicionar uma regra de normalização que corresponda a números de 11 dígitos que comecem com o 1425, certifique-se de que a opção <STRONG>manter tudo</STRONG> esteja classificada abaixo da regra <STRONG>^ (1425 \{7}d)</STRONG> mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="c1b7a-p116">(Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em  **Ir**. Os resultados do teste são exibidos em  **Insira um número de teste**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1b7a-146">É possível salvar um plano de discagem que não passou ainda no teste e reconfigurá-lo mais tarde.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="c1b7a-147">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="c1b7a-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-148">Click **OK**.</span></span>

13. <span data-ttu-id="c1b7a-149">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1b7a-150">Sempre que criar ou modificar um plano de discagem, você deve executar o comando  <STRONG>Confirmar tudo</STRONG> para publicar as alterações de configuração.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c1b7a-151">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1b7a-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="c1b7a-152">See Also</span></span>


[<span data-ttu-id="c1b7a-153">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1b7a-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="c1b7a-154">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1b7a-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="c1b7a-155">Definindo regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1b7a-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

