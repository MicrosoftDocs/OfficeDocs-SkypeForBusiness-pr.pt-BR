---
title: 'Lync Server 2013: executar casos de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="6438e-102">Executar casos de teste de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6438e-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6438e-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="6438e-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="6438e-104">Você pode executar todos os casos de teste em seu pacote de casos de teste de roteamento de voz, ou pode executar um ou mais casos de teste selecionados.</span><span class="sxs-lookup"><span data-stu-id="6438e-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="6438e-105">Para executar todos os casos de teste de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="6438e-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="6438e-106">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6438e-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6438e-107">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6438e-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6438e-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6438e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6438e-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6438e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6438e-110">Na barra de navegação à esquerda, clique em **Roteamento de voz** e, em seguida, clique em **testar roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="6438e-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="6438e-111">Na página **testar roteamento de voz** , clique em **ação** e, em seguida, clique em **executar tudo**.</span><span class="sxs-lookup"><span data-stu-id="6438e-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="6438e-112">O status de aprovação ou falha de cada caso de teste é mostrado na coluna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="6438e-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="6438e-113">Se um caso de teste ainda não foi executado, N/d é mostrado na coluna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="6438e-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="6438e-114">Adicionais Para ver os resultados detalhados de cada caso de teste, clique duas vezes no nome do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="6438e-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="6438e-115">Os resultados são mostrados na área sombreada no lado direito da página **Editar caso de teste** :</span><span class="sxs-lookup"><span data-stu-id="6438e-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="6438e-116">**Resultado do teste:** Status geral de aprovação ou falha da execução do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="6438e-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="6438e-117">**Regra de normalização:** A primeira regra de normalização no plano de discagem selecionada para este caso de teste que corresponda ao número discado (o valor no campo **número a ser testado** ).</span><span class="sxs-lookup"><span data-stu-id="6438e-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="6438e-118">**Número normalizado:** O valor do número discado após a regra de normalização o converteu.</span><span class="sxs-lookup"><span data-stu-id="6438e-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="6438e-119">**Uso da primeira PSTN:** O primeiro registro de uso de rede telefônica pública comutada (PSTN) na política de voz selecionada para este caso de teste que corresponda ao número discado.</span><span class="sxs-lookup"><span data-stu-id="6438e-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="6438e-120">**Primeira rota:** A primeira rota de voz no primeiro registro de uso PSTN que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="6438e-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6438e-121">O <STRONG>registro de uso PSTN esperado</STRONG> e os campos de <STRONG>rota esperada</STRONG> são opcionais na configuração de caso de teste de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="6438e-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="6438e-122">Se o caso de teste não especificar esses valores, o campo correspondente nos resultados do teste estará vazio.</span><span class="sxs-lookup"><span data-stu-id="6438e-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="6438e-123">Para executar um ou mais casos de teste de roteamento de voz selecionado</span><span class="sxs-lookup"><span data-stu-id="6438e-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="6438e-124">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6438e-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6438e-125">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6438e-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6438e-126">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6438e-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6438e-127">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6438e-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6438e-128">Na barra de navegação à esquerda, clique em **Roteamento de voz**e, em seguida, clique em **testar roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="6438e-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="6438e-129">Na página **testar roteamento de voz** , clique nos nomes dos casos de teste que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="6438e-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="6438e-130">No menu **ação** , clique em **executar selecionado**.</span><span class="sxs-lookup"><span data-stu-id="6438e-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="6438e-131">O status de aprovação ou falha de cada caso de teste é mostrado na coluna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="6438e-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="6438e-132">Se um caso de teste ainda não foi executado, N/d é mostrado na coluna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="6438e-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="6438e-133">Adicionais Para ver os resultados detalhados de cada caso de teste, clique duas vezes no nome do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="6438e-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="6438e-134">Os resultados são mostrados na área sombreada no lado direito da página **Editar caso de teste** :</span><span class="sxs-lookup"><span data-stu-id="6438e-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="6438e-135">**Resultado do teste:** Status geral de aprovação ou falha da execução do caso de teste.</span><span class="sxs-lookup"><span data-stu-id="6438e-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="6438e-136">**Regra de normalização:** A primeira regra de normalização no plano de discagem selecionada para este caso de teste que corresponda ao número discado (o valor no campo **número a ser testado** ).</span><span class="sxs-lookup"><span data-stu-id="6438e-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="6438e-137">**Número normalizado:** O valor do número discado após a regra de normalização o converteu.</span><span class="sxs-lookup"><span data-stu-id="6438e-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="6438e-138">**Uso da primeira PSTN:** O primeiro registro de uso PSTN na política de voz selecionada para este caso de teste que corresponda ao número discado.</span><span class="sxs-lookup"><span data-stu-id="6438e-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="6438e-139">**Primeira rota:** A primeira rota de voz no primeiro registro de uso PSTN que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="6438e-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6438e-140">O <STRONG>registro de uso PSTN esperado</STRONG> e os campos de <STRONG>rota esperada</STRONG> são opcionais na configuração de caso de teste de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="6438e-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="6438e-141">Se o caso de teste não especificar esses valores, o campo correspondente nos resultados do teste estará vazio.</span><span class="sxs-lookup"><span data-stu-id="6438e-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6438e-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="6438e-142">See Also</span></span>


[<span data-ttu-id="6438e-143">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6438e-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="6438e-144">Executando testes de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6438e-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

