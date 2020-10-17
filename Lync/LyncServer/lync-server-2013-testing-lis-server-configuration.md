---
title: 'Lync Server 2013: testar configuração do servidor de LIS'
description: 'Lync Server 2013: testar configuração do servidor de LIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560607"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="5f4fa-103">Testando a configuração do servidor LIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f4fa-103">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f4fa-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5f4fa-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f4fa-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="5f4fa-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5f4fa-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="5f4fa-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f4fa-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="5f4fa-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5f4fa-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f4fa-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f4fa-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="5f4fa-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5f4fa-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5f4fa-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="5f4fa-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5f4fa-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f4fa-113">Description</span></span>

<span data-ttu-id="5f4fa-114">O cmdlet Test-CsLisConfiguration verifica sua capacidade de entrar em contato com o serviço Web LIS.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-114">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="5f4fa-115">Se o serviço Web puder ser contatado, o teste será considerado um sucesso, independente de qualquer local específico ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-115">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5f4fa-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="5f4fa-116">Running the test</span></span>

<span data-ttu-id="5f4fa-117">O cmdlet Test-CsLisConfguration pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-117">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="5f4fa-118">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-118">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="5f4fa-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-119">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="5f4fa-120">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="5f4fa-121">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-121">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="5f4fa-122">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5f4fa-122">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5f4fa-123">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="5f4fa-123">Determining success or failure</span></span>

<span data-ttu-id="5f4fa-124">Se o LIS estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="5f4fa-124">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5f4fa-125">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="5f4fa-125">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="5f4fa-126">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="5f4fa-126">liservice.svc</span></span>

<span data-ttu-id="5f4fa-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f4fa-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f4fa-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="5f4fa-128">Result : Success</span></span>

<span data-ttu-id="5f4fa-129">Latência: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="5f4fa-129">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="5f4fa-130">Erros</span><span class="sxs-lookup"><span data-stu-id="5f4fa-130">Error :</span></span>

<span data-ttu-id="5f4fa-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f4fa-131">Diagnosis :</span></span>

<span data-ttu-id="5f4fa-132">Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como falha, e as informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-132">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5f4fa-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="5f4fa-133">TargetUri :</span></span>

<span data-ttu-id="5f4fa-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f4fa-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f4fa-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="5f4fa-135">Result : Failure</span></span>

<span data-ttu-id="5f4fa-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5f4fa-136">Latency : 00:00:00</span></span>

<span data-ttu-id="5f4fa-137">Erro: 11004, o nome solicitado é válido, mas nenhum dado do pedido</span><span class="sxs-lookup"><span data-stu-id="5f4fa-137">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="5f4fa-138">o tipo foi encontrado</span><span class="sxs-lookup"><span data-stu-id="5f4fa-138">type was found</span></span>

<span data-ttu-id="5f4fa-139">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f4fa-139">Diagnosis :</span></span>

<span data-ttu-id="5f4fa-140">Test-CsLisConfiguration: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-140">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="5f4fa-141">Por exemplo, a saída anterior inclui a observação "nenhum cluster correspondente encontrado na topologia".</span><span class="sxs-lookup"><span data-stu-id="5f4fa-141">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="5f4fa-142">Isso geralmente indica um problema com o servidor de borda: o LIS usando o servidor de borda para se conectar ao provedor de serviços e validar os endereços.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-142">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="5f4fa-143">Se Test-CsLisConfiguration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-143">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="5f4fa-144">Quando o parâmetro Verbose é incluído, Test-CsLisConfiguration retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-144">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="5f4fa-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-145">For example:</span></span>

<span data-ttu-id="5f4fa-146">Chamando o serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-146">Calling Location Information Service.</span></span>

<span data-ttu-id="5f4fa-147">Caminho do serviço = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="5f4fa-147">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="5f4fa-148">Subnet =</span><span class="sxs-lookup"><span data-stu-id="5f4fa-148">Subnet =</span></span>

<span data-ttu-id="5f4fa-149">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="5f4fa-149">BssId = 5</span></span>

<span data-ttu-id="5f4fa-150">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="5f4fa-150">ChassisId =</span></span>

<span data-ttu-id="5f4fa-151">Portid =</span><span class="sxs-lookup"><span data-stu-id="5f4fa-151">PortId =</span></span>

<span data-ttu-id="5f4fa-152">PortIdSubType = tipo indefinido</span><span class="sxs-lookup"><span data-stu-id="5f4fa-152">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="5f4fa-153">Mac</span><span class="sxs-lookup"><span data-stu-id="5f4fa-153">Mac</span></span>

<span data-ttu-id="5f4fa-154">Uma exceção de solicitação de serviço Web de informações de local falhou com um código de resposta Item400. '</span><span class="sxs-lookup"><span data-stu-id="5f4fa-154">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="5f4fa-155">ocorrido durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-155">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="5f4fa-156">Se você examinar o resultado anterior de perto, verá que o cmdlet falhou após ele tentar chamar o serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-156">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="5f4fa-157">Um dos parâmetros usados nesta chamada foi o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-157">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="5f4fa-158">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="5f4fa-158">BssId = 5</span></span>

<span data-ttu-id="5f4fa-159">Esse não é um valor válido para o identificador de conjunto de serviços básico (BssID).</span><span class="sxs-lookup"><span data-stu-id="5f4fa-159">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="5f4fa-160">Em vez disso, um BssID deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-160">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="5f4fa-161">12-34-56-78-90-AB</span><span class="sxs-lookup"><span data-stu-id="5f4fa-161">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5f4fa-162">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="5f4fa-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="5f4fa-163">Aqui estão alguns motivos comuns para que Test-CsLisConfiguration possa falhar:</span><span class="sxs-lookup"><span data-stu-id="5f4fa-163">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="5f4fa-164">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-164">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5f4fa-165">Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-165">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5f4fa-166">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-166">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

