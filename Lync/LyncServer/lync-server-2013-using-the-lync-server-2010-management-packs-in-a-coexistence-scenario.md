---
title: Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264cd8f1495840eb6dd86879f279110cd4de4784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="8afca-102">Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência</span><span class="sxs-lookup"><span data-stu-id="8afca-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8afca-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8afca-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8afca-104">Muitos clientes adotam um programa de distribuição dentro de suas empresas, em que os usuários migram progressivamente do Microsoft Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8afca-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="8afca-105">Os administradores nessas empresas se preocupam em monitorar as duas versões do Lync Server para ajudar a garantir que todos os seus usuários finais tenham a melhor experiência de comunicação possível.</span><span class="sxs-lookup"><span data-stu-id="8afca-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="8afca-106">Para esse cenário, o pacote de gerenciamento do Lync Server 2013 dá suporte a um caminho de migração lado a lado com o pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8afca-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="8afca-107">No Lync Server 2010, os computadores do Lync Server foram descobertos por meio do documento de topologia armazenado com o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="8afca-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="8afca-108">Nesta configuração, um único computador pode reportar a existência de todos os outros computadores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8afca-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="8afca-109">Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta em nível de máquina em vez do mecanismo de descoberta central usado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8afca-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="8afca-110">Isso significa que cada agente do System Center essencialmente descobre e relata sua existência ao System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8afca-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="8afca-111">O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do sistema central e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir mais facilmente.</span><span class="sxs-lookup"><span data-stu-id="8afca-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="8afca-112">Para dar suporte a essa migração, primeiro você precisará atualizar o monitoramento existente do Lync Server 2010 para evitar lacunas na cobertura.</span><span class="sxs-lookup"><span data-stu-id="8afca-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="8afca-113">Para fazer isso, elege um computador existente do Lync Server 2010 para atender ao script de descoberta central do servidor do Lync 2010 antes de atualizar seu repositório de gerenciamento central para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8afca-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="8afca-114">Este é um processo de quatro etapas:</span><span class="sxs-lookup"><span data-stu-id="8afca-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="8afca-115">Atualize os pacotes de gerenciamento do Lync Server 2010 para a atualização cumulativa 7.</span><span class="sxs-lookup"><span data-stu-id="8afca-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="8afca-116">Instrua um computador com o Lync Server 2010 para executar o script de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="8afca-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="8afca-117">Substitua o candidato de descoberta central no pacote de gerenciamento do Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8afca-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="8afca-118">Verifique se o novo candidato de descoberta central foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="8afca-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="8afca-119">Como instruir um computador com o Lync Server 2010 para executar o script de descoberta central</span><span class="sxs-lookup"><span data-stu-id="8afca-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="8afca-120">Para indicar um computador que não seja do repositório de gerenciamento central (por exemplo, um servidor front-end do Lync Server) para manipular a descoberta central, você precisará criar a seguinte chave do registro no servidor do repositório de gerenciamento não central:</span><span class="sxs-lookup"><span data-stu-id="8afca-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="8afca-121">Software\\\\HKLM CentralDiscoveryCandidate\\integridade\\\\da comunicação em tempo real da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8afca-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="8afca-122">Você pode criar essa chave do registro completando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="8afca-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="8afca-123">Clique em **Iniciar** e em **executar**.</span><span class="sxs-lookup"><span data-stu-id="8afca-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8afca-124">Na caixa de diálogo **executar** , digite **regedit** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="8afca-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="8afca-125">No editor do registro, expanda **HKEY\_\_local Machine**, expanda **software**, expanda **Microsoft**e, em seguida, expanda **comunicações em tempo real**.</span><span class="sxs-lookup"><span data-stu-id="8afca-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="8afca-126">Clique com o botão direito do mouse em **integridade**, clique em **novo**e clique em **chave**.</span><span class="sxs-lookup"><span data-stu-id="8afca-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="8afca-127">Se a chave de **integridade** não existir, clique com o botão direito do mouse em **comunicações em tempo real**, aponte para **novo**e clique em **tecla**.</span><span class="sxs-lookup"><span data-stu-id="8afca-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="8afca-128">Quando a nova chave for criada, digite Health e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="8afca-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="8afca-129">Após a criação da nova chave, digite **CentralDiscoveryCandidate** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="8afca-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="8afca-130">Pode levar o computador várias horas para que essa alteração seja retomada.</span><span class="sxs-lookup"><span data-stu-id="8afca-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="8afca-131">Para fazer com que a alteração entre em vigor imediatamente, pare e reinicie o serviço do agente de integridade.</span><span class="sxs-lookup"><span data-stu-id="8afca-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="8afca-132">Para reiniciar o serviço do agente de integridade, conclua o procedimento a seguir no computador do Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="8afca-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="8afca-133">Clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8afca-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="8afca-134">Na janela do console, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="8afca-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="8afca-135">Você verá uma mensagem que informa que "o serviço de gerenciamento do System Center está sendo interrompido", seguido por uma segunda mensagem que informa que o serviço foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="8afca-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="8afca-136">Depois que o serviço for interrompido, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="8afca-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="8afca-137">Substituindo o candidato à descoberta central no pacote de gerenciamento do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8afca-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="8afca-138">Depois de instruir um computador do Lync Server 2010 a ser relatado nos computadores do Lync Server 2010, você precisará informar o pacote de gerenciamento do Lync Server 2010 sobre essa alteração também.</span><span class="sxs-lookup"><span data-stu-id="8afca-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="8afca-139">Para fazer isso, será necessário criar uma substituição no pacote de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="8afca-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="8afca-140">Isso pode ser feito completando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="8afca-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="8afca-141">No console do Operations Manager, clique em **criação**.</span><span class="sxs-lookup"><span data-stu-id="8afca-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="8afca-142">Na guia criação de páginas, expanda **objetos do pacote de gerenciamento**, clique em descobertas de **objeto**e, em seguida, clique em **escopo**.</span><span class="sxs-lookup"><span data-stu-id="8afca-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="8afca-143">Na caixa de diálogo **escopo de objetos do pacote de gerenciamento** , selecione o item com o candidato da **descoberta ls** de destino e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8afca-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="8afca-144">Observe que o candidato da descoberta de LS será exibido apenas se você tiver instalado o pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8afca-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="8afca-145">No console do Operations Manager, clique com o botão direito do mouse em **candidato à descoberta ls**, aponte para **substituições**, aponte para **substituir a descoberta de objeto**e clique em **para todos os objetos da classe: candidato à descoberta de ls**.</span><span class="sxs-lookup"><span data-stu-id="8afca-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="8afca-146">Na caixa de diálogo **substituir Propriedades** , marque a caixa de seleção **substituir** ao lado da **descoberta central do parâmetro WatcherNode FQDN**.</span><span class="sxs-lookup"><span data-stu-id="8afca-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="8afca-147">Digite o nome de domínio totalmente qualificado do computador do Lync Server 2010 nas caixas **substituir valor** e **valor efetivo** .</span><span class="sxs-lookup"><span data-stu-id="8afca-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="8afca-148">Marque a caixa de seleção **imposto** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8afca-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="8afca-149">Depois de criar a substituição, você precisará reiniciar o serviço de integridade no servidor de gerenciamento raiz.</span><span class="sxs-lookup"><span data-stu-id="8afca-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="8afca-150">Para reiniciar o serviço de integridade, conclua o procedimento a seguir no servidor de gerenciamento raiz:</span><span class="sxs-lookup"><span data-stu-id="8afca-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="8afca-151">Clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8afca-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="8afca-152">Na janela do console, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="8afca-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="8afca-153">Você verá uma mensagem informando que "o serviço de gerenciamento do System Center está sendo interrompido", seguido por uma segunda mensagem que informa que o serviço foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="8afca-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="8afca-154">Depois que o serviço for interrompido, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="8afca-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="8afca-155">Verificando se o novo candidato de descoberta central foi descoberto</span><span class="sxs-lookup"><span data-stu-id="8afca-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="8afca-156">A etapa final antes da atualização do repositório de gerenciamento central é verificar se o novo candidato de descoberta central foi descoberto pelo pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8afca-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="8afca-157">Para fazer isso, abra o console do Operations Manager e, em seguida, clique em monitoramento.</span><span class="sxs-lookup"><span data-stu-id="8afca-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="8afca-158">Na guia monitoramento, expanda **integridade do Microsoft Lync Server 2010**, expanda **descoberta de topologia**e clique em **modo de exibição estado de descoberta**.</span><span class="sxs-lookup"><span data-stu-id="8afca-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="8afca-159">Verifique se uma linha na tela tem um **caminho** que lista o nome de domínio totalmente qualificado do candidato à descoberta central.</span><span class="sxs-lookup"><span data-stu-id="8afca-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="8afca-160">Você também deve verificar se o estado do computador é reportado como **íntegro**.</span><span class="sxs-lookup"><span data-stu-id="8afca-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

