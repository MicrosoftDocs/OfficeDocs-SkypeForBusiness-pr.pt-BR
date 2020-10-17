---
title: 'Lync Server 2013: criar um plano de discagem'
description: 'Lync Server 2013: criar um plano de discagem.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9d72ad198df41e90ca2d629f9d1d421be187c9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542187"
---
# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="f44ad-103">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44ad-103">Create a dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f44ad-104">_**Última modificação do tópico:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="f44ad-104">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="f44ad-105">Para criar um novo plano de discagem, execute as etapas do procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="f44ad-105">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="f44ad-106">Se quiser editar um plano de discagem, confira [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="f44ad-106">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="f44ad-107">Para criar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="f44ad-107">To create a dial plan</span></span>

1.  <span data-ttu-id="f44ad-108">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f44ad-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f44ad-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f44ad-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f44ad-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f44ad-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f44ad-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f44ad-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f44ad-112">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Plano de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-112">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="f44ad-113">Na página **Plano de Discagem**, clique em **Novo** e selecione um escopo para o plano de discagem:</span><span class="sxs-lookup"><span data-stu-id="f44ad-113">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="f44ad-p104">**Plano de discagem do Site** se aplica a todo um site, exceto quaisquer usuários ou grupos que recebem um plano de discagem de usuário. Se você selecionar **Site** para o escopo de um plano de discagem, deverá escolher o site na caixa de diálogo **Selecionar um Site**. Se já houver um plano de discagem para um site, o site não aparecerá na caixa de diálogo **Selecionar um Site**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="f44ad-p105">**Plano de discagem do pool** pode se aplicar a um gateway de PSTN (Rede Telefônica Pública Comutada) ou um registrador. Se você selecionar **Pool** para o escopo de um plano de discagem, escolha o gateway PSTN ou registrador na caixa de diálogo **Selecionar um Serviço**. Se um plano de discagem já tiver sido criado para um serviço (gateway PSTN ou registrador), o serviço não aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="f44ad-120">**Plano de discagem do usuário** pode ser aplicado a usuários ou grupos especificados.</span><span class="sxs-lookup"><span data-stu-id="f44ad-120">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-121">Depois de selecionar o escopo do plano de discagem, não é possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="f44ad-121">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="f44ad-p106">Se você estiver criando um plano de discagem do usuário, insira um nome descritivo no campo **Nome** na caixa de diálogo **Novo Plano de Discagem**. Após o nome ser salvo, não será possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-124">Para planos de discagem do site, o campo <STRONG>Nome</STRONG> é pré-preenchido com o nome do site e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f44ad-124">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="f44ad-125">Para planos de discagem do pool, o campo <STRONG>Nome</STRONG> é pré-preenchido com o gateway PSTN ou o nome do registrador e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f44ad-125">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="f44ad-p107">O campo **Nome simples** é pré-preenchido com o mesmo nome que aparece no campo **Nome**. Como opção, é possível editar esse campo para especificar um nome mais descritivo que reflete o site, o serviço ou o usuário ao qual o plano de discagem se aplica.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f44ad-128">O <STRONG>nome simples</STRONG> deve ser exclusivo entre todos os planos de discagem na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f44ad-128">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="f44ad-129">Não pode exceder 256 caracteres Unicode, cada um deles pode ser um caractere alfabético ou numérico, um hífen (-), um ponto (.) ou um sublinhado (_).</span><span class="sxs-lookup"><span data-stu-id="f44ad-129">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="f44ad-130">Caracteres <STRONG>não suportados</STRONG> incluem espaços e caracteres reservados, conforme definido no RFC 3966 ( http://www.ietf.org/rfc/rfc3966.txt) .</span><span class="sxs-lookup"><span data-stu-id="f44ad-130">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="f44ad-131">Os caracteres reservados que <STRONG>não têm suporte</STRONG> no <STRONG>nome simples</STRONG> incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f44ad-131">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="f44ad-132">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="f44ad-132">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="f44ad-133">(Opcional) No campo **Descrição**, você pode digitar informações descritivas adicionais sobre o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="f44ad-133">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="f44ad-p110">(Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-136">As regiões de conferência d discagem são necessárias para associar números de acesso de conferência de discagem a um ou mais planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="f44ad-136">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="f44ad-137">(Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se os usuários precisarem discar um ou mais dígitos iniciais adicionais (por exemplo, 9) para obter uma linha externa.</span><span class="sxs-lookup"><span data-stu-id="f44ad-137">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="f44ad-138">Você pode digitar um valor de prefixo de até quatro caracteres ( \# , \* e 0-9).</span><span class="sxs-lookup"><span data-stu-id="f44ad-138">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-139">Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.</span><span class="sxs-lookup"><span data-stu-id="f44ad-139">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="f44ad-140">Associe e configure as regras de normalização para o plano de discagem da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f44ad-140">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="f44ad-141">Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-141">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f44ad-142">Em **Selecionar as Regras de Normalização**, realce as regras que você deseja associar ao plano de discagem e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-142">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="f44ad-143">Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-143">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="f44ad-144">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f44ad-144">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="f44ad-145">Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-145">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="f44ad-146">Para obter detalhes sobre a edição da regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f44ad-146">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="f44ad-147">Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-147">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="f44ad-148">Para obter detalhes sobre como editar a cópia, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f44ad-148">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="f44ad-149">Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-149">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-150">Cada plano de discagem precisa ter pelo menos uma regra de normalização associada.</span><span class="sxs-lookup"><span data-stu-id="f44ad-150">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="f44ad-151">Para obter informações sobre como determinar todas as regras de normalização exigidas por um plano de discagem, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial Plans and Normalization Rules in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f44ad-151">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="f44ad-p117">Verifique se as regras de normalização do plano de discagem são organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f44ad-154">O Lync Server percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="f44ad-154">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="f44ad-155">Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="f44ad-155">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="f44ad-156">O padrão <STRONG>manter todas as</STRONG> regras de normalização <STRONG>^ (\d {11} ) $</STRONG> corresponde a qualquer número de 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="f44ad-156">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="f44ad-157">Por exemplo, se você adicionar uma regra de normalização que corresponda a números de 11 dígitos que começam com 1425, certifique-se de que <STRONG>manter todos</STRONG> esteja classificado abaixo da regra <STRONG>^ (1425 \ d {7} ) $</STRONG> mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="f44ad-157">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="f44ad-p120">(Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em   \*\*Ir \*\*. Os resultados do teste são exibidos em   \*\*Insira um número de teste \*\*.</span><span class="sxs-lookup"><span data-stu-id="f44ad-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-160">É possível salvar um plano de discagem que não passou ainda no teste e reconfigurá-lo mais tarde.</span><span class="sxs-lookup"><span data-stu-id="f44ad-160">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="f44ad-161">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f44ad-161">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="f44ad-162">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-162">Click **OK**.</span></span>

14. <span data-ttu-id="f44ad-163">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="f44ad-163">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f44ad-164">Sempre que você criar um plano de discagem, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="f44ad-164">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f44ad-165">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="f44ad-165">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f44ad-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="f44ad-166">See Also</span></span>


[<span data-ttu-id="f44ad-167">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44ad-167">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="f44ad-168">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44ad-168">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="f44ad-169">Definindo regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44ad-169">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

