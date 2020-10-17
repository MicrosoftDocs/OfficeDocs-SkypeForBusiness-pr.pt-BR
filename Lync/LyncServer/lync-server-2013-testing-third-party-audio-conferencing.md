---
title: 'Lync Server 2013: testar audioconferência de áudio de terceiros'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51f728bfb5617185bdd9a1ef3b5f21b3e12ca61f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503928"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="9db93-102">Testando a conferência de áudio de terceiros no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9db93-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9db93-103">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="9db93-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9db93-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="9db93-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9db93-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="9db93-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db93-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="9db93-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9db93-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9db93-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db93-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="9db93-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9db93-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9db93-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9db93-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="9db93-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="9db93-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9db93-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9db93-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9db93-112">Description</span></span>

<span data-ttu-id="9db93-p102">Um provedor de conferência de áudio é uma empresa terceirizada que oferece serviços de conferências para a organização. Entre outras coisas, os provedores de conferência de áudio permitem os usuários fora do local e não conectados à rede empresarial ou Internet participarem da parte de áudio de uma conferência ou reunião. Os provedores de conferência de áudio frequentemente oferecem serviços de alta tecnologia como conversão ao vivo, transcrição e assistência ao operador por conferência.</span><span class="sxs-lookup"><span data-stu-id="9db93-p102">An audio conferencing provider is a third-party company that provides organizations with conferencing services. Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting. Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="9db93-116">O cmdlet **Test-CsAudioConferencingProvider** é usado para verificar se um usuário é capaz de fazer uma conexão com seu provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9db93-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="9db93-117">Observe que este cmdlet pode ser executado em uma das duas formas.</span><span class="sxs-lookup"><span data-stu-id="9db93-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="9db93-118">Vários administradores usarão os cmdlets CsHealthMonitoringConfiguration para configurar usuários de teste para cada um de seus pools do Registrador.</span><span class="sxs-lookup"><span data-stu-id="9db93-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="9db93-119">Estes usuários de teste representam um par de contas de usuário pré-configurados para uso com transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="9db93-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="9db93-120">(Normalmente, são contas de teste e não contas que pertencem a usuários reais.) Se os usuários de teste estiverem configurados para um pool, os administradores poderão executar o cmdlet **Test-CsAudioConferencingProvider** nesse pool, sem ter que especificar a identidade (e fornecer as credenciais) da conta de usuário envolvida no teste.</span><span class="sxs-lookup"><span data-stu-id="9db93-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="9db93-121">Como alternativa, os administradores podem executar o cmdlet **Test-CsAudioConferencingProvider** usando uma conta de usuário real.</span><span class="sxs-lookup"><span data-stu-id="9db93-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="9db93-122">Se você optar por conduzir um teste usando uma conta de usuário real, será necessário fornecer o nome de logon e a senha dessa conta.</span><span class="sxs-lookup"><span data-stu-id="9db93-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9db93-123">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="9db93-123">Running the test</span></span>

<span data-ttu-id="9db93-124">O Exemplo 1 verifica se um usuário de teste definido para o pool atl-cs-001.litwareinc.com pode se conectar ao provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9db93-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="9db93-125">Este comando exige que pelo menos um usuário de teste seja definido para o pool.</span><span class="sxs-lookup"><span data-stu-id="9db93-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="9db93-126">Se nenhum usuário de teste tiver sido definido para o atl-cs-001.litwareinc.com, o comando irá falhar; Isso ocorre porque o cmdlet **Test-CsAudioConferencingProvider** não sabe qual usuário empregar no teste.</span><span class="sxs-lookup"><span data-stu-id="9db93-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="9db93-127">Se você não definiu os usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais da conta de usuário que o comando deve implantar ao verificar a conexão com um provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9db93-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="9db93-128">Os comandos mostrados no exemplo 2 testam a capacidade de um usuário específico (litwareinc \\ kenmyer) para se conectar ao seu provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9db93-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="9db93-129">Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell contendo o nome e a senha do usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="9db93-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="9db93-130">(Como o nome de logon litwareinc \\ kenmyer foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta Ken Myer.) O objeto de credenciais resultante é armazenado em uma variável chamada $credential.</span><span class="sxs-lookup"><span data-stu-id="9db93-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="9db93-131">O segundo comando verifica se este usuário pode se conectar ao provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9db93-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="9db93-132">Para realizar essa tarefa, o cmdlet Test-CsAudioConferencingProvider é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registradores); Usercredential (o objeto Windows PowerShell que contém as credenciais de usuário de Ken Myer); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).</span><span class="sxs-lookup"><span data-stu-id="9db93-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9db93-133">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="9db93-133">Determining success or failure</span></span>

<span data-ttu-id="9db93-134">Se o provedor de serviços de audioconferência estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="9db93-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9db93-135">FQDN de destino: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9db93-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="9db93-136">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="9db93-136">Result : Success</span></span>

<span data-ttu-id="9db93-137">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9db93-137">Latency : 00:00:00</span></span>

<span data-ttu-id="9db93-138">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="9db93-138">Error Message :</span></span>

<span data-ttu-id="9db93-139">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9db93-139">Diagnosis :</span></span>

<span data-ttu-id="9db93-140">Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como uma **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="9db93-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9db93-141">FQDN de destino: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9db93-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="9db93-142">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="9db93-142">Result : Failure</span></span>

<span data-ttu-id="9db93-143">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9db93-143">Latency : 00:00:00</span></span>

<span data-ttu-id="9db93-144">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="9db93-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="9db93-145">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="9db93-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="9db93-146">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="9db93-146">established connection failed because connected host has</span></span>

<span data-ttu-id="9db93-147">Falha ao responder \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944: \] 5061</span><span class="sxs-lookup"><span data-stu-id="9db93-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="9db93-148">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="9db93-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="9db93-149">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="9db93-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="9db93-150">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="9db93-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="9db93-151">falhou ao responder</span><span class="sxs-lookup"><span data-stu-id="9db93-151">has failed to respond</span></span>

<span data-ttu-id="9db93-152">\[2001:4898: E8: f39e: 5c9a: ad83:81b3: \] 5061</span><span class="sxs-lookup"><span data-stu-id="9db93-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="9db93-153">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9db93-153">Diagnosis :</span></span>

<span data-ttu-id="9db93-154">Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="9db93-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9db93-155">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="9db93-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="9db93-156">Aqui estão alguns motivos comuns pelos quais **Test-CsAudioConferencingProvider** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="9db93-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="9db93-157">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="9db93-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9db93-158">Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="9db93-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9db93-159">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="9db93-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9db93-160">Observe que o teste falhará se o usuário empregado pelo cmdlet **Test-CsAudioConferencingProvider** não tiver sido atribuído um provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9db93-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="9db93-161">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="9db93-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

