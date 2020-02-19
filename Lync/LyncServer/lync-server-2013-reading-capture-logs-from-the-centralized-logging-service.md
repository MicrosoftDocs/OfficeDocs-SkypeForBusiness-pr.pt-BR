---
title: 'Lync Server 2013: lendo logs de captura do serviço de registro em log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb1ec3ebde4f1277d6304190aceafa2e0fe2884
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="58a5d-102">Ler logs de captura do serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58a5d-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58a5d-103">_**Última modificação do tópico:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="58a5d-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="58a5d-104">Você percebe o real benefício do serviço de registro em log centralizado após a execução da pesquisa e tem um arquivo que pode ser usado para rastrear um problema relatado.</span><span class="sxs-lookup"><span data-stu-id="58a5d-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="58a5d-105">Existe um número de formas que você pode ler o arquivo.</span><span class="sxs-lookup"><span data-stu-id="58a5d-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="58a5d-106">O arquivo de resultado está em um formato de texto padrão e você pode usar Notepad.exe ou qualquer outro programa que permitirá abrir e ler um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="58a5d-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="58a5d-107">Para arquivos maiores e problemas mais complexos, você poderia usar uma ferramenta como o Snooper. exe, projetado para ler e analisar a saída de log do serviço de registro em log centralizado.</span><span class="sxs-lookup"><span data-stu-id="58a5d-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="58a5d-108">O Snooper é incluído com as Ferramentas de Depuração do Lync Server 2013 disponíveis como um download separado.</span><span class="sxs-lookup"><span data-stu-id="58a5d-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="58a5d-109">Você pode baixar as ferramentas de depuração do Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)aqui:.</span><span class="sxs-lookup"><span data-stu-id="58a5d-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="58a5d-110">Quando você instala as ferramentas de depuração do Lync Server 2013, atalhos curtos e itens de menu não são criados.</span><span class="sxs-lookup"><span data-stu-id="58a5d-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="58a5d-111">Após a instalação das ferramentas de depuração do Lync Server 2013, abra o Windows Explorer, uma janela de linha de comando ou o Shell de gerenciamento do Lync Server e vá para o diretório\\(local\\padrão) C:\\arquivos de programa Microsoft Lync Server 2013 ferramentas de depuração.</span><span class="sxs-lookup"><span data-stu-id="58a5d-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="58a5d-112">Clique duas vezes em Snooper. exe ou digite Snooper. exe e pressione ENTER se estiver usando a linha de comando ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58a5d-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58a5d-113">A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="58a5d-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="58a5d-114">A resolução de problemas e os processos relacionados é um assunto complexo.</span><span class="sxs-lookup"><span data-stu-id="58a5d-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="58a5d-115">Para obter detalhes sobre como solucionar problemas básicos e solucionar problemas de cargas de trabalho específicas, consulte o Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Server 2010 Resource Kit Book em.</span><span class="sxs-lookup"><span data-stu-id="58a5d-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="58a5d-116">Os processos e procedimentos ainda se aplicam ao Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58a5d-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="58a5d-117">O Lync Server 2013 introduz uma versão atualizada do Snooper que inclui alguns recursos novos.</span><span class="sxs-lookup"><span data-stu-id="58a5d-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="58a5d-118">A captura de tela a seguir mostra a versão do Snooper do Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="58a5d-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="58a5d-119">![Versão do Office Communications 2007 do Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Versão do Office Communications 2007 do Snooper.")</span><span class="sxs-lookup"><span data-stu-id="58a5d-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="58a5d-120">A captura de tela a seguir mostra a nova versão do Snooper incluída nas ferramentas de depuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58a5d-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="58a5d-121">![Lync Server 2013 versão do Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 versão do Snooper.")</span><span class="sxs-lookup"><span data-stu-id="58a5d-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="58a5d-122">A tela a seguir mostra a barra de ferramentas com funções usadas frequentemente.</span><span class="sxs-lookup"><span data-stu-id="58a5d-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="58a5d-123">![Barra de ferramentas do Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de ferramentas do Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="58a5d-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="58a5d-p104">E, o novo recurso que adiciona valor é a exibição do Fluxograma (fluxo de chamadas). Você seleciona um fluxo de mensagens na guia **Mensagem** e clica no botão **Fluxo de chamada**. Conforme você passa pelas mensagens, o fluxograma de chamada é atualizado com novos dados.</span><span class="sxs-lookup"><span data-stu-id="58a5d-p104">And, the newest feature that adds value is the Flow Chart (call flow) diagram view. You select a message flow in the **Message** tab and click the **Call Flow** button. As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="58a5d-127">![Diagrama de fluxo de chamadas 2013 do Snooper.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de fluxo de chamadas 2013 do Snooper.")</span><span class="sxs-lookup"><span data-stu-id="58a5d-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="58a5d-p105">É possível passar sobre a exibição do diagrama e obter detalhes sobre a mensagem e o conteúdo de fluxos e mensagens, assim como os elementos do servidor. Clique em qualquer seta do fluxo de chamadas para ir para a mensagem na exibição de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="58a5d-p105">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements. Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="58a5d-130">![Detalhes da mensagem do diagrama de fluxo de chamadas.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalhes da mensagem do diagrama de fluxo de chamadas.")</span><span class="sxs-lookup"><span data-stu-id="58a5d-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="58a5d-131">Para abrir um arquivo de log no Snooper</span><span class="sxs-lookup"><span data-stu-id="58a5d-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="58a5d-p106">Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.</span><span class="sxs-lookup"><span data-stu-id="58a5d-p106">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="58a5d-134">Após a instalação das ferramentas de depuração do Lync Server (LyncDebugTools. msi), altere o diretório para o local de Snooper. exe usando o Windows Explorer ou a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="58a5d-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="58a5d-135">Por padrão, as ferramentas de depuração estão localizadas em\\C:\\arquivos de programa ferramentas\\de depuração do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58a5d-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="58a5d-136">Clique duas vezes ou execute Snooper.exe.</span><span class="sxs-lookup"><span data-stu-id="58a5d-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="58a5d-137">Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de log, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="58a5d-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="58a5d-138">As mensagens de **Rastreamento** do arquivo de log são exibidas na guia **Rastreamento**. Clique na guia **Mensagens** para exibir o conteúdo da mensagem dos rastreamentos coletados.</span><span class="sxs-lookup"><span data-stu-id="58a5d-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="58a5d-139">Para exibir um fluxograma da chamada</span><span class="sxs-lookup"><span data-stu-id="58a5d-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="58a5d-p108">Para usar o Snooper e abrir arquivos de log, você precisa de acesso de leitura dos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você precisará ser um membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.</span><span class="sxs-lookup"><span data-stu-id="58a5d-p108">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="58a5d-142">Abra um arquivo de log e clique na guia **Mensagens**, selecione uma conversa na exibição de mensagens ou selecione um componente de rastreamento na guia **Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="58a5d-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="58a5d-143">Clique em **Fluxo de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="58a5d-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58a5d-p109">Se você clicar em uma mensagem ou rastreamento que não faz parte do fluxo de chamadas, o diagrama não aparecerá e uma mensagem de status aparece na parte inferior do Snooper dizendo “Esta mensagem não é elegível para fluxo de chamadas”. Escolha outra mensagem ou rastreamento e o fluxo de chamadas aparecerá se a mensagem ou o rastreamento faz parte de um fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="58a5d-p109">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”. Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="58a5d-146">Mova pelas Mensagens ou linhas de Rastreamento e observe se o fluxograma de chamada atualiza ou muda para exibir um novo diagrama.</span><span class="sxs-lookup"><span data-stu-id="58a5d-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="58a5d-147">Passe sobre os elementos para obter informações sobre mensagens de chamada, pontos de extremidade e outros componentes.</span><span class="sxs-lookup"><span data-stu-id="58a5d-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

