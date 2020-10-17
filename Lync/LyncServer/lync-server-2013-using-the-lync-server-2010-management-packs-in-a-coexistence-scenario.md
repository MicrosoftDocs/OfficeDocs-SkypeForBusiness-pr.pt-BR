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
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529918"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="e0eec-102">Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência</span><span class="sxs-lookup"><span data-stu-id="e0eec-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0eec-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e0eec-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e0eec-104">Muitos clientes adotam um programa de distribuição dentro de suas empresas nas quais os usuários são migrados progressivamente do Microsoft Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0eec-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="e0eec-105">Os administradores dessas empresas se preocupam em monitorar as duas versões do Lync Server para ajudar a garantir que todos os usuários finais estejam obtendo a melhor experiência de comunicação possível.</span><span class="sxs-lookup"><span data-stu-id="e0eec-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="e0eec-106">Para este cenário, o pacote de gerenciamento do Lync Server 2013 oferece suporte a um caminho de migração lado a lado com o pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0eec-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="e0eec-107">No Lync Server 2010, os computadores do Lync Server foram detectados pelo documento de topologia armazenado com o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="e0eec-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="e0eec-108">Nessa configuração, um único computador reportaria a existência de todos os outros computadores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0eec-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="e0eec-109">Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta no nível de máquina em vez do mecanismo de descoberta central usado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0eec-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="e0eec-110">Isso significa que cada agente do System Center, descobre essencialmente a si mesmo e relata sua existência ao System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="e0eec-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="e0eec-111">O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do System Center e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir com mais facilidade.</span><span class="sxs-lookup"><span data-stu-id="e0eec-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="e0eec-112">Para dar suporte a essa migração, primeiro você precisará atualizar seu monitoramento existente do Lync Server 2010 para evitar lacunas de cobertura.</span><span class="sxs-lookup"><span data-stu-id="e0eec-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="e0eec-113">Para fazer isso, elege um computador existente do Lync Server 2010 para atender ao script de descoberta central do Lync Server 2010 antes de atualizar seu repositório de gerenciamento central para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0eec-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="e0eec-114">Este é um processo em quatro etapas:</span><span class="sxs-lookup"><span data-stu-id="e0eec-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="e0eec-115">Atualize os pacotes de gerenciamento do Lync Server 2010 para a atualização cumulativa 7.</span><span class="sxs-lookup"><span data-stu-id="e0eec-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="e0eec-116">Instrua um computador do Lync Server 2010 para executar o script de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="e0eec-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="e0eec-117">Substitua o candidato de descoberta central no pacote de gerenciamento do Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0eec-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="e0eec-118">Verifique se o novo Candidato a Descoberta Central foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="e0eec-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="e0eec-119">Instrua um computador com Lync Server 2010 para executar o script de Descoberta Central</span><span class="sxs-lookup"><span data-stu-id="e0eec-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="e0eec-120">Para indicar um computador do repositório de gerenciamento não central (por exemplo, um servidor front-end do Lync Server) para lidar com a descoberta central, você precisará criar a seguinte chave do registro no servidor do repositório de gerenciamento não central:</span><span class="sxs-lookup"><span data-stu-id="e0eec-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="e0eec-121">\\CentralDiscoveryCandidate de \\ \\ integridade de comunicação em tempo real da Microsoft \\ \\</span><span class="sxs-lookup"><span data-stu-id="e0eec-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="e0eec-122">Você pode instalar criar essa chave de registro concluindo o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="e0eec-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="e0eec-123">Clique em **Iniciar** e depois em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="e0eec-124">Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e0eec-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="e0eec-125">No editor do registro, expanda \*\* \_ \_ máquina local de hKey\*\*, expanda **software**, expanda **Microsoft**e, em seguida, expanda **comunicação em tempo real**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="e0eec-p105">Com o botão direito em **Integridade**, clique em **Novo**, e depois em **Chave**. Se a chave **Integridade** não existir, clique com o botão direito em **Comunicações em tempo real**, aponte para **Novo**, e depois clique em **Chave**. Quando a nova chave for criada, digite Integridade, e depois pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e0eec-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="e0eec-129">Depois que a nova chave for criada, digite **CentralDiscoveryCandidate** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="e0eec-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="e0eec-130">Pode levar algumas horas para que o computador obtenha essa alteração.</span><span class="sxs-lookup"><span data-stu-id="e0eec-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="e0eec-131">Para atualizar essas configurações imediatamente, pare e em seguida reinicie o serviço Agente de Integridade.</span><span class="sxs-lookup"><span data-stu-id="e0eec-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="e0eec-132">Para reiniciar o serviço do agente de integridade, conclua o procedimento a seguir no computador do Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="e0eec-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="e0eec-133">Clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique o botão direito no **Prompt de comando**, e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e0eec-134">Na janela do console, digite o seguinte comando e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e0eec-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="e0eec-p107">Você verá uma mensagem que diz "O serviço de Gerenciamento do 	Gerenciamento do System Center está sendo interrompido", seguida por uma segunda mensagem que diz que o serviço foi interrompido. Após a interrupção do serviço, você pode reiniciá-lo digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="e0eec-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="e0eec-137">Substituição do Candidato a Descoberta Central no Pacote de Gerenciamento do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e0eec-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="e0eec-138">Depois de instruir um computador do Lync Server 2010 para relatar nos computadores do Lync Server 2010, você precisará informar o pacote de gerenciamento do Lync Server 2010 sobre essa alteração também.</span><span class="sxs-lookup"><span data-stu-id="e0eec-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="e0eec-139">Para fazer isso, será necessário criar uma substituição no Pacote de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="e0eec-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="e0eec-140">Isso pode ser feito realizando o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="e0eec-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="e0eec-141">No console do Operations Manager, clique em **Criação**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="e0eec-142">Na guia Criação, expanda **Objetos do Pacote de Gerenciamento**, clique em **Descobertas de Objeto**, e depois em **Escopo**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="e0eec-143">Na caixa de diálogo **Delimitar Objetos do Pacote de Gerenciamento**, selecione o item com o **Candidato à descoberta LS** do alvo e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="e0eec-144">Observe que o candidato à descoberta de LS aparecerá somente se você tiver instalado o pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0eec-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="e0eec-145">No console do Operations Manager, clique com o botão direito em **Candidato à descoberta LS**, aponte para **Substituições**, aponte para **Substituir a Descoberta de Objeto**, e clique em **Para todos os objetos da classe: Candidato à descoberta LS**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="e0eec-146">Na caixa de diálogo **Substituir propriedades**, marque a caixa de seleção **Substituir** ao lado do parâmetro **WatcherNode Fqdn da Descoberta Central**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="e0eec-147">Digite o nome de domínio totalmente qualificado do computador do Lync Server 2010 nas caixas **valor de substituição** e **valor efetivo** .</span><span class="sxs-lookup"><span data-stu-id="e0eec-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="e0eec-148">Marque a caixa de seleção **Imposto** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="e0eec-p111">Após criar a substituição, será necessário reiniciar o serviço de integridade no Servidor de Gerenciamento Raiz. Para reiniciar o serviço Agente de Integridade, siga o procedimento a seguir no Servidor de Gerenciamento Raiz:</span><span class="sxs-lookup"><span data-stu-id="e0eec-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="e0eec-151">Clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique o botão direito no **Prompt de comando**, e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e0eec-152">Na janela do console, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e0eec-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="e0eec-p112">Você verá uma mensagem que diz "O serviço de Gerenciamento do 	Gerenciamento do System Center está sendo interrompido", seguida por uma segunda mensagem que diz que o serviço foi interrompido. Após a interrupção do serviço, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="e0eec-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="e0eec-155">Verificação se o novo Candidato a Descoberta Central foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="e0eec-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="e0eec-156">A etapa final antes de atualizar o repositório de gerenciamento central é verificar se o novo candidato de descoberta central foi descoberto pelo pacote de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0eec-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="e0eec-157">Para isso, abra o console do Operations Manager e clique em Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="e0eec-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="e0eec-158">Na guia Monitoramento, expanda **Integridade do Microsoft Lync Server 2010**, expanda **Descoberta de topologia** e depois clique em **Exibição do estado de descoberta**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="e0eec-159">Verifique se uma linha na exibição tem o **Caminho** que lista o nome de domínio totalmente qualificado do candidato à descoberta central.</span><span class="sxs-lookup"><span data-stu-id="e0eec-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="e0eec-160">Você também deve verificar se o estado do computador é relatado como **Íntegro**.</span><span class="sxs-lookup"><span data-stu-id="e0eec-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

