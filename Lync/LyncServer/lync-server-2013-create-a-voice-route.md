---
title: 'Lync Server 2013: criar uma rota de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f51c1df7807d30d2c8c97882db638febc78e78ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="25d65-102">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25d65-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="25d65-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="25d65-104">O procedimento a seguir explica como criar uma nova rota de voz usando o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25d65-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="25d65-105">Para editar uma rota existente, confira [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md) para o procedimento.</span><span class="sxs-lookup"><span data-stu-id="25d65-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="25d65-106">Para criar uma rota de voz usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="25d65-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="25d65-107">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="25d65-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="25d65-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25d65-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25d65-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="25d65-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25d65-110">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="25d65-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="25d65-111">Clique em **Rota**.</span><span class="sxs-lookup"><span data-stu-id="25d65-111">Click **Route**.</span></span>

5.  <span data-ttu-id="25d65-112">Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.</span><span class="sxs-lookup"><span data-stu-id="25d65-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="25d65-113">Em **nome**, digite um nome descritivo para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="25d65-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="25d65-114">Opcion Em **Descrição**, digite informações descritivas adicionais para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="25d65-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="25d65-115">Para especificar os padrões que você deseja que essa rota acomode, você pode usar a ferramenta **criar um padrão de correspondência** para gerar uma expressão regular ou gravar a expressão regular manualmente.</span><span class="sxs-lookup"><span data-stu-id="25d65-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="25d65-p103">Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:</span><span class="sxs-lookup"><span data-stu-id="25d65-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="25d65-118">**Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo a entrelinha +, se necessário).</span><span class="sxs-lookup"><span data-stu-id="25d65-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="25d65-119">Por exemplo, digite **+ 425**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="25d65-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="25d65-120">Repita isso para cada valor de prefixo que você deseja incluir na rota.</span><span class="sxs-lookup"><span data-stu-id="25d65-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="25d65-121">**Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**.</span><span class="sxs-lookup"><span data-stu-id="25d65-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="25d65-122">Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota.</span><span class="sxs-lookup"><span data-stu-id="25d65-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="25d65-123">Por exemplo, para excluir números que começam com + 425237 da rota, insira um valor de **+ 425237** no campo **exceções** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25d65-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="25d65-124">Para definir manualmente o padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada.</span><span class="sxs-lookup"><span data-stu-id="25d65-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="25d65-125">Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)em.</span><span class="sxs-lookup"><span data-stu-id="25d65-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="25d65-p107">Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, especifique um **ID de chamadas alternativo** que aparecerá no display de ID da chamada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="25d65-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="25d65-128">Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco na lista.</span><span class="sxs-lookup"><span data-stu-id="25d65-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25d65-129">Se sua implantação incluir quaisquer servidores de mediação do Microsoft Office Communications Server 2007 R2, eles também estarão disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="25d65-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="25d65-130">Para associar um ou mais usos de PSTN (rede telefônica pública comutada) à rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso de PSTN que foram definidos para sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="25d65-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25d65-131">Para exibir as propriedades de cada um dos registros de uso de PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25d65-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="25d65-132">Para criar ou editar registros de uso de PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25d65-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="25d65-p108">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="25d65-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25d65-135">Ao contrário de uma política de voz, onde a ordem na qual os registros de uso PSTN são listados é importante, a ordem na qual os registros de uso PSTN são listados na rota de voz é insignificante.</span><span class="sxs-lookup"><span data-stu-id="25d65-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="25d65-136">No entanto, recomendamos que você organize a lista por frequência de uso.</span><span class="sxs-lookup"><span data-stu-id="25d65-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="25d65-137">Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="25d65-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="25d65-138">(O Lync Server percorre a lista de cima para baixo.)</span><span class="sxs-lookup"><span data-stu-id="25d65-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="25d65-p110">(Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.</span><span class="sxs-lookup"><span data-stu-id="25d65-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25d65-141">É possível salvar uma rota de voz que não passou ainda no teste e reconfigurá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="25d65-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="25d65-142">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25d65-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="25d65-143">Clique em **OK** para salvar a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="25d65-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25d65-144">Sempre que você cria uma rota de voz, deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="25d65-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="25d65-145">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25d65-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25d65-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="25d65-146">See Also</span></span>


[<span data-ttu-id="25d65-147">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="25d65-148">Exibir registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="25d65-149">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="25d65-150">Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="25d65-151">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="25d65-152">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d65-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

