---
title: 'Lync Server 2013: modificar uma rota de voz'
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
ms.openlocfilehash: c0731383eea99e7510ef1748777e7139e2d9f369
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="9e35b-102">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e35b-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9e35b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9e35b-104">Este tópico explica como editar uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="9e35b-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="9e35b-105">Para criar uma nova rota, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9e35b-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="9e35b-106">Para modificar uma rota de voz</span><span class="sxs-lookup"><span data-stu-id="9e35b-106">To modify a voice route</span></span>

1.  <span data-ttu-id="9e35b-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9e35b-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9e35b-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9e35b-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9e35b-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e35b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9e35b-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9e35b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9e35b-111">Na barra de navegação à esquerda, clique em **Roteamento de Voz** e, em seguida, clique em **Rota**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="9e35b-112">Na página **Rota**, use um dos métodos a seguir para modificar uma rota de voz:</span><span class="sxs-lookup"><span data-stu-id="9e35b-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="9e35b-113">Clique no nome de uma rota de voz, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="9e35b-p104">Clique no nome de uma rota de voz, clique em **Editar**, **Copiar** e, em seguida, em **Colar**. Clique na nova cópia da rota de voz que você acabou de criar, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9e35b-116">No campo **Nome** na página **Editar Rota de Voz**, digite um nome descritivo para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="9e35b-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="9e35b-117">(Opcional) No campo **Descrição**, digite informações descritivas adicionais para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="9e35b-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="9e35b-118">Para especificar os padrões a serem acomodados por esta rota, você pode usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou a escreva manualmente.</span><span class="sxs-lookup"><span data-stu-id="9e35b-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="9e35b-p105">Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:</span><span class="sxs-lookup"><span data-stu-id="9e35b-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="9e35b-121">**Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo o + + se necessário).</span><span class="sxs-lookup"><span data-stu-id="9e35b-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="9e35b-122">Por exemplo, digite **+425** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="9e35b-123">Repita este procedimento para cada valor de prefixo que deseja incluir na rota.</span><span class="sxs-lookup"><span data-stu-id="9e35b-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="9e35b-124">**Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="9e35b-125">Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota.</span><span class="sxs-lookup"><span data-stu-id="9e35b-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="9e35b-126">Por exemplo, para excluir números que começam com +425237 da rota, digite um valor de **+425237** no campo **Exceções** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="9e35b-127">Para definir manualmente um padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada.</span><span class="sxs-lookup"><span data-stu-id="9e35b-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="9e35b-128">Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)em.</span><span class="sxs-lookup"><span data-stu-id="9e35b-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="9e35b-p109">Selecione **Suprimir ID de chamadas** se não deseja que a ID do telefone que faz a chamada de saída apareça para o destinatário da chamada. Se você selecionar essa opção, é necessário especificar uma **ID de chamada alternativa** que aparecerá na tela do ID de chamada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="9e35b-p109">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="9e35b-131">Para associar um ou mais troncos PSTN À rota de voz, clique em **Adicionar** e selecione um tronco da lista.</span><span class="sxs-lookup"><span data-stu-id="9e35b-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e35b-132">Se sua implantação inclui qualquer servidor de mediação do Microsoft Office Communications Server 2007 R2, ele também estará disponível na lista.</span><span class="sxs-lookup"><span data-stu-id="9e35b-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="9e35b-133">Para associar um ou mais usos de PSTN à rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso PSTN definidos para a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9e35b-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e35b-134">Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">exibir registros de uso PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e35b-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="9e35b-135">Para criar ou editar registros de uso PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e35b-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="9e35b-p110">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="9e35b-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e35b-138">Contrastando com a política de voz, em que a ordem em que os registros de uso do PSTN são listados é importante, a ordem dos registros de uso do PSTN em uma rota de voz é insignificante.</span><span class="sxs-lookup"><span data-stu-id="9e35b-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="9e35b-139">No entanto, é recomendável organizar a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="9e35b-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="9e35b-140">(O Lync Server percorre a lista de cima para baixo.)</span><span class="sxs-lookup"><span data-stu-id="9e35b-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="9e35b-p112">(Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.</span><span class="sxs-lookup"><span data-stu-id="9e35b-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e35b-143">Você pode salvar uma rota de voz que ainda não passou no teste e, em seguida, reconfigurá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="9e35b-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="9e35b-144">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e35b-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="9e35b-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-145">Click **OK**.</span></span>

14. <span data-ttu-id="9e35b-146">Na página **Rota**, clique em **Confirmar** e em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="9e35b-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e35b-147">Toda vez que criar ou modificar uma rota de voz, você deve executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="9e35b-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="9e35b-148">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="9e35b-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e35b-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="9e35b-149">See Also</span></span>


[<span data-ttu-id="9e35b-150">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="9e35b-151">Exibir registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="9e35b-152">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="9e35b-153">Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="9e35b-154">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="9e35b-155">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e35b-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

