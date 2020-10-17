---
title: 'Lync Server 2013: criar um caso de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da110d7e3bfb7188384163cb572591d0bf7f8ff3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501768"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="655ad-102">Criar um caso de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="655ad-102">Create a voice routing test case in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="655ad-103">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="655ad-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="655ad-104">Para criar um caso de teste</span><span class="sxs-lookup"><span data-stu-id="655ad-104">To create a test case</span></span>

1.  <span data-ttu-id="655ad-105">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="655ad-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="655ad-106">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="655ad-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="655ad-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="655ad-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="655ad-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="655ad-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="655ad-109">Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Testar Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="655ad-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="655ad-110">Na página **Testar Roteamento de Voz**, clique em **Novo** para criar um novo caso de teste.</span><span class="sxs-lookup"><span data-stu-id="655ad-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="655ad-111">Em **Nome**, digite um nome exclusivo para o caso de teste.</span><span class="sxs-lookup"><span data-stu-id="655ad-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="655ad-112">O nome deve ser exclusivo entre todos os casos de teste de roteamento de voz em sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="655ad-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="655ad-113">Pode ter até 32 caracteres de comprimento e pode conter qualquer caractere alfanumérico, além da barra invertida ( \\ ), ponto (.) ou sublinhado ( \_ ).</span><span class="sxs-lookup"><span data-stu-id="655ad-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="655ad-p104">Em **Número discado para fazer um teste**, digite o número discado que deseja usar para testar a configuração de roteamento que você especificar para esse caso de teste. Com base no plano de discagem, na rota e na política de voz, esse número será normalizado e exibido como saída.</span><span class="sxs-lookup"><span data-stu-id="655ad-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="655ad-p105">Na lista **Plano de Discagem**, selecione o plano de discagem a ser usado ao executar o teste. O padrão é o plano de discagem Global.</span><span class="sxs-lookup"><span data-stu-id="655ad-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="655ad-p106">Na lista **Política de Voz**, selecione a política de voz a ser usada ao executar o teste. O padrão é a política de voz Global.</span><span class="sxs-lookup"><span data-stu-id="655ad-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="655ad-p107">Em **Conversão esperada**, digite o número de telefone no formato que você espera ver após a conversão. Esse é o valor do número de telefone que você está testando depois que ele foi convertido pela primeira regra de normalização correspondente no plano de discagem selecionado. Quando você executa o caso de teste, se o número que está testando não resultar no valor em **Conversão esperada**, o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="655ad-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="655ad-p108">(Opcional) Na lista **Uso de PSTN esperado**, você pode selecionar o registro de uso da Rede Telefônica Pública Comutada (PSTN) que espera que seja usado ao executar o caso de teste, com base na política de voz e no plano de discagem especificado. Se um registro de uso diferente do PSTN for usado, o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="655ad-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="655ad-p109">(Opcional) Na lista **Rota esperada**, você pode selecionar a rota de voz que espera que seja usada ao executar o caso de teste, com base na política de voz e no plano de discagem especificado. Se um registro de uso diferente do PSTN for usado, o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="655ad-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="655ad-p110">(Opcional) Clique em **Executar**  para executar o caso de teste. Os resultados são mostrados no painel à direita da página.</span><span class="sxs-lookup"><span data-stu-id="655ad-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="655ad-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="655ad-129">Click **OK**.</span></span>

14. <span data-ttu-id="655ad-130">Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="655ad-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="655ad-131">Sempre que criar um caso de teste de roteamento de voz, você deve executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="655ad-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="655ad-132">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="655ad-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="655ad-133">Se o plano de discagem que está sendo empregado no teste normalizar números de telefone que começam com um sinal de adição (por exemplo, + 12065551219), esse plano pode causar uma falha no teste de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="655ad-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="655ad-134">(O plano de discagem e a rota de voz funcionará; na verdade, Test-CsDialPlan será bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="655ad-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="655ad-135">No entanto, o teste de roteamento de voz pode falhar. É algo que você deve ter em mente ao testar as rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="655ad-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="655ad-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="655ad-136">See Also</span></span>


[<span data-ttu-id="655ad-137">Exportar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="655ad-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="655ad-138">Importar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="655ad-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="655ad-139">Configurando planos de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="655ad-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="655ad-140">Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="655ad-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

