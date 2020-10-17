---
title: Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência
description: Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência.
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
ms.openlocfilehash: f5f6e76f49b74badd0f40d115101abb38aa35172
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556057"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="37bfc-103">Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência</span><span class="sxs-lookup"><span data-stu-id="37bfc-103">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37bfc-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="37bfc-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="37bfc-105">Muitos clientes adotam um programa de distribuição dentro de suas empresas nas quais os usuários são migrados progressivamente do Microsoft Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37bfc-105">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="37bfc-106">Os administradores dessas empresas se preocupam em monitorar as duas versões do Lync Server para ajudar a garantir que todos os usuários finais estejam obtendo a melhor experiência de comunicação possível.</span><span class="sxs-lookup"><span data-stu-id="37bfc-106">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="37bfc-107">Para este cenário, o pacote de gerenciamento do Lync Server 2013 oferece suporte a um caminho de migração lado a lado com o pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37bfc-107">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="37bfc-108">No Lync Server 2010, os computadores do Lync Server foram detectados pelo documento de topologia armazenado com o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="37bfc-108">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="37bfc-109">Nessa configuração, um único computador reportaria a existência de todos os outros computadores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37bfc-109">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="37bfc-110">Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta no nível de máquina em vez do mecanismo de descoberta central usado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37bfc-110">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="37bfc-111">Isso significa que cada agente do System Center, descobre essencialmente a si mesmo e relata sua existência ao System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="37bfc-111">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="37bfc-112">O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do System Center e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir com mais facilidade.</span><span class="sxs-lookup"><span data-stu-id="37bfc-112">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="37bfc-113">Para dar suporte a essa migração, primeiro você precisará atualizar seu monitoramento existente do Lync Server 2010 para evitar lacunas de cobertura.</span><span class="sxs-lookup"><span data-stu-id="37bfc-113">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="37bfc-114">Para fazer isso, elege um computador existente do Lync Server 2010 para atender ao script de descoberta central do Lync Server 2010 antes de atualizar seu repositório de gerenciamento central para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37bfc-114">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="37bfc-115">Este é um processo em quatro etapas:</span><span class="sxs-lookup"><span data-stu-id="37bfc-115">This is a four-step process:</span></span>

1.  <span data-ttu-id="37bfc-116">Atualize os pacotes de gerenciamento do Lync Server 2010 para a atualização cumulativa 7.</span><span class="sxs-lookup"><span data-stu-id="37bfc-116">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="37bfc-117">Instrua um computador do Lync Server 2010 para executar o script de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="37bfc-117">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="37bfc-118">Substitua o candidato de descoberta central no pacote de gerenciamento do Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37bfc-118">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="37bfc-119">Verifique se o novo Candidato a Descoberta Central foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="37bfc-119">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="37bfc-120">Instrua um computador com Lync Server 2010 para executar o script de Descoberta Central</span><span class="sxs-lookup"><span data-stu-id="37bfc-120">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="37bfc-121">Para indicar um computador do repositório de gerenciamento não central (por exemplo, um servidor front-end do Lync Server) para lidar com a descoberta central, você precisará criar a seguinte chave do registro no servidor do repositório de gerenciamento não central:</span><span class="sxs-lookup"><span data-stu-id="37bfc-121">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="37bfc-122">\\CentralDiscoveryCandidate de \\ \\ integridade de comunicação em tempo real da Microsoft \\ \\</span><span class="sxs-lookup"><span data-stu-id="37bfc-122">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="37bfc-123">Você pode instalar criar essa chave de registro concluindo o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="37bfc-123">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="37bfc-124">Clique em **Iniciar** e depois em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-124">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="37bfc-125">Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="37bfc-125">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="37bfc-126">No editor do registro, expanda \*\* \_ \_ máquina local de hKey\*\*, expanda **software**, expanda **Microsoft**e, em seguida, expanda **comunicação em tempo real**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-126">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="37bfc-p105">Com o botão direito em **Integridade**, clique em **Novo**, e depois em **Chave**. Se a chave **Integridade** não existir, clique com o botão direito em **Comunicações em tempo real**, aponte para **Novo**, e depois clique em **Chave**. Quando a nova chave for criada, digite Integridade, e depois pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="37bfc-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="37bfc-130">Depois que a nova chave for criada, digite **CentralDiscoveryCandidate** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="37bfc-130">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="37bfc-131">Pode levar algumas horas para que o computador obtenha essa alteração.</span><span class="sxs-lookup"><span data-stu-id="37bfc-131">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="37bfc-132">Para atualizar essas configurações imediatamente, pare e em seguida reinicie o serviço Agente de Integridade.</span><span class="sxs-lookup"><span data-stu-id="37bfc-132">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="37bfc-133">Para reiniciar o serviço do agente de integridade, conclua o procedimento a seguir no computador do Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="37bfc-133">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="37bfc-134">Clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique o botão direito no **Prompt de comando**, e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-134">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="37bfc-135">Na janela do console, digite o seguinte comando e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="37bfc-135">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="37bfc-p107">Você verá uma mensagem que diz "O serviço de Gerenciamento do 	Gerenciamento do System Center está sendo interrompido", seguida por uma segunda mensagem que diz que o serviço foi interrompido. Após a interrupção do serviço, você pode reiniciá-lo digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="37bfc-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="37bfc-138">Substituição do Candidato a Descoberta Central no Pacote de Gerenciamento do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="37bfc-138">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="37bfc-139">Depois de instruir um computador do Lync Server 2010 para relatar nos computadores do Lync Server 2010, você precisará informar o pacote de gerenciamento do Lync Server 2010 sobre essa alteração também.</span><span class="sxs-lookup"><span data-stu-id="37bfc-139">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="37bfc-140">Para fazer isso, será necessário criar uma substituição no Pacote de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="37bfc-140">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="37bfc-141">Isso pode ser feito realizando o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="37bfc-141">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="37bfc-142">No console do Operations Manager, clique em **Criação**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-142">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="37bfc-143">Na guia Criação, expanda **Objetos do Pacote de Gerenciamento**, clique em **Descobertas de Objeto**, e depois em **Escopo**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-143">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="37bfc-144">Na caixa de diálogo **Delimitar Objetos do Pacote de Gerenciamento**, selecione o item com o **Candidato à descoberta LS** do alvo e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-144">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="37bfc-145">Observe que o candidato à descoberta de LS aparecerá somente se você tiver instalado o pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37bfc-145">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="37bfc-146">No console do Operations Manager, clique com o botão direito em **Candidato à descoberta LS**, aponte para **Substituições**, aponte para **Substituir a Descoberta de Objeto**, e clique em **Para todos os objetos da classe: Candidato à descoberta LS**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-146">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="37bfc-147">Na caixa de diálogo **Substituir propriedades**, marque a caixa de seleção **Substituir** ao lado do parâmetro **WatcherNode Fqdn da Descoberta Central**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-147">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="37bfc-148">Digite o nome de domínio totalmente qualificado do computador do Lync Server 2010 nas caixas **valor de substituição** e **valor efetivo** .</span><span class="sxs-lookup"><span data-stu-id="37bfc-148">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="37bfc-149">Marque a caixa de seleção **Imposto** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-149">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="37bfc-p111">Após criar a substituição, será necessário reiniciar o serviço de integridade no Servidor de Gerenciamento Raiz. Para reiniciar o serviço Agente de Integridade, siga o procedimento a seguir no Servidor de Gerenciamento Raiz:</span><span class="sxs-lookup"><span data-stu-id="37bfc-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="37bfc-152">Clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique o botão direito no **Prompt de comando**, e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-152">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="37bfc-153">Na janela do console, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="37bfc-153">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="37bfc-p112">Você verá uma mensagem que diz "O serviço de Gerenciamento do 	Gerenciamento do System Center está sendo interrompido", seguida por uma segunda mensagem que diz que o serviço foi interrompido. Após a interrupção do serviço, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="37bfc-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="37bfc-156">Verificação se o novo Candidato a Descoberta Central foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="37bfc-156">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="37bfc-157">A etapa final antes de atualizar o repositório de gerenciamento central é verificar se o novo candidato de descoberta central foi descoberto pelo pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37bfc-157">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="37bfc-158">Para isso, abra o console do Operations Manager e clique em Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="37bfc-158">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="37bfc-159">Na guia Monitoramento, expanda **Integridade do Microsoft Lync Server 2010**, expanda **Descoberta de topologia** e depois clique em **Exibição do estado de descoberta**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-159">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="37bfc-160">Verifique se uma linha na exibição tem o **Caminho** que lista o nome de domínio totalmente qualificado do candidato à descoberta central.</span><span class="sxs-lookup"><span data-stu-id="37bfc-160">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="37bfc-161">Você também deve verificar se o estado do computador é relatado como **Íntegro**.</span><span class="sxs-lookup"><span data-stu-id="37bfc-161">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

