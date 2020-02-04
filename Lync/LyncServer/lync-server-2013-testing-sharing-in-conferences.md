---
title: 'Lync Server 2013: testando o compartilhamento em conferências'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54997f5ec8cd81154c1a456541ec0612187ec747
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="010c5-102">Testando o compartilhamento em conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="010c5-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="010c5-103">_**Tópico da última modificação:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="010c5-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="010c5-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="010c5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="010c5-105">Diário</span><span class="sxs-lookup"><span data-stu-id="010c5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="010c5-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="010c5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="010c5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="010c5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="010c5-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="010c5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="010c5-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="010c5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="010c5-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDataConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="010c5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="010c5-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="010c5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="010c5-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="010c5-112">Description</span></span>

<span data-ttu-id="010c5-113">No Lync Server 2013, uma conferência de dados é qualquer conferência na qual atividades colaborativas, como quadros de comunicações ou anotações, são usadas.</span><span class="sxs-lookup"><span data-stu-id="010c5-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="010c5-114">O cmdlet **Test-CsDataConference** permite que você verifique se um par de usuários consegue participar de uma conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="010c5-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="010c5-115">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="010c5-115">Running the test</span></span>

<span data-ttu-id="010c5-116">O comando mostrado no exemplo 1 verifica se uma conferência de dados pode ser conduzida na atl-cs-001.litwareinc.com do pool.</span><span class="sxs-lookup"><span data-stu-id="010c5-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="010c5-117">Esse comando pressupõe que você configurou um par de usuários de teste para o pool especificado.</span><span class="sxs-lookup"><span data-stu-id="010c5-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="010c5-118">Se não houver esses usuários de teste, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="010c5-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="010c5-119">Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e conduzir uma conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="010c5-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="010c5-120">Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do pilar do usuário Alverca.</span><span class="sxs-lookup"><span data-stu-id="010c5-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="010c5-121">(Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige apenas que o administrador insira a senha da conta pilar Alverca.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="010c5-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="010c5-122">O segundo comando faz a mesma coisa, desta vez retornando um objeto Credential para a conta Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="010c5-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="010c5-123">Com os objetos de credenciais em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e conduzir uma conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="010c5-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="010c5-124">Para executar essa tarefa, o cmdlet **Test-CsDataConference** é chamado, juntamente com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto do Windows PowerShell que contém as credenciais para esse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto do Windows PowerShell que contém as credenciais do outro usuário de teste).</span><span class="sxs-lookup"><span data-stu-id="010c5-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="010c5-125">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="010c5-125">Determining success or failure</span></span>

<span data-ttu-id="010c5-126">Se a conferência de dados estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="010c5-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="010c5-127">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="010c5-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="010c5-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="010c5-128">Result : Success</span></span>

<span data-ttu-id="010c5-129">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="010c5-129">Latency : 00:00:00</span></span>

<span data-ttu-id="010c5-130">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="010c5-130">Error Message :</span></span>

<span data-ttu-id="010c5-131">Correto</span><span class="sxs-lookup"><span data-stu-id="010c5-131">Diagnosis :</span></span>

<span data-ttu-id="010c5-132">Se os usuários especificados não conseguirem usar o compartilhamento de dados, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="010c5-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="010c5-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="010c5-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="010c5-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="010c5-134">Result : Failure</span></span>

<span data-ttu-id="010c5-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="010c5-135">Latency : 00:00:00</span></span>

<span data-ttu-id="010c5-136">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="010c5-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="010c5-137">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="010c5-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="010c5-138">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="010c5-138">established connection failed because connected host has</span></span>

<span data-ttu-id="010c5-139">Falha ao responder \[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="010c5-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="010c5-140">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="010c5-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="010c5-141">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="010c5-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="010c5-142">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="010c5-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="010c5-143">Não respondeu</span><span class="sxs-lookup"><span data-stu-id="010c5-143">has failed to respond</span></span>

<span data-ttu-id="010c5-144">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="010c5-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="010c5-145">Correto</span><span class="sxs-lookup"><span data-stu-id="010c5-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="010c5-146">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="010c5-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="010c5-147">Aqui estão alguns motivos comuns pelos quais **Test-CsDataConference** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="010c5-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="010c5-148">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="010c5-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="010c5-149">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="010c5-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="010c5-150">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="010c5-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="010c5-151">A capacidade de conduzir uma conferência de dados depende da política de conferência que foi atribuída ao usuário que organizou a conferência (no caso do cmdlet **Test-CsDataConference** , que é o "remetente").</span><span class="sxs-lookup"><span data-stu-id="010c5-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="010c5-152">Se o organizador não puder incluir atividades colaborativas em sua reunião (por exemplo, se a política de conferência tiver a propriedade EnableDataCollaboration definida como false), o cmdlet **Test-CsDataConference** falhará.</span><span class="sxs-lookup"><span data-stu-id="010c5-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="010c5-153">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="010c5-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

