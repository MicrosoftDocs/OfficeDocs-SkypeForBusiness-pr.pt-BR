---
title: 'Lync Server 2013: testando conferências de áudio de terceiros'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="f3c1b-102">Testar conferências de áudio de terceiros no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c1b-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3c1b-103">_**Tópico da última modificação:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3c1b-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c1b-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="f3c1b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f3c1b-105">Diário</span><span class="sxs-lookup"><span data-stu-id="f3c1b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c1b-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="f3c1b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f3c1b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3c1b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c1b-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f3c1b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f3c1b-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f3c1b-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="f3c1b-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f3c1b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f3c1b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3c1b-112">Description</span></span>

<span data-ttu-id="f3c1b-113">Um provedor de conferência de áudio é uma empresa de terceiros que oferece serviços de conferência às organizações.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="f3c1b-114">Entre outras coisas, os provedores de conferência de áudio permitem que usuários que estiverem longe do local e não conectados à rede corporativa ou pela Internet participem do áudio de uma conferência ou reunião.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="f3c1b-115">Geralmente, os provedores de audioconferência fornecem serviços de high-end, como a tradução ao vivo, a transcrição e a assistência ao vivo por conferência ao vivo.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="f3c1b-116">O cmdlet **Test-CsAudioConferencingProvider** é usado para verificar se um usuário consegue fazer uma conexão com seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="f3c1b-117">Observe que esse cmdlet pode ser executado de uma das duas maneiras.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="f3c1b-118">Muitos administradores usarão os cmdlets CsHealthMonitoringConfiguration para configurar usuários de teste para cada um dos seus pools de registradores.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="f3c1b-119">Esses usuários de teste representam um par de contas de usuário que foram pré-configuradas para uso com transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="f3c1b-120">(Geralmente são contas de teste e não contas que pertencem a usuários reais.) Se os usuários de teste estiverem configurados para um pool, os administradores poderão executar o cmdlet **Test-CsAudioConferencingProvider** nesse pool sem ter que especificar a identidade de (e fornecer as credenciais para) a conta de usuário envolvida no teste.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="f3c1b-121">Como alternativa, os administradores podem executar o cmdlet **Test-CsAudioConferencingProvider** usando uma conta de usuário real.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="f3c1b-122">Se você decidir conduzir o teste usando uma conta de usuário real, será necessário fornecer o nome de logon e a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f3c1b-123">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="f3c1b-123">Running the test</span></span>

<span data-ttu-id="f3c1b-124">O exemplo 1 verifica se um usuário de teste definido para o pool atl-cs-001.litwareinc.com é capaz de se conectar ao seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="f3c1b-125">Esse comando requer que pelo menos um usuário de teste seja definido para o pool.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="f3c1b-126">Se nenhum usuário de teste tiver sido definido para atl-cs-001.litwareinc.com, o comando irá falhar; Isso ocorre porque o cmdlet **Test-CsAudioConferencingProvider** não sabe qual o usuário empregar no teste.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="f3c1b-127">Se você não definiu usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais da conta de usuário que o comando deve empregar ao verificar a conexão com um provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="f3c1b-128">Os comandos mostrados no exemplo 2 testam a capacidade de um usuário específico\\(litwareinc kenmyer) para se conectar ao seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="f3c1b-129">Para fazer isso, o primeiro comando do exemplo usa o cmdlet Get-Credential para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell que contém o nome e a senha do usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="f3c1b-130">(Como o nome de logon\\litwareinc kenmyer foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador digite a senha para a conta Ken Myer.) O objeto de credenciais resultante é armazenado em uma variável chamada $credential.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="f3c1b-131">Em seguida, o segundo comando verifica se este usuário pode se conectar ao seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="f3c1b-132">Para executar essa tarefa, o cmdlet Test-CsAudioConferencingProvider é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registrador); Usercredential (o objeto do Windows PowerShell que contém as credenciais de usuário de Ken Myer); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).</span><span class="sxs-lookup"><span data-stu-id="f3c1b-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f3c1b-133">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="f3c1b-133">Determining success or failure</span></span>

<span data-ttu-id="f3c1b-134">Se o provedor de serviços de audioconferência estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="f3c1b-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f3c1b-135">FQDN de destino: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3c1b-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="f3c1b-136">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="f3c1b-136">Result : Success</span></span>

<span data-ttu-id="f3c1b-137">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f3c1b-137">Latency : 00:00:00</span></span>

<span data-ttu-id="f3c1b-138">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="f3c1b-138">Error Message :</span></span>

<span data-ttu-id="f3c1b-139">Correto</span><span class="sxs-lookup"><span data-stu-id="f3c1b-139">Diagnosis :</span></span>

<span data-ttu-id="f3c1b-140">Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="f3c1b-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f3c1b-141">FQDN de destino: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3c1b-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="f3c1b-142">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="f3c1b-142">Result : Failure</span></span>

<span data-ttu-id="f3c1b-143">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f3c1b-143">Latency : 00:00:00</span></span>

<span data-ttu-id="f3c1b-144">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="f3c1b-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="f3c1b-145">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="f3c1b-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="f3c1b-146">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="f3c1b-146">established connection failed because connected host has</span></span>

<span data-ttu-id="f3c1b-147">Falha ao responder \[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="f3c1b-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="f3c1b-148">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="f3c1b-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="f3c1b-149">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="f3c1b-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="f3c1b-150">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="f3c1b-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="f3c1b-151">Não respondeu</span><span class="sxs-lookup"><span data-stu-id="f3c1b-151">has failed to respond</span></span>

<span data-ttu-id="f3c1b-152">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="f3c1b-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="f3c1b-153">Correto</span><span class="sxs-lookup"><span data-stu-id="f3c1b-153">Diagnosis :</span></span>

<span data-ttu-id="f3c1b-154">Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f3c1b-155">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="f3c1b-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="f3c1b-156">Aqui estão alguns motivos comuns pelos quais **Test-CsAudioConferencingProvider** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="f3c1b-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="f3c1b-157">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f3c1b-158">Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f3c1b-159">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f3c1b-160">Observe que o teste falhará se o usuário empregado pelo cmdlet **Test-CsAudioConferencingProvider** não tiver sido atribuído um provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="f3c1b-161">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="f3c1b-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

