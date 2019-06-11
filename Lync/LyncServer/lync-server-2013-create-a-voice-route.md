---
title: 'Lync Server 2013: criar uma rota de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="34b98-102">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34b98-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="34b98-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="34b98-104">O procedimento a seguir explica como criar uma nova rota de voz usando o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34b98-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="34b98-105">Para editar uma rota existente, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md) para obter o procedimento.</span><span class="sxs-lookup"><span data-stu-id="34b98-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="34b98-106">Para criar uma rota de voz usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="34b98-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="34b98-107">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="34b98-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="34b98-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34b98-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34b98-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="34b98-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34b98-110">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="34b98-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="34b98-111">Clique em **Rota**.</span><span class="sxs-lookup"><span data-stu-id="34b98-111">Click **Route**.</span></span>

5.  <span data-ttu-id="34b98-112">Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.</span><span class="sxs-lookup"><span data-stu-id="34b98-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="34b98-113">No campo **Nome**, digite o nome descritivo da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="34b98-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="34b98-114">(Opcional) Em **Descrição**, digite outras informações descritivas para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="34b98-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="34b98-115">Para especificar os padrões que você deseja acomodar com essa rota, é possível usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.</span><span class="sxs-lookup"><span data-stu-id="34b98-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="34b98-p103">Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:</span><span class="sxs-lookup"><span data-stu-id="34b98-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="34b98-118">**Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo o + + se necessário).</span><span class="sxs-lookup"><span data-stu-id="34b98-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="34b98-119">Por exemplo, digite **+425** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="34b98-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="34b98-120">Repita este procedimento para cada valor de prefixo que deseja incluir na rota.</span><span class="sxs-lookup"><span data-stu-id="34b98-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="34b98-121">**Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**.</span><span class="sxs-lookup"><span data-stu-id="34b98-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="34b98-122">Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota.</span><span class="sxs-lookup"><span data-stu-id="34b98-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="34b98-123">Por exemplo, para excluir números que começam com +425237 da rota, digite um valor de **+425237** no campo **Exceções** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34b98-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="34b98-124">Para definir manualmente um padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada.</span><span class="sxs-lookup"><span data-stu-id="34b98-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="34b98-125">Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)em.</span><span class="sxs-lookup"><span data-stu-id="34b98-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="34b98-p107">Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, especifique um **ID de chamadas alternativo** que aparecerá no display de ID da chamada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="34b98-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="34b98-128">Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco SIP ou gateway na lista.</span><span class="sxs-lookup"><span data-stu-id="34b98-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34b98-129">Se sua implantação inclui qualquer servidor de mediação do Microsoft Office Communications Server 2007 R2, ele também estará disponível na lista.</span><span class="sxs-lookup"><span data-stu-id="34b98-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="34b98-130">Para associar um ou mais usos de PSTN (rede telefônica pública comutada) com a rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso PSTN definidos para a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="34b98-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34b98-131">Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">exibir registros de uso PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="34b98-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="34b98-132">Para criar ou editar registros de uso PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="34b98-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="34b98-p108">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="34b98-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34b98-135">Em contraste à política de voz, onde a ordem no qual os registros de uso PSTN estão listados é importante, a ordem na qual os registros de uso PSTN estão listados na rota de voz é insignificante.</span><span class="sxs-lookup"><span data-stu-id="34b98-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="34b98-136">No entanto, recomendamos organizar a lista por frequência de uso.</span><span class="sxs-lookup"><span data-stu-id="34b98-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="34b98-137">Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="34b98-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="34b98-138">(O Lync Server percorre a lista de cima para baixo.)</span><span class="sxs-lookup"><span data-stu-id="34b98-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="34b98-p110">(Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.</span><span class="sxs-lookup"><span data-stu-id="34b98-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34b98-141">Você pode salvar uma rota de voz que ainda não passou no teste e, em seguida, reconfigurá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="34b98-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="34b98-142">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="34b98-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="34b98-143">Clique em **OK** para salvar a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="34b98-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="34b98-144">Sempre que você criar uma rota de voz, deverá executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração da configuração.</span><span class="sxs-lookup"><span data-stu-id="34b98-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="34b98-145">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="34b98-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34b98-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="34b98-146">See Also</span></span>


[<span data-ttu-id="34b98-147">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="34b98-148">Exibir registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="34b98-149">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="34b98-150">Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="34b98-151">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="34b98-152">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34b98-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

