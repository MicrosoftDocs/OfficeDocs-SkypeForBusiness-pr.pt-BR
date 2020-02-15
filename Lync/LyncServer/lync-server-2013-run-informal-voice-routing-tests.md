---
title: 'Lync Server 2013: executar testes de roteamento de voz informais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8edac9a9bd955165a2e20197fd340ea80c2e27a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="fef20-102">Executar testes de roteamento de voz informais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef20-103">_**Última modificação do tópico:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="fef20-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="fef20-p101">É possível usar a caixa de diálogo **Criar informações de caso de teste de roteamento de voz** para executar testes informais antes de criar um caso de teste real. Quando você estiver satisfeito com o resultado do teste, terá a opção de salvá-lo como um caso de teste formal.</span><span class="sxs-lookup"><span data-stu-id="fef20-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="fef20-106">Para executar um teste de roteamento de voz informal</span><span class="sxs-lookup"><span data-stu-id="fef20-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="fef20-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fef20-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="fef20-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fef20-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="fef20-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fef20-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fef20-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fef20-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fef20-111">Na barra de navegação esquerda, clique em **Roteamento de Voz** e então clique em **Testar Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="fef20-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="fef20-112">Na página **Testar Roteamento de Voz**, clique em **Criar informações do caso de teste de roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="fef20-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="fef20-p104">No campo **Número discado**, digite o número de telefone que você deseja usar para este teste. Esse número será normalizado e exibido no campo **Número normalizado** do painel **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="fef20-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="fef20-p105">Na lista **Plano de discagem**, selecione o plano de discagem a ser usado para testar o número discado. O padrão é o plano de discagem Padrão.</span><span class="sxs-lookup"><span data-stu-id="fef20-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="fef20-117">Ao executar o teste, a primeira regra de normalização nesse plano de discagem que corresponde ao número discado será exibido no campo **Regra de normalização** do painel **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="fef20-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="fef20-p106">Na lista **Política de Voz**, selecione a política de voz a ser usada para testar o número discado. O padrão é a política de voz Global.</span><span class="sxs-lookup"><span data-stu-id="fef20-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="fef20-p107">Ao executar o teste, o primeiro registro de uso de PSTN correspondente nessa política de voz será exibido no campo **Primeiro uso do PSTN** no painel **Resultados**. Além disso, a primeira rota de voz correspondente associada ao registro de uso desse PSTN será exibida no campo **Primeira rota**.</span><span class="sxs-lookup"><span data-stu-id="fef20-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="fef20-122">(Opcional) Marque a caixa de seleção **Popular no usuário** se você quiser testar o número discado com base na política de voz atribuída a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="fef20-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="fef20-123">Clique em **Procurar** para exibir a caixa de seleção **Selecionar os Usuários do Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="fef20-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="fef20-124">Clique em **Localizar** para exibir a lista de usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fef20-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="fef20-p108">Clique duas vezes no nome do usuário cuja política de voz atribuída você deseja usar para este teste. O campo **Política** agora está preenchido com a política de voz atribuída ao usuário selecionado.</span><span class="sxs-lookup"><span data-stu-id="fef20-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="fef20-p109">Quando você executa o teste, o primeiro registro de uso de PSTN (Rede Telefônica Pública Comutada) correspondente nesta política de voz será exibido no campo **Primeiro uso do PSTN** do painel **Resultados**. Além disso, a primeira rota de voz correspondente associada ao registro de uso do PSTN será exibida no campo **Primeira rota**.</span><span class="sxs-lookup"><span data-stu-id="fef20-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="fef20-p110">Clique em **Executar** para executar o caso de teste. Os resultados são exibidos no painel direito da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fef20-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="fef20-131">(Opcional) Clique em **Salvar como** se você quiser salvar esta configuração de teste como um caso de teste formal.</span><span class="sxs-lookup"><span data-stu-id="fef20-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="fef20-132">No campo **Nome** da caixa de diálogo **Salvar Informações do Caso de Teste de Roteamento de Voz**, digite um nome exclusivo para o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="fef20-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="fef20-133">O nome deve ser exclusivo entre todos os casos de teste de roteamento de voz em sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fef20-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="fef20-134">Pode ter até 32 caracteres de comprimento e pode conter qualquer caractere alfanumérico, além da barra invertida (\\), ponto (.) ou sublinhado (\_).</span><span class="sxs-lookup"><span data-stu-id="fef20-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="fef20-p112">Observe que os campos restantes na caixa de diálogo **Salvar Informações do Caso de Teste de Roteamento** são somente leitura e são pré-preenchidos a partir dos resultados *e* configuração do teste informal. Verifique se essa é a configuração que você deseja salvar para o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="fef20-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fef20-137">Os valores dos resultados do teste são usados para pré-preencher os campos na caixa de diálogo <STRONG>Salvar Informações do Caso de Teste de Roteamento de Voz</STRONG> da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fef20-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="fef20-138"><STRONG>Conversão esperada</STRONG> é pré-preenchida com o valor no campo <STRONG>Número normalizado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fef20-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="fef20-139"><STRONG>Rota esperada</STRONG> é pré-preenchido com o valor no campo <STRONG>Primeira rota</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fef20-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="fef20-140"><STRONG>Registro esperado de uso do PSTN</STRONG> é pré-preenchido com o valor no campo <STRONG>Primeiro uso do PSTN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fef20-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="fef20-p113">Se nenhuma correspondência para qualquer um desses valores for encontrada durante a execução do teste, a entrada do campo correspondente ficará vazia na caixa de diálogo <STRONG>Salvar Informações do Caso de Teste de Roteamento de Voz</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fef20-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="fef20-142">Clique em **Ok** para salvar o caso de teste ou clique em **Cancelar** para voltar à caixa de diálogo **Exibir informações do caso de teste de roteamento de voz** para desenvolver ainda mais o teste antes de salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="fef20-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="fef20-143">Clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="fef20-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fef20-144">Sempre que você criar um caso de teste de roteamento de voz, deverá executar o comando <STRONG>Confirmar tudo</STRONG> para publicar o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="fef20-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="fef20-145">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="fef20-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fef20-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="fef20-146">See Also</span></span>


[<span data-ttu-id="fef20-147">Criar um caso de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="fef20-148">Executar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="fef20-149">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="fef20-150">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="fef20-151">Configurando planos de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="fef20-152">Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef20-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

