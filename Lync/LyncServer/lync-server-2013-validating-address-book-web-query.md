---
title: 'Lync Server 2013: Validando consulta da Web do catálogo de endereços'
description: 'Lync Server 2013: Validando consulta da Web do catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547247"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="8e2e0-103">Validando a consulta da Web do catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2e0-103">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e2e0-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8e2e0-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2e0-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="8e2e0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8e2e0-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="8e2e0-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2e0-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="8e2e0-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8e2e0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e2e0-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2e0-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="8e2e0-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8e2e0-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8e2e0-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="8e2e0-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8e2e0-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e2e0-113">Description</span></span>

<span data-ttu-id="8e2e0-114">O cmdlet Test-CsAddressBookWebQuery permite que os administradores verifiquem se os usuários podem usar o serviço de consulta da Web do catálogo de endereços para pesquisar um contato específico.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-114">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="8e2e0-115">Quando você executar o cmdlet, Test-CsAddressBookWebQuery primeiro se conectará ao serviço de tíquete da Web para ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-115">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="8e2e0-116">Se a autenticação for bem-sucedida, o cmdlet será conectado ao serviço de consulta à Web do catálogo de endereços e pesquisará o contato especificado.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-116">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="8e2e0-117">Se esse contato for encontrado, o cmdlet tentará retornar essas informações para o computador local.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-117">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="8e2e0-118">O teste será marcado como êxito apenas se todas as etapas puderem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-118">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="8e2e0-119">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="8e2e0-119">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8e2e0-120">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="8e2e0-120">Running the test</span></span>

<span data-ttu-id="8e2e0-121">O cmdlet Test-CsAddressBookWebQuery pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-121">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="8e2e0-122">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server e o endereço SIP do usuário que atua como o destino da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="8e2e0-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-123">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="8e2e0-124">Para executar essa verificação usando uma conta de usuário real, você deve criar um objeto de credenciais do Windows PowerShell que contenha um nome de usuário e uma senha válidos.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="8e2e0-125">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando o código chamar Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-125">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="8e2e0-126">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="8e2e0-126">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8e2e0-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="8e2e0-127">Determining success or failure</span></span>

<span data-ttu-id="8e2e0-128">Se o usuário especificado puder se conectar ao serviço de catálogo de endereços e recuperar o endereço de usuário de destino, você retornará uma saída semelhante a esta com a propriedade Result marcada como êxito:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-128">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="8e2e0-129">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8e2e0-129">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="8e2e0-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8e2e0-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8e2e0-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="8e2e0-131">Result : Success</span></span>

<span data-ttu-id="8e2e0-132">Latência: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="8e2e0-132">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="8e2e0-133">Erros</span><span class="sxs-lookup"><span data-stu-id="8e2e0-133">Error :</span></span>

<span data-ttu-id="8e2e0-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8e2e0-134">Diagnosis :</span></span>

<span data-ttu-id="8e2e0-135">Se o usuário especificado não puder se conectar ou se o endereço do usuário de destino não puder ser recuperado, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-135">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8e2e0-136">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8e2e0-136">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="8e2e0-137">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8e2e0-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8e2e0-138">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="8e2e0-138">Result : Failure</span></span>

<span data-ttu-id="8e2e0-139">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8e2e0-139">Latency : 00:00:00</span></span>

<span data-ttu-id="8e2e0-140">Erro: a solicitação de serviço Web do catálogo de endereços falhou com o código de resposta</span><span class="sxs-lookup"><span data-stu-id="8e2e0-140">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="8e2e0-141">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-141">NoEntryFound.</span></span>

<span data-ttu-id="8e2e0-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8e2e0-142">Diagnosis :</span></span>

<span data-ttu-id="8e2e0-143">A saída anterior indica que o teste falhou porque o usuário de destino não pôde ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-143">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="8e2e0-144">Você pode determinar se um endereço SIP válido foi ou não passado para Test-CsAddressBookWebQuery executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-144">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="8e2e0-145">Se Test-CsAddressBookWebQuery falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-145">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="8e2e0-146">Quando o parâmetro Verbose é incluído, Test-CsAddressBookWebQuery retornará uma conta passo a passo de cada ação que tentou ao verificar a capacidade do usuário especificado de fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-146">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="8e2e0-147">Por exemplo, essa saída indica que Test-CsAddressBookWebQuery foi capaz de se conectar ao serviço de catálogo de endereços, mas não pôde localizar o endereço SIP de destino:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-147">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="8e2e0-148">Atividade ' QueryAddressBookWebService ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-148">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="8e2e0-149">Chamando o serviço de consulta da Web do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-149">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="8e2e0-150">URL ABWS =</span><span class="sxs-lookup"><span data-stu-id="8e2e0-150">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="8e2e0-151">Exceção de consulta do catálogo de endereços: a solicitação de serviço Web do catálogo de endereços falhou com o código de resposta NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-151">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8e2e0-152">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="8e2e0-152">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="8e2e0-153">Aqui estão alguns motivos comuns para que Test-CsAddressBookWebQuery possa falhar:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-153">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="8e2e0-154">Você especificou uma conta de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-154">You specified an invalid user account.</span></span> <span data-ttu-id="8e2e0-155">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-155">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8e2e0-156">A conta de usuário é válida, mas a conta não está atualmente habilitada para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-156">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="8e2e0-157">Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-157">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="8e2e0-158">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-158">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="8e2e0-159">O usuário de destino pode não estar no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-159">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="8e2e0-160">O catálogo de endereços pode não ter sido totalmente atualizado e replicado.</span><span class="sxs-lookup"><span data-stu-id="8e2e0-160">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="8e2e0-161">Você pode forçar uma atualização de todos os servidores de catálogo de endereços em sua organização executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8e2e0-161">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

