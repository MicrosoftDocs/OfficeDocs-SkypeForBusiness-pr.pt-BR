---
title: 'Lync Server 2013: importando os pacotes de gerenciamento do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adaf9fe1c6d5d4cc0769810aece05bcb46681e79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="aac6e-102">Importando os pacotes de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aac6e-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aac6e-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="aac6e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="aac6e-104">Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar e como esses itens devem ser monitorados e como os alertas devem ser acionados e informação.</span><span class="sxs-lookup"><span data-stu-id="aac6e-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="aac6e-105">O Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que oferecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="aac6e-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="aac6e-106">O pacote de gerenciamento de componente e usuário (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) rastreia problemas do Lync Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos registros de detalhes da chamada (CDR) ou na qualidade da experiência (QoE) bancos.</span><span class="sxs-lookup"><span data-stu-id="aac6e-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="aac6e-107">Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="aac6e-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="aac6e-108">O SMS é a tecnlogia usada para enviar mensagens entre celulares.</span><span class="sxs-lookup"><span data-stu-id="aac6e-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aac6e-109">Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte a notificação de <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>configuração na biblioteca do TechNet em.</span><span class="sxs-lookup"><span data-stu-id="aac6e-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="aac6e-110">O pacote de gerenciamento de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como entrar no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado no Public comutado rede telefônica (PSTN).</span><span class="sxs-lookup"><span data-stu-id="aac6e-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="aac6e-111">Esses testes são conduzidos usando os cmdlets de transação sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aac6e-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="aac6e-112">Por exemplo, você pode usar o cmdlet **Test-CsIM**para simular conversas por mensagens instantâneas entre usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="aac6e-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="aac6e-113">Se a simulação de conversa falhar, um alerta é gerado.</span><span class="sxs-lookup"><span data-stu-id="aac6e-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="aac6e-114">Você deve importar os pacotes de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="aac6e-114">You need to import the management packs.</span></span> <span data-ttu-id="aac6e-115">Se você não importar os pacotes de gerenciamento, não poderá usar o Operations Manager para monitorar eventos do Lync Server ou executar transações sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aac6e-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="aac6e-116">O pacote de gerenciamento de componente e usuário é usado apenas para monitorar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac6e-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="aac6e-117">Se você estiver em um cenário de coexistência, em que o Lync Server 2013 e o Lync Server 2010 estão instalados, você deverá continuar a usar os pacotes de gerenciamento do Lync Server 2010 para seus computadores com o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aac6e-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aac6e-118">Os pacotes de gerenciamento do Lync Server 2010 incluem o pacote de gerenciamento de monitoramento do Lync Server 2010 e o pacote de gerenciamento de monitoramento de chat de grupo do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aac6e-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="aac6e-119">Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="aac6e-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="aac6e-120">**System Center Operations Manager**   com este método, você usa o Operations Manager para adicionar o monitoramento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aac6e-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="aac6e-121">**Shell do Operations Manager**   você pode usar o Shell do Operations Manager para importar diretamente ou solucionar quaisquer problemas que encontrar ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="aac6e-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="aac6e-122">Importando os pacotes de gerenciamento usando o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="aac6e-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="aac6e-123">Baixe os arquivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="aac6e-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="aac6e-124">No System Center Operations Manager, clique em **Administração**.</span><span class="sxs-lookup"><span data-stu-id="aac6e-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="aac6e-125">No painel **Administração**, clique com o botão direito do mouse em **Pacotes de gerenciamento** e, em seguida, clique em **Importar pacotes de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="aac6e-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="aac6e-126">Na caixa de diálogo **Selecinar pacotes de gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.</span><span class="sxs-lookup"><span data-stu-id="aac6e-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="aac6e-127">Na caixa de diálogo **conexão do catálogo online** , clique em **Cancelar** para impedir que o Operations Manager fique online para ver se há alguma dependência para os pacotes de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aac6e-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="aac6e-128">Se você estiver usando o System Center Operations Manager 2012, clique em **não**.</span><span class="sxs-lookup"><span data-stu-id="aac6e-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="aac6e-p107">Na caixa de diálogo **Selecionar pacotes de gerenciamento para importar**, localize e selecione os arquivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** e **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**. Em seguida, clique em **Abrir**. Para selecionar diversos arquivos na caixa de diálogo, mantenha a tecla Ctrl pressionada enquanto clica em outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="aac6e-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="aac6e-p108">Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso signfica que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para outra pasta e reinicie o processo de intalação e importação.</span><span class="sxs-lookup"><span data-stu-id="aac6e-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="aac6e-p109">Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. A conclusão do processo de importação e instalação pode levar muitos minuto</span><span class="sxs-lookup"><span data-stu-id="aac6e-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="aac6e-136">Importando pacotes de gerenciamento usando o Shell do Operations Manager</span><span class="sxs-lookup"><span data-stu-id="aac6e-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="aac6e-137">Em geral, é mais fácil importar os pacotes de gerenciamento usando o Operations Manager. no entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá os relatórios de erro adequados.</span><span class="sxs-lookup"><span data-stu-id="aac6e-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="aac6e-138">Por comparação, o Shell do Operations Manager oferece informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="aac6e-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="aac6e-139">Se você estiver usando o Operations Manager e tiver problemas para importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="aac6e-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="aac6e-140">O Shell do Operations Manager fornece mais informações que podem ajudá-lo a determinar o motivo da falha da importação.</span><span class="sxs-lookup"><span data-stu-id="aac6e-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="aac6e-141">Se você estiver usando o System Center Operations Manager 2007 R2, conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="aac6e-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="aac6e-142">Clique em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e em **shell do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="aac6e-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="aac6e-143">No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="aac6e-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="aac6e-144">Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="aac6e-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="aac6e-145">Feche o Shell do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="aac6e-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="aac6e-146">Se você estiver usando o System Center Operations Manager 2012, conclua este procedimento:</span><span class="sxs-lookup"><span data-stu-id="aac6e-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="aac6e-147">Clique **em Iniciar**, **em todos os programas**, em **Microsoft System Center 2012**, em **Operations Manager**e em **shell do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="aac6e-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="aac6e-148">No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="aac6e-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="aac6e-149">Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho até sua cópia do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="aac6e-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

