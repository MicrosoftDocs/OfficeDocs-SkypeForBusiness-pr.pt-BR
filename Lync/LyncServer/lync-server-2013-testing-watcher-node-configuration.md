---
title: 'Lync Server 2013: testar a configuração do nó do Inspetor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d2c79de4f86e490244ef63948c263d8f387fc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="bf980-102">Testando a configuração do nó do Inspetor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf980-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf980-103">_**Tópico da última modificação:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="bf980-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf980-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="bf980-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bf980-105">Diário</span><span class="sxs-lookup"><span data-stu-id="bf980-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf980-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="bf980-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bf980-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf980-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf980-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="bf980-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bf980-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bf980-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bf980-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="bf980-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="bf980-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bf980-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bf980-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="bf980-112">Description</span></span>

<span data-ttu-id="bf980-113">Se estiver usando o Microsoft System Center Operations Manager para monitorar o Lync Server 2013, você tem a opção de configurar "nós de Inspetor": computadores que periodicamente e automaticamente executam transações sintéticas para verificar se o Lync Server está funcionando como esperado.</span><span class="sxs-lookup"><span data-stu-id="bf980-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="bf980-114">Os nós de Inspetor são atribuídos a pools e são gerenciados usando-se os cmdlets **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bf980-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="bf980-115">Observe que você não precisa instalar nós do Inspetor se estiver usando o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bf980-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="bf980-116">Você ainda pode monitorar o sistema sem usar nós de Inspetor.</span><span class="sxs-lookup"><span data-stu-id="bf980-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="bf980-117">A única diferença é que as transações sintéticas que você deseja executar devem ser invocadas manualmente em vez de invocadas automaticamente pelo Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bf980-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="bf980-118">O cmdlet **Test-CsWatcherNodeConfiguration** permite que você verifique se um nó do inspetor foi configurado corretamente e se foi atribuído a um pool válido do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf980-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="bf980-119">Observe que o cmdlet **Test-CsWatcherNodeConfiguration** deve ser executado no próprio nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="bf980-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="bf980-120">O cmdlet não pode ser executado em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="bf980-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bf980-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="bf980-121">Running the test</span></span>

<span data-ttu-id="bf980-122">O comando a seguir verifica as definições de configuração para cada nó do inspetor que está sendo usado na organização.</span><span class="sxs-lookup"><span data-stu-id="bf980-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bf980-123">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="bf980-123">Determining success or failure</span></span>

<span data-ttu-id="bf980-124">A seguinte saída de exemplo a seguir mostra um sistema com quatro servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="bf980-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="bf980-125">Validando o pool de destino atl-cs-001.litwareinc.com em relação à topologia.</span><span class="sxs-lookup"><span data-stu-id="bf980-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="bf980-126">Êxito: o pool de destino atl-cs-001.litwareinc.com existe na topologia.</span><span class="sxs-lookup"><span data-stu-id="bf980-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="bf980-127">Êxito: o pool de destino atl-cs-001.litwareinc.com tem a função de registrador instalada.</span><span class="sxs-lookup"><span data-stu-id="bf980-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="bf980-128">Êxito: versão do pool de destino atl-cs-001.litwareinc.com com suporte.</span><span class="sxs-lookup"><span data-stu-id="bf980-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="bf980-129">Êxito: o número da porta para o pool de destino do 5061 atl-cs-001.litwareinc.com está correto.</span><span class="sxs-lookup"><span data-stu-id="bf980-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="bf980-130">A verificação de pools ausentes na configuração do nó do Inspetor é iniciada.</span><span class="sxs-lookup"><span data-stu-id="bf980-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="bf980-131">Se for detectado algum erro, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="bf980-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="bf980-132">A verificação de pools ausentes na configuração do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="bf980-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="bf980-133">A verificação de chaves do registro do nó do Inspetor criadas pela instalação do nó do Inspetor é iniciada.</span><span class="sxs-lookup"><span data-stu-id="bf980-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="bf980-134">Se for detectado algum erro, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="bf980-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="bf980-135">A verificação das chaves do registro do nó do Inspetor criadas pela instalação do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="bf980-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="bf980-136">O tipo de autenticação detectado é Negotiate.</span><span class="sxs-lookup"><span data-stu-id="bf980-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="bf980-137">Existência validada com êxito da credencial do usuário de teste SIP: Usuário1 @ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="bf980-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="bf980-138">Existência validada com êxito da credencial do usuário de teste SIP: user2 @ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="bf980-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="bf980-139">A verificação de pools ausentes na configuração do nó do Inspetor é iniciada.</span><span class="sxs-lookup"><span data-stu-id="bf980-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="bf980-140">Se for detectado algum erro, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="bf980-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="bf980-141">Aviso: o pool atl-cs-001.litwareinc.com tem registrador</span><span class="sxs-lookup"><span data-stu-id="bf980-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="bf980-142">função instalada, mas não há usuários de teste configurados para ele.</span><span class="sxs-lookup"><span data-stu-id="bf980-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="bf980-143">A verificação de pools ausentes na configuração do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="bf980-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="bf980-144">Verificar as chaves do registro do nó do Inspetor criadas pela instalação do nó do Inspetor é</span><span class="sxs-lookup"><span data-stu-id="bf980-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="bf980-145">vindo.</span><span class="sxs-lookup"><span data-stu-id="bf980-145">started.</span></span> <span data-ttu-id="bf980-146">Se for detectado algum erro, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="bf980-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="bf980-147">Test-CsWatcherNodeConfiguration: não é possível encontrar a chave do registro de integridade no</span><span class="sxs-lookup"><span data-stu-id="bf980-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="bf980-148">Software\\de\\comunicação em tempo real da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf980-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="bf980-149">Verifique se o nó inspetor. msi está</span><span class="sxs-lookup"><span data-stu-id="bf980-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="bf980-150">instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="bf980-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bf980-151">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="bf980-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="bf980-152">Aqui estão alguns motivos comuns pelos quais **Test-CsWatcherNodeConfiguration** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="bf980-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="bf980-153">O nó do inspetor não está instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="bf980-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="bf980-154">Nenhum usuário de teste está configurado.</span><span class="sxs-lookup"><span data-stu-id="bf980-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf980-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf980-155">See Also</span></span>


[<span data-ttu-id="bf980-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf980-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="bf980-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf980-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="bf980-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf980-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="bf980-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf980-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

