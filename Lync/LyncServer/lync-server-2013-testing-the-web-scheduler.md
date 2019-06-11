---
title: 'Lync Server 2013: testando o Agendador da Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="8c330-102">Testando o Agendador da Web no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c330-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c330-103">_**Tópico da última modificação:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="8c330-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c330-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="8c330-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8c330-105">Diário</span><span class="sxs-lookup"><span data-stu-id="8c330-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c330-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="8c330-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8c330-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c330-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c330-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="8c330-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8c330-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8c330-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8c330-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="8c330-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="8c330-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8c330-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8c330-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c330-112">Description</span></span>

<span data-ttu-id="8c330-113">O cmdlet **Test-CsWebScheduler** permite que você determine se um usuário específico pode agendar uma reunião usando o Web scheduler.</span><span class="sxs-lookup"><span data-stu-id="8c330-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="8c330-114">O Web Scheduler permite que os usuários que não estão executando o Outlook agendem reuniões online.</span><span class="sxs-lookup"><span data-stu-id="8c330-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="8c330-115">Entre outras coisas, esse novo recurso (que incorpora a funcionalidade encontrada na ferramenta do Agendador da Web incluída com o Microsoft Lync Server 2010 Resource Kit) permite que os usuários:</span><span class="sxs-lookup"><span data-stu-id="8c330-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="8c330-116">Agendar uma nova reunião online.</span><span class="sxs-lookup"><span data-stu-id="8c330-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="8c330-117">Listar todas as reuniões agendadas por ele ou ela.</span><span class="sxs-lookup"><span data-stu-id="8c330-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="8c330-118">Exibir/modificar uma reunião existente.</span><span class="sxs-lookup"><span data-stu-id="8c330-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="8c330-119">Excluir uma reunião existente.</span><span class="sxs-lookup"><span data-stu-id="8c330-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="8c330-120">Envie um convite por email para os participantes da reunião usando um servidor de email SMTP pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="8c330-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="8c330-121">Ingressar em uma conferência existente.</span><span class="sxs-lookup"><span data-stu-id="8c330-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8c330-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="8c330-122">Running the test</span></span>

<span data-ttu-id="8c330-123">O exemplo a seguir verifica o Agendador da Web para o conjunto de atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8c330-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="8c330-124">Esse comando funcionará apenas se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8c330-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="8c330-125">Se eles tiverem, o comando determinará se o primeiro usuário de teste pode agendar uma reunião online usando o Web scheduler.</span><span class="sxs-lookup"><span data-stu-id="8c330-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="8c330-126">Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário deve fazer logon.</span><span class="sxs-lookup"><span data-stu-id="8c330-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="8c330-127">Se você não definiu usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar quando tentar fazer logon.</span><span class="sxs-lookup"><span data-stu-id="8c330-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="8c330-128">Os comandos mostrados no próximo exemplo testam a capacidade de um usuário específico (\\litwareinc kenmeyer) agendar uma reunião online usando o Web scheduler.</span><span class="sxs-lookup"><span data-stu-id="8c330-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="8c330-129">Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contém o nome e a senha do usuário Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="8c330-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="8c330-130">(Como o nome de logon\\litwareinc kenmeyer está incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador digite a senha da conta Ken Meyer.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="8c330-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="8c330-131">Em seguida, o segundo comando verifica se este usuário pode fazer logon no pool atl-cs-001.litwareinc.com e agendar uma reunião online.</span><span class="sxs-lookup"><span data-stu-id="8c330-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="8c330-132">Para executar essa tarefa, o cmdlet **Test-CsWebScheduler** é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registrador); Usercredential (o objeto do Windows PowerShell que contém as credenciais de usuário de pilar Alverca); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).</span><span class="sxs-lookup"><span data-stu-id="8c330-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8c330-133">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="8c330-133">Determining success or failure</span></span>

<span data-ttu-id="8c330-134">Se o Web Scheduler estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="8c330-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="8c330-135">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8c330-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8c330-136">URI de destino: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8c330-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="8c330-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="8c330-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="8c330-138">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="8c330-138">Result : Success</span></span>

<span data-ttu-id="8c330-139">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8c330-139">Latency : 00:00:00</span></span>

<span data-ttu-id="8c330-140">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="8c330-140">Error Message :</span></span>

<span data-ttu-id="8c330-141">Correto</span><span class="sxs-lookup"><span data-stu-id="8c330-141">Diagnosis :</span></span>

<span data-ttu-id="8c330-142">Se o Web Scheduler não estiver configurado corretamente, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="8c330-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8c330-143">Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="8c330-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="8c330-144">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="8c330-144">domain name (FQDN).</span></span> <span data-ttu-id="8c330-145">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="8c330-145">Using default Registrar port number.</span></span> <span data-ttu-id="8c330-146">Extremamente</span><span class="sxs-lookup"><span data-stu-id="8c330-146">Exception:</span></span>

<span data-ttu-id="8c330-147">System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="8c330-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="8c330-148">como</span><span class="sxs-lookup"><span data-stu-id="8c330-148">at</span></span>

<span data-ttu-id="8c330-149">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="8c330-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="8c330-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="8c330-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="8c330-151">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8c330-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8c330-152">URI de destino:</span><span class="sxs-lookup"><span data-stu-id="8c330-152">Target Uri :</span></span>

<span data-ttu-id="8c330-153">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="8c330-153">Result : Failure</span></span>

<span data-ttu-id="8c330-154">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8c330-154">Latency : 00:00:00</span></span>

<span data-ttu-id="8c330-155">Mensagem de erro: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="8c330-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="8c330-156">Correto</span><span class="sxs-lookup"><span data-stu-id="8c330-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8c330-157">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="8c330-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="8c330-158">Aqui estão alguns motivos comuns pelos quais **Test-CsWebScheduler** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="8c330-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="8c330-159">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="8c330-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="8c330-160">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="8c330-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="8c330-161">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="8c330-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="8c330-162">Esse comando falhará se o Web Scheduler estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="8c330-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c330-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c330-163">See Also</span></span>


[<span data-ttu-id="8c330-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="8c330-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

