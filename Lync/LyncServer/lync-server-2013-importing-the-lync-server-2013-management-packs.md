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
ms.openlocfilehash: 1cc97cad4069c286f66707c34a9a1af7e87e97da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="1f459-102">Importando os pacotes de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f459-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f459-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1f459-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1f459-104">Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar e como esses itens devem ser monitorados e como os alertas devem ser acionados e menciona.</span><span class="sxs-lookup"><span data-stu-id="1f459-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="1f459-105">O Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="1f459-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="1f459-106">O componente e o pacote de gerenciamento de usuários (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) controla problemas do Lync Server gravados em logs de eventos, registrados por contadores de desempenho, ou registrados nos registros de detalhes de chamadas (CDR) ou na qualidade da experiência (QoE) bancos.</span><span class="sxs-lookup"><span data-stu-id="1f459-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="1f459-107">Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (serviço de mensagens curtas).</span><span class="sxs-lookup"><span data-stu-id="1f459-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="1f459-108">SMS é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.)</span><span class="sxs-lookup"><span data-stu-id="1f459-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f459-109">Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte a notificação Configurando na biblioteca do TechNet em <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span><span class="sxs-lookup"><span data-stu-id="1f459-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="1f459-110">O pacote de gerenciamento de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como conectar-se ao sistema, trocar mensagens de chat ou fazer chamadas para um telefone localizado na pública comutada rede telefônica (PSTN).</span><span class="sxs-lookup"><span data-stu-id="1f459-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="1f459-111">Esses testes são conduzidos usando cmdlets de transação sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f459-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="1f459-112">Por exemplo, você pode usar o cmdlet **Test-CsIM** para simular uma conversa de mensagens instantâneas entre um par de usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="1f459-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="1f459-113">Se essa conversa de mensagens simulada falhar, um alerta será gerado.</span><span class="sxs-lookup"><span data-stu-id="1f459-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="1f459-114">Você precisa importar os pacotes de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="1f459-114">You need to import the management packs.</span></span> <span data-ttu-id="1f459-115">Se você não importar os pacotes de gerenciamento, não poderá usar o Operations Manager para monitorar eventos do Lync Server ou executar transações sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f459-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="1f459-116">O pacote de gerenciamento de componentes e usuários só é usado para monitorar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f459-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="1f459-117">Se você estiver em um cenário de coexistência, no qual você tem o Lync Server 2013 e o Lync Server 2010 instalados, você deve continuar a usar os pacotes de gerenciamento do Lync Server 2010 para seus computadores com o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1f459-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f459-118">Os pacotes de gerenciamento do Lync Server 2010 incluem o pacote de gerenciamento de monitoramento do Lync Server 2010 e o pacote de gerenciamento de monitoramento de chat de grupo do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1f459-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="1f459-119">Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="1f459-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="1f459-120">**System Center Operations Manager**   com esse método, use o Gerenciador de operações para adicionar o monitoramento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f459-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="1f459-121">**Shell do Operations Manager**   você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas encontrados ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1f459-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="1f459-122">Importando os pacotes de gerenciamento usando o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1f459-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="1f459-123">Baixe os arquivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="1f459-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="1f459-124">No System Center Operations Manager, clique em **Administração**.</span><span class="sxs-lookup"><span data-stu-id="1f459-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="1f459-125">No painel **Administração** , clique com o botão direito do mouse em **pacotes de gerenciamento**e, em seguida, clique em **importar pacotes de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="1f459-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="1f459-126">Na caixa de diálogo **Selecionar Pacotes de Gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.</span><span class="sxs-lookup"><span data-stu-id="1f459-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="1f459-127">Na caixa de diálogo **conexão de catálogo online** , clique em **Cancelar** para impedir que o Operations Manager fique online para ver se há dependências para os pacotes de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f459-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="1f459-128">Se você estiver usando o System Center Operations Manager 2012, clique em **não**.</span><span class="sxs-lookup"><span data-stu-id="1f459-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="1f459-129">Na caixa de diálogo **selecionar pacotes de gerenciamento a serem importados** , localize e selecione os arquivos **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** e **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** e, em seguida, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="1f459-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="1f459-130">Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo, mantenha pressionada a tecla CTRL e clique no segundo arquivo.</span><span class="sxs-lookup"><span data-stu-id="1f459-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="1f459-131">Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="1f459-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="1f459-132">Se receber uma mensagem de erro e a instalação falhar, geralmente isso significa que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="1f459-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="1f459-133">Se isso ocorrer, copie os arquivos para uma pasta diferente e reinicie o processo de importação e instalação.</span><span class="sxs-lookup"><span data-stu-id="1f459-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="1f459-134">Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1f459-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="1f459-135">Observe que o processo de importação e instalação pode exigir vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="1f459-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="1f459-136">Importando pacotes de gerenciamento usando o Shell do Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1f459-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="1f459-137">Em geral, é mais fácil importar os pacotes de gerenciamento usando o Gerenciador de operações. no entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá os relatórios de erro adequados.</span><span class="sxs-lookup"><span data-stu-id="1f459-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="1f459-138">Por comparação, o Shell do Operations Manager fornece informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1f459-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="1f459-139">Se você estiver usando o Operations Manager e tiver problemas para importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1f459-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="1f459-140">O Shell do Operations Manager fornece mais informações que podem ajudá-lo a determinar por que houve falha na importação.</span><span class="sxs-lookup"><span data-stu-id="1f459-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="1f459-141">Se você estiver usando o System Center Operations Manager 2007 R2, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="1f459-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="1f459-142">Clique em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e, em seguida, clique em **shell do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="1f459-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="1f459-143">No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e, em seguida, pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="1f459-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="1f459-144">Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="1f459-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="1f459-145">Feche o Shell do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1f459-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="1f459-146">Se você estiver usando o System Center Operations Manager 2012, conclua este procedimento em vez disso:</span><span class="sxs-lookup"><span data-stu-id="1f459-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="1f459-147">Clique em **Iniciar**, **Todos os Programas**, **Microsoft System Center 2012**, **Operations Manager** e **Shell do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="1f459-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="1f459-148">No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e, em seguida, pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="1f459-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="1f459-149">Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="1f459-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

