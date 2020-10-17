---
title: 'Lync Server 2013: ferramenta de diagnóstico de chamadas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19051eb183dc12f091de0d90ebb707bc6cee8fc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525148"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="301c0-102">Ferramenta de diagnóstico de chamadas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301c0-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="301c0-103">_**Última modificação do tópico:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="301c0-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="301c0-104">A ferramenta de diagnóstico de chamadas (PCD) do Lync é um aplicativo baseado no cliente que permite que você veja como o estado atual da sua rede pode afetar a qualidade de áudio em uma próxima chamada do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="301c0-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="301c0-105">O PCD é mais útil em situações em que o último salto de uma rede provavelmente será o mais fraco (por exemplo, com laptops em uma rede Wi-Fi pública ou usuários domésticos).</span><span class="sxs-lookup"><span data-stu-id="301c0-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="301c0-106">O PCD cria um pequeno fluxo de pacotes que atravessa o trecho final da rede.</span><span class="sxs-lookup"><span data-stu-id="301c0-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="301c0-107">Em seguida, a ferramenta analisa o fluxo de pacotes para estimar como a tremulação e a perda desse trecho podem afetar a qualidade da chamada e, em seguida, fornece um relatório.</span><span class="sxs-lookup"><span data-stu-id="301c0-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="301c0-108">Você pode executar o PCD continuamente no cliente, mesmo quando as chamadas estão sendo feitas.</span><span class="sxs-lookup"><span data-stu-id="301c0-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="301c0-109">O fluxo de pacote não tem um efeito significativo sobre a largura de banda.</span><span class="sxs-lookup"><span data-stu-id="301c0-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="301c0-110">**A versão mais recente do PCD, versão 1,1, inclui os seguintes aprimoramentos:**</span><span class="sxs-lookup"><span data-stu-id="301c0-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="301c0-111">Suporte para senhas mais longas, que agora podem ter até 127 caracteres</span><span class="sxs-lookup"><span data-stu-id="301c0-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="301c0-112">Diagnóstico adicional para problemas de entrada de autenticação</span><span class="sxs-lookup"><span data-stu-id="301c0-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="301c0-113">Melhor suporte para implantações híbridas do Lync</span><span class="sxs-lookup"><span data-stu-id="301c0-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="301c0-114">Atualizações para o seletor de credenciais</span><span class="sxs-lookup"><span data-stu-id="301c0-114">Updates to credential picker</span></span>

  - <span data-ttu-id="301c0-115">Melhorias de estabilidade</span><span class="sxs-lookup"><span data-stu-id="301c0-115">Stability improvements</span></span>

<span data-ttu-id="301c0-116">Agradecemos todos os comentários.</span><span class="sxs-lookup"><span data-stu-id="301c0-116">We appreciate any feedback.</span></span> <span data-ttu-id="301c0-117">Envie todas as perguntas ou problemas de suporte para o alias de [comentários do PCD](mailto:pcdfb@microsoft.com) em <pcdfb@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="301c0-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="301c0-118">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="301c0-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="301c0-119">Versões do Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="301c0-120">Requisitos do sistema do Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="301c0-121">Recursos do Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-121">Lync PCD Features</span></span>

  - <span data-ttu-id="301c0-122">Executando o Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-122">Running Lync PCD</span></span>

  - <span data-ttu-id="301c0-123">Desinstalando o Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="301c0-124">Versões do Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-124">Lync PCD Versions</span></span>

<span data-ttu-id="301c0-125">Este tópico descreve as seguintes versões da ferramenta, disponível para download gratuito:</span><span class="sxs-lookup"><span data-stu-id="301c0-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="301c0-126">Aplicativo da área de trabalho Windows ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )</span><span class="sxs-lookup"><span data-stu-id="301c0-126">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="301c0-127">Requisitos do sistema do Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="301c0-128">O PCD requer que a UCWA (Unified Communications Web API) seja instalada e configurada para dar suporte a clientes móveis na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="301c0-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="301c0-129">O UCWA é instalado com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="301c0-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="301c0-130">Requisitos do aplicativo da área de trabalho Windows</span><span class="sxs-lookup"><span data-stu-id="301c0-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="301c0-131">Qualquer edição do sistema operacional Windows 7 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="301c0-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="301c0-132">Microsoft .NET Framework 4,5 disponível em [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="301c0-132">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="301c0-133">Recursos do Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-133">Lync PCD Features</span></span>

<span data-ttu-id="301c0-134">O Lync PCD inclui os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="301c0-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="301c0-135">Executar no padrão por demanda (intermitências de 2 minutos)</span><span class="sxs-lookup"><span data-stu-id="301c0-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="301c0-136">Executar em modo Always on (até 24 horas no modo de exibição encaixado)</span><span class="sxs-lookup"><span data-stu-id="301c0-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="301c0-137">Exibição histórica de suas execuções de teste</span><span class="sxs-lookup"><span data-stu-id="301c0-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="301c0-138">Diagnosticar falhas de logon (Lync PCD somente para Windows 8)</span><span class="sxs-lookup"><span data-stu-id="301c0-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="301c0-139">![Captura de tela de progresso de recursos do Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de tela de progresso de recursos do Lync PCD")</span><span class="sxs-lookup"><span data-stu-id="301c0-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="301c0-140">Exibição gráfica de métricas de rede – MOS de rede, perda de pacotes e Tremulação de interentrada em tela inteira e modo de exibição instantâneo.</span><span class="sxs-lookup"><span data-stu-id="301c0-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="301c0-141">**Exibição de tela inteira**</span><span class="sxs-lookup"><span data-stu-id="301c0-141">**Full screen view**</span></span>

<span data-ttu-id="301c0-142">![Gráficos de resultados de teste da ferramenta de diagnóstico de chamadas](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultados de teste da ferramenta de diagnóstico de chamadas")</span><span class="sxs-lookup"><span data-stu-id="301c0-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="301c0-143">**Exibição ajustada**</span><span class="sxs-lookup"><span data-stu-id="301c0-143">**Snapped view**</span></span>

<span data-ttu-id="301c0-144">![Resultados do teste de utilização da ferramenta de diagnóstico de chamadas](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados do teste de utilização da ferramenta de diagnóstico de chamadas")</span><span class="sxs-lookup"><span data-stu-id="301c0-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="301c0-145">Executando o Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="301c0-146">Executando o aplicativo da área de trabalho Windows</span><span class="sxs-lookup"><span data-stu-id="301c0-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="301c0-147">Para iniciar o PCD em um sistema Windows 7, selecione **diagnóstico de chamadas** no menu **Iniciar** .</span><span class="sxs-lookup"><span data-stu-id="301c0-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="301c0-148">Para iniciar o PCD em um sistema Windows 8, selecione o ícone na tela inicial ou pesquise "diagnósticos de chamada".</span><span class="sxs-lookup"><span data-stu-id="301c0-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="301c0-149">![Ícone da ferramenta de diagnóstico de chamada](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Ícone da ferramenta de diagnóstico de chamada")</span><span class="sxs-lookup"><span data-stu-id="301c0-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="301c0-150">Quando a ferramenta for iniciada, selecione seu método preferido de fornecer credenciais e selecione o modo operacional de rede na caixa de diálogo **Opções da ferramenta de diagnóstico de chamadas** e, em seguida, selecione **OK**:</span><span class="sxs-lookup"><span data-stu-id="301c0-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="301c0-151">Selecione o botão **Iniciar teste** para começar a executar o diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="301c0-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="301c0-152">Se você selecionou a opção **usar credenciais de rede** , o teste começará imediatamente.</span><span class="sxs-lookup"><span data-stu-id="301c0-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="301c0-153">Se você selecionou a opção **deixe-me digitar minhas credenciais** , a caixa de diálogo **segurança do Windows** será aberta.</span><span class="sxs-lookup"><span data-stu-id="301c0-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="301c0-154">Depois de inserir suas credenciais, o teste é iniciado.</span><span class="sxs-lookup"><span data-stu-id="301c0-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="301c0-155">Desinstalando o Lync PCD</span><span class="sxs-lookup"><span data-stu-id="301c0-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="301c0-156">Para remover o Lync PCD, siga o procedimento para seu sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="301c0-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="301c0-157">Em um sistema Windows 7, abra o **painel de controle**, selecione **programas e recursos**e clique duas vezes em **diagnóstico de chamadas do Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="301c0-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="301c0-158">Em um sistema Windows 8, clique com o botão direito do mouse no bloco PCD e clique em **desinstalar** na barra de aplicativos na parte inferior da tela iniciar.</span><span class="sxs-lookup"><span data-stu-id="301c0-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

