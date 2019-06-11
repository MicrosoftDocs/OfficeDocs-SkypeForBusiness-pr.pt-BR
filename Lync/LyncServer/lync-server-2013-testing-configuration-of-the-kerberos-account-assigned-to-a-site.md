---
title: Testando a configuração da conta Kerberos atribuída a um site
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="8d63f-102">Testando a configuração da conta Kerberos atribuída a um site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d63f-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d63f-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8d63f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d63f-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="8d63f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8d63f-105">Diário</span><span class="sxs-lookup"><span data-stu-id="8d63f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d63f-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="8d63f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8d63f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d63f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d63f-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="8d63f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8d63f-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8d63f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8d63f-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="8d63f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="8d63f-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d63f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8d63f-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d63f-112">Description</span></span>

<span data-ttu-id="8d63f-113">O cmdlet Test-CsKerberosAccountAssignment permite que você verifique se uma conta Kerberos está associada a um determinado site, se essa conta está configurada corretamente e se a conta está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="8d63f-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="8d63f-114">As contas Kerberos são contas de computador que podem servir como a entidade de autenticação para todos os computadores em um site que estejam executando o IIS (servidor de informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="8d63f-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="8d63f-115">Como essas contas usam o protocolo de autenticação Kerberos, as contas são conhecidas como contas Kerberos, e o novo processo de autenticação é conhecido como autenticação da Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8d63f-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="8d63f-116">Isso permite que você gerencie todos os servidores IIS usando uma única conta.</span><span class="sxs-lookup"><span data-stu-id="8d63f-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="8d63f-117">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8d63f-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8d63f-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="8d63f-118">Running the Test</span></span>

<span data-ttu-id="8d63f-119">Por padrão, Test-CsKerberosAccountAssignment exibe um pouco de saída na tela.</span><span class="sxs-lookup"><span data-stu-id="8d63f-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="8d63f-120">Em vez disso, as informações retornadas pelo cmdlet são gravadas em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="8d63f-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="8d63f-121">Por isso, recomendamos que você inclua o parâmetro Verbose e o parâmetro Report a qualquer momento que executar Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="8d63f-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="8d63f-122">O parâmetro Verbose fornecerá uma saída levemente mais detalhada na tela enquanto o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="8d63f-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="8d63f-123">O parâmetro Report permite que você especifique um caminho de arquivo e um nome de arquivo para o arquivo HTML gerado por Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="8d63f-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="8d63f-124">Se você não incluir o parâmetro do relatório, o arquivo HTML será salvo automaticamente na pasta usuários e receberá um nome semelhante a este: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="8d63f-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="8d63f-125">Você também deve especificar uma identidade de site ao executar Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="8d63f-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="8d63f-126">As contas Kerberos são atribuídas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="8d63f-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="8d63f-127">O comando a seguir executa Test-CsKerberosAccountAssignment e salva a saída em um arquivo chamado C:\\logs\\KerberosTest. html:</span><span class="sxs-lookup"><span data-stu-id="8d63f-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="8d63f-128">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8d63f-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8d63f-129">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="8d63f-129">Determining Success or Failure</span></span>

<span data-ttu-id="8d63f-130">O cmdlet Test-CsKerberosAccountAssignment não retorna uma simples indicação de sucesso ou falha.</span><span class="sxs-lookup"><span data-stu-id="8d63f-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="8d63f-131">Em vez disso, você deve exibir o arquivo HTML gerado usando o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8d63f-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8d63f-132">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="8d63f-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="8d63f-133">Aqui estão alguns motivos comuns pelos quais Test-CsKerberosAccountAssignment pode falhar:</span><span class="sxs-lookup"><span data-stu-id="8d63f-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="8d63f-134">Você pode ter especificado uma identidade de site incorreta.</span><span class="sxs-lookup"><span data-stu-id="8d63f-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="8d63f-135">Para retornar uma lista de identidade de site válida, use este comando:</span><span class="sxs-lookup"><span data-stu-id="8d63f-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="8d63f-136">Uma identidade de site geralmente tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="8d63f-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="8d63f-137">site: Redmond</span><span class="sxs-lookup"><span data-stu-id="8d63f-137">site:Redmond</span></span>

  - <span data-ttu-id="8d63f-138">O site especificado pode não ter uma conta Kerberos atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="8d63f-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="8d63f-139">Você pode determinar se uma conta Kerberos está ou não atribuída a um site executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="8d63f-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="8d63f-140">Sua conta Kerberos pode ter uma senha que não é válida.</span><span class="sxs-lookup"><span data-stu-id="8d63f-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="8d63f-141">Se você receber a seguinte mensagem de erro no relatório, provavelmente precisará redefinir a senha da conta Kerberos:</span><span class="sxs-lookup"><span data-stu-id="8d63f-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="8d63f-142">InvalidKerberosConfiguration: a configuração Kerberos é inválida.</span><span class="sxs-lookup"><span data-stu-id="8d63f-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="8d63f-143">InvalidKerberosConfiguration: a configuração Kerberos em atl-cs001.litwareinc.com é inválida.</span><span class="sxs-lookup"><span data-stu-id="8d63f-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="8d63f-144">A conta atribuída esperada é\\litwareinc kerberostest.</span><span class="sxs-lookup"><span data-stu-id="8d63f-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="8d63f-145">Verifique se a conta não expirou e se a senha configurada no computador corresponde à senha do Active Directory da conta.</span><span class="sxs-lookup"><span data-stu-id="8d63f-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="8d63f-146">Você pode definir a senha usando o cmdlet [set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8d63f-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

