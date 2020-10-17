---
title: 'Lync Server 2013: modificar uma rota de voz'
description: 'Lync Server 2013: modificar uma rota de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa507f3d0f459dd200b9c772f3a330d7da36197
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546407"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="b61bd-103">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-103">Modify a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b61bd-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b61bd-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b61bd-105">Este tópico explica como editar uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="b61bd-105">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="b61bd-106">Para criar uma nova rota, confira [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b61bd-106">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="b61bd-107">Para modificar uma rota de voz</span><span class="sxs-lookup"><span data-stu-id="b61bd-107">To modify a voice route</span></span>

1.  <span data-ttu-id="b61bd-108">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b61bd-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b61bd-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b61bd-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b61bd-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b61bd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b61bd-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b61bd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b61bd-112">Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Rota**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-112">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="b61bd-113">Na página **Rota**, use um dos métodos a seguir par modificar uma rota de voz:</span><span class="sxs-lookup"><span data-stu-id="b61bd-113">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="b61bd-114">Clique no nome de uma rota de voz, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-114">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="b61bd-p104">Clique no nome de uma rota de voz, clique em **Editar**, **Copiar** e, em seguida, em **Colar**. Clique na nova cópia da rota de voz que você acabou de criar, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b61bd-117">No campo **Nome** na página **Editar Rota de Voz**, digite um nome descritivo para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="b61bd-117">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="b61bd-118">(Opcional) No campo **Descrição**, digite informações descritivas adicionais para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="b61bd-118">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="b61bd-119">Para especificar os padrões que você deseja acomodar com essa rota, use a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b61bd-119">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="b61bd-p105">Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:</span><span class="sxs-lookup"><span data-stu-id="b61bd-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="b61bd-122">**Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo a entrelinha +, se necessário).</span><span class="sxs-lookup"><span data-stu-id="b61bd-122">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="b61bd-123">Por exemplo, digite **+425** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-123">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="b61bd-124">Repita isso para cada valor de prefixo que você deseja incluir na rota.</span><span class="sxs-lookup"><span data-stu-id="b61bd-124">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="b61bd-125">**Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-125">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="b61bd-126">Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota.</span><span class="sxs-lookup"><span data-stu-id="b61bd-126">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="b61bd-127">Por exemplo, para excluir números que começam com + 425237 da rota, insira um valor de **+ 425237** no campo **exceções** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-127">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b61bd-128">Para definir manualmente o padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada.</span><span class="sxs-lookup"><span data-stu-id="b61bd-128">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="b61bd-129">Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" em [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="b61bd-129">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="b61bd-130">Selecione **suprimir ID de chamadas** se você não quiser que a ID do telefone que está fazendo a chamada de saída apareça para o destinatário da chamada.</span><span class="sxs-lookup"><span data-stu-id="b61bd-130">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="b61bd-131">Se você selecionar essa opção, especifique um **ID de chamadas alternativo** que aparecerá no display de ID da chamada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b61bd-131">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="b61bd-132">Para associar um ou mais troncos PSTN (rede telefônica pública comutada) à rota de voz, clique em **Adicionar**e selecione um tronco na lista.</span><span class="sxs-lookup"><span data-stu-id="b61bd-132">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b61bd-133">Se sua implantação incluir quaisquer servidores de mediação do Microsoft Office Communications Server 2007 R2, eles também estarão disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="b61bd-133">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="b61bd-134">Para associar um ou mais usos de PSTN à rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso de PSTN que foram definidos para sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b61bd-134">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b61bd-135">Para exibir as propriedades de cada um dos registros de uso de PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b61bd-135">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="b61bd-136">Para criar ou editar registros de uso de PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b61bd-136">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="b61bd-p110">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="b61bd-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b61bd-139">Ao contrário de uma política de voz onde a ordem na qual os registros de uso PSTN são listados é importante, a ordem dos registros de uso de PSTN em uma rota de voz é insignificante.</span><span class="sxs-lookup"><span data-stu-id="b61bd-139">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="b61bd-140">No entanto, recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="b61bd-140">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="b61bd-141">(O Lync Server percorre a lista de cima para baixo.)</span><span class="sxs-lookup"><span data-stu-id="b61bd-141">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="b61bd-p112">(Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.</span><span class="sxs-lookup"><span data-stu-id="b61bd-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b61bd-144">É possível salvar uma rota de voz que não passou ainda no teste e reconfigurá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="b61bd-144">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="b61bd-145">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b61bd-145">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="b61bd-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-146">Click **OK**.</span></span>

14. <span data-ttu-id="b61bd-147">Na página **Rota**, clique em **Confirmar** e em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="b61bd-147">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b61bd-148">Sempre que criar ou modificar uma rota de voz, você deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="b61bd-148">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b61bd-149">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="b61bd-149">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b61bd-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="b61bd-150">See Also</span></span>


[<span data-ttu-id="b61bd-151">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-151">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="b61bd-152">Exibir registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-152">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="b61bd-153">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-153">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="b61bd-154">Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-154">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="b61bd-155">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-155">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="b61bd-156">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b61bd-156">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

