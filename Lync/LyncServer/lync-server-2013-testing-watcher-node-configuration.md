---
title: 'Lync Server 2013: testar a configuração do nó do Inspetor'
description: 'Lync Server 2013: testar a configuração do nó do observador.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546837"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="c8cea-103">Testando a configuração do nó do Inspetor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8cea-103">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8cea-104">_**Última modificação do tópico:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c8cea-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8cea-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="c8cea-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c8cea-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="c8cea-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cea-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="c8cea-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c8cea-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8cea-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8cea-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="c8cea-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c8cea-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c8cea-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c8cea-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="c8cea-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="c8cea-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8cea-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c8cea-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8cea-113">Description</span></span>

<span data-ttu-id="c8cea-114">Se estiver usando o Microsoft System Center Operations Manager para monitorar o Lync Server 2013, você terá a opção de configurar "nós do Inspetor": computadores que periodicamente, e automaticamente, executam transações sintéticas para verificar se o Lync Server está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="c8cea-114">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="c8cea-115">Os nós do Inspetor são atribuídos a pools e são gerenciados usando os cmdlets **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c8cea-115">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="c8cea-116">Observe que você não precisa instalar nós do observador se estiver usando o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c8cea-116">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="c8cea-117">Você ainda pode monitorar o sistema sem usar nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="c8cea-117">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="c8cea-118">A única diferença é que todas as transações sintéticas que você deseja executar devem ser chamadas manualmente em vez de invocadas automaticamente pelo Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c8cea-118">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="c8cea-119">O cmdlet **Test-CsWatcherNodeConfiguration** permite verificar se um nó do inspetor foi configurado corretamente e é atribuído a um pool válido do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8cea-119">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="c8cea-120">Observe que o cmdlet **Test-CsWatcherNodeConfiguration** deve ser executado no próprio nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="c8cea-120">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="c8cea-121">O cmdlet não pode ser executado em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="c8cea-121">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c8cea-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="c8cea-122">Running the test</span></span>

<span data-ttu-id="c8cea-123">O comando a seguir verifica as definições de configuração para cada nó do inspetor que está sendo usado na organização.</span><span class="sxs-lookup"><span data-stu-id="c8cea-123">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c8cea-124">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="c8cea-124">Determining success or failure</span></span>

<span data-ttu-id="c8cea-125">A saída de exemplo a seguir mostra um sistema com quatro servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="c8cea-125">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="c8cea-126">Validar o pool de destino atl-cs-001.litwareinc.com em relação à topologia.</span><span class="sxs-lookup"><span data-stu-id="c8cea-126">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="c8cea-127">Êxito: o pool de destino atl-cs-001.litwareinc.com existe na topologia.</span><span class="sxs-lookup"><span data-stu-id="c8cea-127">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="c8cea-128">Êxito: o pool de destino atl-cs-001.litwareinc.com tem a função de registrador instalada.</span><span class="sxs-lookup"><span data-stu-id="c8cea-128">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="c8cea-129">Êxito: versão do pool de destino atl-cs-001.litwareinc.com suportada.</span><span class="sxs-lookup"><span data-stu-id="c8cea-129">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="c8cea-130">Êxito: o número da porta para o pool de destino 5061 atl-cs-001.litwareinc.com está correto.</span><span class="sxs-lookup"><span data-stu-id="c8cea-130">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="c8cea-131">A verificação de pools ausentes na configuração do nó do inspetor foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="c8cea-131">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="c8cea-132">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="c8cea-132">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c8cea-133">A verificação de pools ausentes na configuração do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="c8cea-133">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="c8cea-134">A verificação das chaves do registro do nó do observador criadas pela instalação do nó do observador, será iniciada.</span><span class="sxs-lookup"><span data-stu-id="c8cea-134">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="c8cea-135">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="c8cea-135">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c8cea-136">A verificação das chaves do registro do nó do observador criadas pela instalação do nó do observador foi concluída.</span><span class="sxs-lookup"><span data-stu-id="c8cea-136">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="c8cea-137">O tipo de autenticação detectado é Negotiate.</span><span class="sxs-lookup"><span data-stu-id="c8cea-137">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="c8cea-138">Existência validada com êxito da credencial do usuário de teste SIP: user1@ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="c8cea-138">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="c8cea-139">Existência validada com êxito da credencial do usuário de teste SIP: user2@ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="c8cea-139">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="c8cea-140">A verificação de pools ausentes na configuração do nó do inspetor foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="c8cea-140">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="c8cea-141">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="c8cea-141">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c8cea-142">Aviso: o pool atl-cs-001.litwareinc.com tem o registrador</span><span class="sxs-lookup"><span data-stu-id="c8cea-142">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="c8cea-143">função instalada, mas não há usuários de teste configurados para ele.</span><span class="sxs-lookup"><span data-stu-id="c8cea-143">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="c8cea-144">A verificação de pools ausentes na configuração do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="c8cea-144">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="c8cea-145">Verificar as chaves do registro do nó do observador criadas pela instalação do nó do observador, é</span><span class="sxs-lookup"><span data-stu-id="c8cea-145">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="c8cea-146">tiver.</span><span class="sxs-lookup"><span data-stu-id="c8cea-146">started.</span></span> <span data-ttu-id="c8cea-147">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="c8cea-147">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="c8cea-148">Test-CsWatcherNodeConfiguration: não é possível encontrar a chave do registro de integridade no</span><span class="sxs-lookup"><span data-stu-id="c8cea-148">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="c8cea-149">\\Comunicação do software da Microsoft \\ em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c8cea-149">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="c8cea-150">Verifique se o nó do Inspetor. msi é</span><span class="sxs-lookup"><span data-stu-id="c8cea-150">Make sure watcher node .msi is</span></span>

<span data-ttu-id="c8cea-151">instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="c8cea-151">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c8cea-152">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="c8cea-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="c8cea-153">Aqui estão alguns motivos comuns pelos quais **Test-CsWatcherNodeConfiguration** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="c8cea-153">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="c8cea-154">O nó do inspetor não está instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="c8cea-154">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="c8cea-155">Nenhum usuário de teste está configurado.</span><span class="sxs-lookup"><span data-stu-id="c8cea-155">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8cea-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="c8cea-156">See Also</span></span>


[<span data-ttu-id="c8cea-157">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8cea-157">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="c8cea-158">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8cea-158">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="c8cea-159">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8cea-159">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="c8cea-160">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8cea-160">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

