---
title: 'Lync Server 2013: testar a configuração do nó do Inspetor'
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
ms.openlocfilehash: a52b251f238b8d79602e5fe1bf2803902cbae23f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503808"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="4a5dc-102">Testando a configuração do nó do Inspetor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a5dc-102">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5dc-103">_**Última modificação do tópico:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="4a5dc-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a5dc-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="4a5dc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4a5dc-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="4a5dc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a5dc-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="4a5dc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4a5dc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a5dc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a5dc-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="4a5dc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4a5dc-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4a5dc-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="4a5dc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="4a5dc-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a5dc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4a5dc-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="4a5dc-112">Description</span></span>

<span data-ttu-id="4a5dc-113">Se estiver usando o Microsoft System Center Operations Manager para monitorar o Lync Server 2013, você terá a opção de configurar "nós do Inspetor": computadores que periodicamente, e automaticamente, executam transações sintéticas para verificar se o Lync Server está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="4a5dc-114">Os nós do Inspetor são atribuídos a pools e são gerenciados usando os cmdlets **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4a5dc-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="4a5dc-115">Observe que você não precisa instalar nós do observador se estiver usando o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="4a5dc-116">Você ainda pode monitorar o sistema sem usar nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="4a5dc-117">A única diferença é que todas as transações sintéticas que você deseja executar devem ser chamadas manualmente em vez de invocadas automaticamente pelo Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="4a5dc-118">O cmdlet **Test-CsWatcherNodeConfiguration** permite verificar se um nó do inspetor foi configurado corretamente e é atribuído a um pool válido do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="4a5dc-119">Observe que o cmdlet **Test-CsWatcherNodeConfiguration** deve ser executado no próprio nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="4a5dc-120">O cmdlet não pode ser executado em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4a5dc-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="4a5dc-121">Running the test</span></span>

<span data-ttu-id="4a5dc-122">O comando a seguir verifica as definições de configuração para cada nó do inspetor que está sendo usado na organização.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4a5dc-123">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="4a5dc-123">Determining success or failure</span></span>

<span data-ttu-id="4a5dc-124">A saída de exemplo a seguir mostra um sistema com quatro servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="4a5dc-125">Validar o pool de destino atl-cs-001.litwareinc.com em relação à topologia.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="4a5dc-126">Êxito: o pool de destino atl-cs-001.litwareinc.com existe na topologia.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="4a5dc-127">Êxito: o pool de destino atl-cs-001.litwareinc.com tem a função de registrador instalada.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="4a5dc-128">Êxito: versão do pool de destino atl-cs-001.litwareinc.com suportada.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="4a5dc-129">Êxito: o número da porta para o pool de destino 5061 atl-cs-001.litwareinc.com está correto.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="4a5dc-130">A verificação de pools ausentes na configuração do nó do inspetor foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="4a5dc-131">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="4a5dc-132">A verificação de pools ausentes na configuração do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="4a5dc-133">A verificação das chaves do registro do nó do observador criadas pela instalação do nó do observador, será iniciada.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="4a5dc-134">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="4a5dc-135">A verificação das chaves do registro do nó do observador criadas pela instalação do nó do observador foi concluída.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="4a5dc-136">O tipo de autenticação detectado é Negotiate.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="4a5dc-137">Existência validada com êxito da credencial do usuário de teste SIP: user1@ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="4a5dc-138">Existência validada com êxito da credencial do usuário de teste SIP: user2@ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="4a5dc-139">A verificação de pools ausentes na configuração do nó do inspetor foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="4a5dc-140">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="4a5dc-141">Aviso: o pool atl-cs-001.litwareinc.com tem o registrador</span><span class="sxs-lookup"><span data-stu-id="4a5dc-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="4a5dc-142">função instalada, mas não há usuários de teste configurados para ele.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="4a5dc-143">A verificação de pools ausentes na configuração do nó do inspetor está concluída.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="4a5dc-144">Verificar as chaves do registro do nó do observador criadas pela instalação do nó do observador, é</span><span class="sxs-lookup"><span data-stu-id="4a5dc-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="4a5dc-145">tiver.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-145">started.</span></span> <span data-ttu-id="4a5dc-146">Se algum erro for detectado, ele será impresso.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="4a5dc-147">Test-CsWatcherNodeConfiguration: não é possível encontrar a chave do registro de integridade no</span><span class="sxs-lookup"><span data-stu-id="4a5dc-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="4a5dc-148">\\Comunicação do software da Microsoft \\ em tempo real.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="4a5dc-149">Verifique se o nó do Inspetor. msi é</span><span class="sxs-lookup"><span data-stu-id="4a5dc-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="4a5dc-150">instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4a5dc-151">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="4a5dc-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="4a5dc-152">Aqui estão alguns motivos comuns pelos quais **Test-CsWatcherNodeConfiguration** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="4a5dc-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="4a5dc-153">O nó do inspetor não está instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="4a5dc-154">Nenhum usuário de teste está configurado.</span><span class="sxs-lookup"><span data-stu-id="4a5dc-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a5dc-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="4a5dc-155">See Also</span></span>


[<span data-ttu-id="4a5dc-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="4a5dc-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="4a5dc-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="4a5dc-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="4a5dc-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="4a5dc-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="4a5dc-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="4a5dc-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

