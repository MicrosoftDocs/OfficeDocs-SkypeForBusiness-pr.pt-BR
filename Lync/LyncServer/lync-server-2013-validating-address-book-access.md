---
title: 'Lync Server 2013: Validando o acesso ao catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="17322-102">Validando o acesso ao catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17322-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17322-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="17322-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17322-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="17322-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="17322-105">Diário</span><span class="sxs-lookup"><span data-stu-id="17322-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17322-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="17322-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="17322-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17322-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17322-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="17322-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="17322-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="17322-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="17322-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="17322-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="17322-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17322-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="17322-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="17322-112">Description</span></span>

<span data-ttu-id="17322-113">O cmdlet Test-CsAddressBookService fornece uma maneira de verificar se um usuário pode se conectar ao serviço Web de download do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="17322-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="17322-114">Quando você executa o cmdlet, Test-CsAddressBookService conecta-se ao serviço Web de download do catálogo de endereços no pool especificado e solicita o local dos arquivos do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="17322-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="17322-115">Se o serviço Web de download do catálogo de endereços fornecer essa localização, o teste será considerado com êxito.</span><span class="sxs-lookup"><span data-stu-id="17322-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="17322-116">Se a solicitação for negada, o teste será considerado uma falha.</span><span class="sxs-lookup"><span data-stu-id="17322-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="17322-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="17322-117">Running the test</span></span>

<span data-ttu-id="17322-118">O cmdlet Test-CsAddressBookService pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário que tenha sido habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17322-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="17322-119">Para executar essa verificação usando uma conta de teste, tudo o que você precisa fazer é especificar o nome de domínio totalmente qualificado (FQDN) do pool do servidor do Lync que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="17322-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="17322-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="17322-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="17322-121">Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="17322-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="17322-122">Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="17322-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="17322-123">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="17322-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="17322-124">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="17322-124">Determining success or failure</span></span>

<span data-ttu-id="17322-125">Se o usuário especificado for capaz de se conectar ao serviço de catálogo de endereços, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="17322-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="17322-126">TargetUri :https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="17322-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="17322-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="17322-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="17322-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="17322-128">Result : Success</span></span>

<span data-ttu-id="17322-129">Latência: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="17322-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="17322-130">Erros</span><span class="sxs-lookup"><span data-stu-id="17322-130">Error :</span></span>

<span data-ttu-id="17322-131">Correto</span><span class="sxs-lookup"><span data-stu-id="17322-131">Diagnosis :</span></span>

<span data-ttu-id="17322-132">Se o usuário especificado não puder fazer essa conexão, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="17322-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="17322-133">TargetUri :</span><span class="sxs-lookup"><span data-stu-id="17322-133">TargetUri :</span></span>

<span data-ttu-id="17322-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="17322-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="17322-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="17322-135">Result : Failure</span></span>

<span data-ttu-id="17322-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="17322-136">Latency : 00:00:00</span></span>

<span data-ttu-id="17322-137">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="17322-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="17322-138">Motivo = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="17322-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="17322-139">Existem.</span><span class="sxs-lookup"><span data-stu-id="17322-139">exist.</span></span>

<span data-ttu-id="17322-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="17322-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="17322-141">Por exemplo, a saída anterior informa que o teste falhou porque o usuário especificado (isto é, o "URI de destino") não existe ou não foi habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17322-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="17322-142">Você pode verificar se uma conta de usuário é válida e se você forneceu o endereço SIP correto executando um comando como este:</span><span class="sxs-lookup"><span data-stu-id="17322-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="17322-143">Get-CsUser-identidade "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span><span class="sxs-lookup"><span data-stu-id="17322-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="17322-144">Se Test-CsAddressBookService falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="17322-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="17322-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-detalhado</span><span class="sxs-lookup"><span data-stu-id="17322-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="17322-146">Quando o parâmetro Verbose for incluído, Test-CsAddressBookService retornará uma conta passo a passo de cada ação tentada ao verificar a capacidade do usuário especificado de fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17322-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="17322-147">Por exemplo, esta saída de exemplo mostra que Test-CsAddressBookService, pelo menos neste exemplo, pôde baixar o arquivo do catálogo de endereços:</span><span class="sxs-lookup"><span data-stu-id="17322-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="17322-148">Enviando solicitação HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="17322-148">Sending Http GET Request.</span></span>

<span data-ttu-id="17322-149">Caminho do arquivo =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="17322-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="17322-150">Número da tentativa = 1</span><span class="sxs-lookup"><span data-stu-id="17322-150">Attempt Number = 1</span></span>

<span data-ttu-id="17322-151">Tempo limite (mseg) = 60000</span><span class="sxs-lookup"><span data-stu-id="17322-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="17322-152">O arquivo ABS foi baixado com êxitohttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="17322-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="17322-153">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="17322-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="17322-154">Aqui estão alguns motivos comuns pelos quais Test-CsAddressBookService pode falhar:</span><span class="sxs-lookup"><span data-stu-id="17322-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="17322-155">Você especificou uma conta de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="17322-155">You specified an invalid user account.</span></span> <span data-ttu-id="17322-156">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="17322-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="17322-157">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17322-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="17322-158">Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="17322-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="17322-159">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17322-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17322-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="17322-160">See Also</span></span>


[<span data-ttu-id="17322-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="17322-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

