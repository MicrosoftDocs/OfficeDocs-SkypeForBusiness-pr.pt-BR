---
title: 'Lync Server 2013: executar casos de teste de roteamento de voz'
description: 'Lync Server 2013: executar casos de teste de roteamento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566787"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="42357-103">Executar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42357-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42357-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="42357-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="42357-105">Você pode executar todos os casos de teste no seu pacote de casos de teste de roteamento de voz ou pode executar um ou mais casos de teste selecionados.</span><span class="sxs-lookup"><span data-stu-id="42357-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="42357-106">Para executar todos os casos de teste de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="42357-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="42357-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="42357-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="42357-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="42357-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="42357-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42357-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42357-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42357-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42357-111">Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Testar roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="42357-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="42357-112">Na página **Testar roteamento de voz**, clique em \*\*Ação \*\* e em **Executar todos**.</span><span class="sxs-lookup"><span data-stu-id="42357-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="42357-p103">O status de aprovação ou reprovação de cada caso de teste é exibido na coluna **Aprovado/reprovado**. Se um caso de teste ainda não foi executado, N/D é exibido na coluna **Aprovado/reprovado**.</span><span class="sxs-lookup"><span data-stu-id="42357-p103">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="42357-p104">(Opcional) Para ver os resultados detalhados para cada caso de teste, clique duas vezes no nome do caso de teste. Os resultados são exibidos na área acinzentada no lado direito da página **Editar caso de teste**:</span><span class="sxs-lookup"><span data-stu-id="42357-p104">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="42357-117">**Resultado do teste:** Status de aprovação geral ou de falha da execução do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="42357-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="42357-118">**Regra de normalização:** A primeira regra de normalização no plano de discagem selecionado para este caso de teste que corresponde ao número discado (o valor no campo **número para teste** ).</span><span class="sxs-lookup"><span data-stu-id="42357-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="42357-119">**Número normalizado:** O valor do número discado após a regra de normalização a converteu.</span><span class="sxs-lookup"><span data-stu-id="42357-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="42357-120">**Primeiro uso de PSTN:** O primeiro registro de uso de PSTN (rede telefônica pública comutada) na política de voz selecionada para este caso de teste que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="42357-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="42357-121">**Primeiro roteamento:** A primeira rota de voz no primeiro registro de uso de PSTN que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="42357-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="42357-p105">Os campos <STRONG>Registro de uso PSTN esperado</STRONG> e <STRONG>Roteamento esperado</STRONG> são opcionais na configuração do caso de teste de roteamento de voz. Se o caso de teste não especificar estes valores, o campo correspondente nos resultados de teste estarão vazios.</span><span class="sxs-lookup"><span data-stu-id="42357-p105">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="42357-124">Para executar um ou mais casos de teste de roteamento de voz selecionados</span><span class="sxs-lookup"><span data-stu-id="42357-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="42357-125">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="42357-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="42357-126">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="42357-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="42357-127">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42357-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42357-128">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42357-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42357-129">Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Testar roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="42357-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="42357-130">Na página \*\*Testar roteamento de voz \*\*, clique nos nomes dos casos de teste que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="42357-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="42357-131">No menu \*\*Ação \*\*, clique em **Executar selecionado**.</span><span class="sxs-lookup"><span data-stu-id="42357-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="42357-p108">O status de aprovação ou reprovação de cada caso de teste é exibido na coluna **Aprovado/reprovado**. Se um caso de teste ainda não foi executado, N/D é exibido na coluna **Aprovado/reprovado**.</span><span class="sxs-lookup"><span data-stu-id="42357-p108">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="42357-p109">(Opcional) Para ver os resultados detalhados para cada caso de teste, clique duas vezes no nome do caso de teste. Os resultados são exibidos na área acinzentada no lado direito da página **Editar caso de teste**:</span><span class="sxs-lookup"><span data-stu-id="42357-p109">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="42357-136">**Resultado do teste:** Status de aprovação geral ou de falha da execução do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="42357-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="42357-137">**Regra de normalização:** A primeira regra de normalização no plano de discagem selecionado para este caso de teste que corresponde ao número discado (o valor no campo **número para teste** ).</span><span class="sxs-lookup"><span data-stu-id="42357-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="42357-138">**Número normalizado:** O valor do número discado após a regra de normalização a converteu.</span><span class="sxs-lookup"><span data-stu-id="42357-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="42357-139">**Primeiro uso de PSTN:** O primeiro registro de uso de PSTN na política de voz selecionada para este caso de teste que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="42357-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="42357-140">**Primeiro roteamento:** A primeira rota de voz no primeiro registro de uso de PSTN que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="42357-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="42357-p110">Os campos <STRONG>Registro de uso PSTN esperado</STRONG> e <STRONG>Roteamento esperado</STRONG> são opcionais na configuração do caso de teste de roteamento de voz. Se o caso de teste não especificar estes valores, o campo correspondente nos resultados de teste estarão vazios.</span><span class="sxs-lookup"><span data-stu-id="42357-p110">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42357-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="42357-143">See Also</span></span>


[<span data-ttu-id="42357-144">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42357-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="42357-145">Executando testes de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42357-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

