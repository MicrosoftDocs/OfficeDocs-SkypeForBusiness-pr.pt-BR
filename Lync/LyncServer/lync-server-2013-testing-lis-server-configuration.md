---
title: 'Lync Server 2013: testar configuração do servidor de LIS'
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
ms.openlocfilehash: 50b2908b3f2403cc59f4cb7ce26f176d366ce2e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="3bc4d-102">Testando a configuração do servidor LIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc4d-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bc4d-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3bc4d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bc4d-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="3bc4d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3bc4d-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="3bc4d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc4d-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="3bc4d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3bc4d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bc4d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bc4d-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="3bc4d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3bc4d-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3bc4d-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="3bc4d-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3bc4d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="3bc4d-112">Description</span></span>

<span data-ttu-id="3bc4d-113">O cmdlet Test-CsLisConfiguration verifica sua capacidade de entrar em contato com o serviço Web LIS.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="3bc4d-114">Se o serviço Web puder ser contatado, o teste será considerado um sucesso, independente de qualquer local específico ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3bc4d-115">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="3bc4d-115">Running the test</span></span>

<span data-ttu-id="3bc4d-116">O cmdlet Test-CsLisConfguration pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="3bc4d-117">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3bc4d-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3bc4d-119">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="3bc4d-120">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="3bc4d-121">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3bc4d-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3bc4d-122">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="3bc4d-122">Determining success or failure</span></span>

<span data-ttu-id="3bc4d-123">Se o LIS estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="3bc4d-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3bc4d-124">TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="3bc4d-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="3bc4d-125">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="3bc4d-125">liservice.svc</span></span>

<span data-ttu-id="3bc4d-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3bc4d-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3bc4d-127">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="3bc4d-127">Result : Success</span></span>

<span data-ttu-id="3bc4d-128">Latência: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="3bc4d-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="3bc4d-129">Erros</span><span class="sxs-lookup"><span data-stu-id="3bc4d-129">Error :</span></span>

<span data-ttu-id="3bc4d-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3bc4d-130">Diagnosis :</span></span>

<span data-ttu-id="3bc4d-131">Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como falha, e as informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3bc4d-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="3bc4d-132">TargetUri :</span></span>

<span data-ttu-id="3bc4d-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3bc4d-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3bc4d-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="3bc4d-134">Result : Failure</span></span>

<span data-ttu-id="3bc4d-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3bc4d-135">Latency : 00:00:00</span></span>

<span data-ttu-id="3bc4d-136">Erro: 11004, o nome solicitado é válido, mas nenhum dado do pedido</span><span class="sxs-lookup"><span data-stu-id="3bc4d-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="3bc4d-137">o tipo foi encontrado</span><span class="sxs-lookup"><span data-stu-id="3bc4d-137">type was found</span></span>

<span data-ttu-id="3bc4d-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3bc4d-138">Diagnosis :</span></span>

<span data-ttu-id="3bc4d-139">Test-CsLisConfiguration: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="3bc4d-140">Por exemplo, a saída anterior inclui a observação "nenhum cluster correspondente encontrado na topologia".</span><span class="sxs-lookup"><span data-stu-id="3bc4d-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="3bc4d-141">Isso geralmente indica um problema com o servidor de borda: o LIS usando o servidor de borda para se conectar ao provedor de serviços e validar os endereços.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="3bc4d-142">Se Test-CsLisConfiguration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="3bc4d-143">Quando o parâmetro Verbose é incluído, o Test-CsLisConfiguration retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="3bc4d-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-144">For example:</span></span>

<span data-ttu-id="3bc4d-145">Chamando o serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-145">Calling Location Information Service.</span></span>

<span data-ttu-id="3bc4d-146">Caminho do serviço =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="3bc4d-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="3bc4d-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="3bc4d-147">Subnet =</span></span>

<span data-ttu-id="3bc4d-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="3bc4d-148">BssId = 5</span></span>

<span data-ttu-id="3bc4d-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="3bc4d-149">ChassisId =</span></span>

<span data-ttu-id="3bc4d-150">Portid =</span><span class="sxs-lookup"><span data-stu-id="3bc4d-150">PortId =</span></span>

<span data-ttu-id="3bc4d-151">PortIdSubType = tipo indefinido</span><span class="sxs-lookup"><span data-stu-id="3bc4d-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="3bc4d-152">Mac</span><span class="sxs-lookup"><span data-stu-id="3bc4d-152">Mac</span></span>

<span data-ttu-id="3bc4d-153">Uma exceção de solicitação de serviço Web de informações de local falhou com um código de resposta Item400. '</span><span class="sxs-lookup"><span data-stu-id="3bc4d-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="3bc4d-154">ocorrido durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="3bc4d-155">Se você examinar o resultado anterior de perto, verá que o cmdlet falhou após ele tentar chamar o serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="3bc4d-156">Um dos parâmetros usados nesta chamada foi o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="3bc4d-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="3bc4d-157">BssId = 5</span></span>

<span data-ttu-id="3bc4d-158">Esse não é um valor válido para o identificador de conjunto de serviços básico (BssID).</span><span class="sxs-lookup"><span data-stu-id="3bc4d-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="3bc4d-159">Em vez disso, um BssID deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="3bc4d-160">12-34-56-78-90-AB</span><span class="sxs-lookup"><span data-stu-id="3bc4d-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3bc4d-161">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="3bc4d-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="3bc4d-162">Aqui estão alguns motivos comuns pelos quais Test-CsLisConfiguration pode falhar:</span><span class="sxs-lookup"><span data-stu-id="3bc4d-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="3bc4d-163">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3bc4d-164">Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3bc4d-165">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="3bc4d-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

