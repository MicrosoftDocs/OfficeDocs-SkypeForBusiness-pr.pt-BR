---
title: 'Lync Server 2013: executar testes de roteamento de voz informais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="1f6fe-102">Executar testes de roteamento de voz informais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f6fe-103">_**Tópico da última modificação:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="1f6fe-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="1f6fe-104">Você pode usar a caixa de diálogo **criar informações do caso de teste de roteamento de voz** para executar testes informais antes de criar um caso de teste real.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="1f6fe-105">Quando você estiver satisfeito com o resultado de um teste, terá a opção de salvá-lo como um caso de teste formal.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="1f6fe-106">Para executar um teste de roteamento de voz informal</span><span class="sxs-lookup"><span data-stu-id="1f6fe-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="1f6fe-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1f6fe-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1f6fe-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1f6fe-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1f6fe-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1f6fe-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1f6fe-111">Na barra de navegação à esquerda, clique em **Roteamento de voz**e, em seguida, clique em **testar roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="1f6fe-112">Na página **testar roteamento de voz** , clique em **criar informações de caso de teste de roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="1f6fe-113">No campo **número discado** , digite o número de telefone que você deseja usar para este teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="1f6fe-114">Esse número será normalizado e exibido no campo **número normalizado** do painel de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="1f6fe-115">Na lista **plano** de discagem, selecione o plano de discagem a ser usado para testar o número discado.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="1f6fe-116">Padrão é o plano de discagem global.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="1f6fe-117">Quando você executar o teste, a primeira regra de normalização neste plano de discagem que corresponda ao número discado será exibida no campo **regra** de normalização do painel **resultados** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="1f6fe-118">Na lista **política de voz** , selecione a política de voz a ser usada para testar o número discado.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="1f6fe-119">Padrão é a política de voz global.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="1f6fe-120">Quando você executar o teste, o primeiro registro de uso PSTN coincidente nesta política de voz será exibido no **primeiro campo uso PSTN** do painel de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="1f6fe-121">Além disso, a primeira rota de voz correspondente que está associada a este registro de uso PSTN será exibida no primeiro campo de **rota** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="1f6fe-122">Adicionais Marque a caixa **de seleção popular do usuário** se desejar testar o número discado em relação à política de voz atribuída a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="1f6fe-123">Clique em **procurar** para exibir a caixa de diálogo **Selecionar usuários do Enterprise Voice** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="1f6fe-124">Clique em **Localizar** para exibir a lista de usuários que estão habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="1f6fe-125">Clique duas vezes no nome do usuário cuja política de voz atribuída você deseja usar para esse teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="1f6fe-126">O campo **política** agora está preenchido com a política de voz atribuída ao usuário selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="1f6fe-127">Quando você executar o teste, o primeiro registro de uso de rede telefônica pública comutada (PSTN) nessa política de voz será exibido no **primeiro campo uso PSTN** do painel de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="1f6fe-128">Além disso, a primeira rota de voz correspondente que está associada a este registro de uso PSTN será exibida no primeiro campo de **rota** .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="1f6fe-129">Clique em **executar** para executar o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="1f6fe-130">Os resultados são mostrados no painel direito da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="1f6fe-131">Adicionais Clique em **salvar como** se você quiser salvar essa configuração de teste como um caso de teste formal.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="1f6fe-132">No campo **nome** da caixa de diálogo **salvar informações do caso de teste de roteamento de voz** , digite um nome exclusivo para o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="1f6fe-133">O nome deve ser exclusivo entre todos os casos de teste de roteamento de voz na sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="1f6fe-134">Pode ter até 32 caracteres de comprimento e pode conter qualquer caractere alfanumérico, além da barra invertida (\\), ponto final (.) ou sublinhado (\_).</span><span class="sxs-lookup"><span data-stu-id="1f6fe-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="1f6fe-135">Observe que os campos restantes na caixa de diálogo **salvar informações do caso de teste de roteamento de voz** são somente leitura e são preenchidos com base na configuração *e* nos resultados informais do teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="1f6fe-136">Verifique se essa é a configuração que você deseja salvar para o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1f6fe-137">Os valores dos resultados do teste são usados para pré-popular campos na caixa de diálogo <STRONG>salvar informações do caso de teste de roteamento de voz</STRONG> da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1f6fe-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="1f6fe-138">A <STRONG>tradução esperada</STRONG> é preenchida previamente com o valor no campo <STRONG>número normalizado</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="1f6fe-139">A <STRONG>rota esperada</STRONG> é preenchida previamente com o valor no <STRONG>primeiro campo Route</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="1f6fe-140">O <STRONG>registro de uso de PSTN esperado</STRONG> é preenchido com o valor no primeiro campo de <STRONG>uso de PSTN</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="1f6fe-141">Se as correspondências para qualquer um desses valores não forem encontradas durante a execução do teste, o campo correspondente estará vazio na caixa de diálogo <STRONG>salvar informações do caso de teste de roteamento de voz</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f6fe-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="1f6fe-142">Clique em **OK** para salvar o caso de teste ou clique em **Cancelar** para retornar para retornar à caixa de diálogo **Exibir informações do caso de teste de roteamento de voz** para desenvolver ainda mais o teste antes de salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="1f6fe-143">Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f6fe-144">Sempre que criar um caso de teste de roteamento de voz, você deve executar o comando <STRONG>Commit All</STRONG> para publicar o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="1f6fe-145">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="1f6fe-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f6fe-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f6fe-146">See Also</span></span>


[<span data-ttu-id="1f6fe-147">Criar um caso de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="1f6fe-148">Executar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="1f6fe-149">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="1f6fe-150">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="1f6fe-151">Configurando planos de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="1f6fe-152">Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6fe-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

