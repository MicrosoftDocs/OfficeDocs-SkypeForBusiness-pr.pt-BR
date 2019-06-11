---
title: 'Lync Server 2013: Validando a consulta à Web do catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="ed998-102">Validando a consulta da Web do catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed998-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed998-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ed998-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed998-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="ed998-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ed998-105">Diário</span><span class="sxs-lookup"><span data-stu-id="ed998-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed998-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="ed998-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ed998-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed998-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed998-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="ed998-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ed998-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ed998-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ed998-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="ed998-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="ed998-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ed998-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ed998-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed998-112">Description</span></span>

<span data-ttu-id="ed998-113">O cmdlet Test-CsAddressBookWebQuery permite que os administradores verifiquem se os usuários podem usar o serviço de consulta à Web do catálogo de endereços para pesquisar um contato específico.</span><span class="sxs-lookup"><span data-stu-id="ed998-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="ed998-114">Quando você executar o cmdlet, Test-CsAddressBookWebQuery primeiro se conectará ao serviço de tíquete da Web para ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="ed998-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="ed998-115">Se a autenticação for bem-sucedida, o cmdlet se conectará ao serviço de consulta à Web do catálogo de endereços e pesquisará o contato especificado.</span><span class="sxs-lookup"><span data-stu-id="ed998-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="ed998-116">Se esse contato for encontrado, o cmdlet tentará retornar essas informações para o computador local.</span><span class="sxs-lookup"><span data-stu-id="ed998-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="ed998-117">O teste será marcado como sucesso apenas se todas essas etapas puderem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="ed998-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="ed998-118">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="ed998-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ed998-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="ed998-119">Running the test</span></span>

<span data-ttu-id="ed998-120">O cmdlet Test-CsAddressBookWebQuery pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed998-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="ed998-121">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync e o endereço SIP do usuário que atua como o destino da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ed998-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="ed998-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ed998-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="ed998-123">Para executar essa verificação usando uma conta de usuário real, você deve criar um objeto de credenciais do Windows PowerShell que contenha um nome de usuário e senha válidos.</span><span class="sxs-lookup"><span data-stu-id="ed998-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="ed998-124">Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta quando o código chamar Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="ed998-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="ed998-125">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="ed998-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ed998-126">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="ed998-126">Determining success or failure</span></span>

<span data-ttu-id="ed998-127">Se o usuário especificado puder se conectar ao serviço de catálogo de endereços e recuperar o endereço de usuário direcionado, você retornará uma saída semelhante a isso com a propriedade Result marcada como Success:</span><span class="sxs-lookup"><span data-stu-id="ed998-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="ed998-128">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="ed998-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="ed998-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed998-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ed998-130">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="ed998-130">Result : Success</span></span>

<span data-ttu-id="ed998-131">Latência: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="ed998-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="ed998-132">Erros</span><span class="sxs-lookup"><span data-stu-id="ed998-132">Error :</span></span>

<span data-ttu-id="ed998-133">Correto</span><span class="sxs-lookup"><span data-stu-id="ed998-133">Diagnosis :</span></span>

<span data-ttu-id="ed998-134">Se o usuário especificado não puder se conectar ou se o endereço de usuário de destino não puder ser recuperado, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="ed998-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ed998-135">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="ed998-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="ed998-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed998-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ed998-137">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="ed998-137">Result : Failure</span></span>

<span data-ttu-id="ed998-138">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ed998-138">Latency : 00:00:00</span></span>

<span data-ttu-id="ed998-139">Erro: falha na solicitação de serviço Web de catálogo de endereços com código de resposta</span><span class="sxs-lookup"><span data-stu-id="ed998-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="ed998-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="ed998-140">NoEntryFound.</span></span>

<span data-ttu-id="ed998-141">Correto</span><span class="sxs-lookup"><span data-stu-id="ed998-141">Diagnosis :</span></span>

<span data-ttu-id="ed998-142">A saída anterior informa que o teste falhou porque o usuário de destino não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="ed998-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="ed998-143">Você pode determinar se um endereço SIP válido foi passado para Test-CsAddressBookWebQuery executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ed998-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="ed998-144">Se Test-CsAddressBookWebQuery falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="ed998-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="ed998-145">Quando o parâmetro Verbose estiver incluído, Test-CsAddressBookWebQuery retornará uma conta passo a passo de cada ação que ele tentou ao verificar a capacidade do usuário especificado de fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed998-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ed998-146">Por exemplo, essa saída indica que Test-CsAddressBookWebQuery foi capaz de se conectar ao serviço de catálogo de endereços, mas não pôde localizar o endereço SIP de destino:</span><span class="sxs-lookup"><span data-stu-id="ed998-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="ed998-147">Atividade "QueryAddressBookWebService" iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed998-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="ed998-148">Fazendo chamadas para o serviço de consulta da Web Catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="ed998-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="ed998-149">URL ABWS =</span><span class="sxs-lookup"><span data-stu-id="ed998-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="ed998-150">Exceção de consulta do catálogo de endereços: falha na solicitação de serviço Web do catálogo de endereços com o código de resposta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="ed998-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ed998-151">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="ed998-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="ed998-152">Aqui estão alguns motivos comuns pelos quais Test-CsAddressBookWebQuery pode falhar:</span><span class="sxs-lookup"><span data-stu-id="ed998-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="ed998-153">Você especificou uma conta de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="ed998-153">You specified an invalid user account.</span></span> <span data-ttu-id="ed998-154">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ed998-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ed998-155">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed998-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="ed998-156">Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ed998-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="ed998-157">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed998-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="ed998-158">O usuário de destino pode não estar no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="ed998-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="ed998-159">O catálogo de endereços pode não ter sido totalmente atualizado e replicado.</span><span class="sxs-lookup"><span data-stu-id="ed998-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="ed998-160">Você pode forçar uma atualização de todos os servidores de catálogo de endereços em sua organização executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="ed998-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

