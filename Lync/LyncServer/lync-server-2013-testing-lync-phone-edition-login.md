---
title: 'Lync Server 2013: testar o logon do Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce22e6c7f5fb48132f3f67c79c33daaa568d93ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="91acd-102">Testando o logon do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91acd-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91acd-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="91acd-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91acd-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="91acd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="91acd-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="91acd-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91acd-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="91acd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="91acd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91acd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91acd-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="91acd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="91acd-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="91acd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="91acd-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="91acd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="91acd-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="91acd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="91acd-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="91acd-112">Description</span></span>

<span data-ttu-id="91acd-113">O cmdlet Test-CsPhoneBootstrap permite que os administradores verifiquem se um determinado usuário, usando o número de telefone e o PIN atribuído a ele, podem fazer logon no sistema de um dispositivo compatível com Lync 2013 Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="91acd-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="91acd-114">(Nenhum dispositivo é realmente necessário para executar o teste).</span><span class="sxs-lookup"><span data-stu-id="91acd-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="91acd-115">Para que Test-CsPhoneBootstrap possa realizar essa verificação, é necessário que o pool de registradores que hospeda a conta do usuário testada seja detectável usando-se o DHCP.</span><span class="sxs-lookup"><span data-stu-id="91acd-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="91acd-116">Para determinar se um registrador é detectável dessa maneira, use o cmdlet Get-CsRegistrarConfiguration e verifique o valor da propriedade EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="91acd-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="91acd-117">Se essa propriedade for definida como false, você deverá usar set-CsRegistrarConfiguration para definir o valor da propriedade como true e tornar o registrador detectável usando DHCP.</span><span class="sxs-lookup"><span data-stu-id="91acd-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="91acd-118">Isso também pode ser feito usando o servidor DHCP corporativo e configurando as opções específicas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91acd-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="91acd-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="91acd-119">Running the test</span></span>

<span data-ttu-id="91acd-120">Para executar o cmdlet Test-CsPhoneBootstrap, você deve, no mínimo, fornecer o número de telefone e o PIN (número de identificação pessoal) do cliente para um usuário válido do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91acd-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="91acd-121">Por exemplo, este comando testa a capacidade de logon do usuário que possui o número de telefone 12065551219 e o PIN 0712:</span><span class="sxs-lookup"><span data-stu-id="91acd-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="91acd-122">Para uma verificação mais abrangente, você também pode incluir o endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="91acd-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="91acd-123">Nesse caso, o número de telefone, PIN do cliente e endereço SIP devem ser válidos para que o teste seja bem-sucedido:</span><span class="sxs-lookup"><span data-stu-id="91acd-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="91acd-124">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="91acd-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="91acd-125">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="91acd-125">Determining success or failure</span></span>

<span data-ttu-id="91acd-126">Se o usuário especificado foi capaz de se conectar ao Lync Server, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="91acd-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="91acd-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="91acd-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="91acd-128">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="91acd-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="91acd-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91acd-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91acd-130">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="91acd-130">Result : Success</span></span>

<span data-ttu-id="91acd-131">Latência: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="91acd-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="91acd-132">Erros</span><span class="sxs-lookup"><span data-stu-id="91acd-132">Error :</span></span>

<span data-ttu-id="91acd-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="91acd-133">Diagnosis :</span></span>

<span data-ttu-id="91acd-134">Se o usuário especificado não foi capaz de fazer uma conexão, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="91acd-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="91acd-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="91acd-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="91acd-136">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="91acd-136">Result : Failure</span></span>

<span data-ttu-id="91acd-137">Latência: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="91acd-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="91acd-138">Erro: erro-nenhuma resposta recebida para o serviço de tíquete da Web.</span><span class="sxs-lookup"><span data-stu-id="91acd-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="91acd-139">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="91acd-139">Diagnosis :</span></span>

<span data-ttu-id="91acd-140">A saída anterior indica que o teste falhou porque o serviço de tíquete da Web não respondeu.</span><span class="sxs-lookup"><span data-stu-id="91acd-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="91acd-141">Isso pode ser devido a um problema com o serviço em si ou pode ser devido ao endereço SIP, número de telefone ou PIN do cliente passado para Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="91acd-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="91acd-142">Você pode verificar o endereço SIP do usuário e o número de telefone usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="91acd-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="91acd-143">E você pode verificar se o usuário tem um PIN válido usando um comando da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="91acd-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="91acd-144">Se Test-CsPhoneBootstrap falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="91acd-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="91acd-145">Quando o parâmetro Verbose é incluído, o Test-CsPhoneBootstrap retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91acd-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="91acd-146">Por exemplo, aqui está uma parte da saída de um logon não bem-sucedido, uma sessão na qual um PIN incorreto foi incluído:</span><span class="sxs-lookup"><span data-stu-id="91acd-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="91acd-147">Usando o PIN auth com\\ramal de telefone: 12065551219 PIN: 0712</span><span class="sxs-lookup"><span data-stu-id="91acd-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="91acd-148">Não foi possível obter o tíquete da Web</span><span class="sxs-lookup"><span data-stu-id="91acd-148">Could not get web ticket</span></span>

<span data-ttu-id="91acd-149">Fira</span><span class="sxs-lookup"><span data-stu-id="91acd-149">CHECK :</span></span>

<span data-ttu-id="91acd-150">\-A URL do serviço Web é válida e os serviços Web são funcionais</span><span class="sxs-lookup"><span data-stu-id="91acd-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="91acd-151">\-Se estiver usando\\o PIN PhoneNo para autenticação, certifique-se de que eles correspondam ao URI do usuário</span><span class="sxs-lookup"><span data-stu-id="91acd-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="91acd-152">\-Se estiver usando\\a autenticação Kerberos NTLM, certifique-se de ter fornecido credenciais válidas</span><span class="sxs-lookup"><span data-stu-id="91acd-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="91acd-153">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="91acd-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="91acd-154">Aqui estão alguns motivos comuns pelos quais Test-CsPhoneBootstrap pode falhar:</span><span class="sxs-lookup"><span data-stu-id="91acd-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="91acd-155">Você pode ter especificado um endereço SIP que não é válido.</span><span class="sxs-lookup"><span data-stu-id="91acd-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="91acd-156">Você pode verificar se um endereço SIP está correto usando um comando como este:</span><span class="sxs-lookup"><span data-stu-id="91acd-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="91acd-157">Você pode ter especificado um PIN que não é válido.</span><span class="sxs-lookup"><span data-stu-id="91acd-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="91acd-158">Embora não seja possível recuperar o número PIN do usuário, você pode verificar se o usuário pelo menos tem um número PIN usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="91acd-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="91acd-159">Você pode ter especificado um número de telefone que não seja válido.</span><span class="sxs-lookup"><span data-stu-id="91acd-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="91acd-160">Você pode verificar o telefone de um usuário usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="91acd-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="91acd-161">O pool de registradores não está habilitado para DHCP.</span><span class="sxs-lookup"><span data-stu-id="91acd-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="91acd-162">Para determinar se o seu pool de registradores está habilitado para DHCP, execute o cmdlet Get-CsRegistrarConfiguration e verifique o valor da propriedade EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="91acd-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="91acd-163">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="91acd-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

