---
title: 'Lync Server 2013: verificar certificados de servidor do Lync Server 2013'
description: 'Lync Server 2013: verificar certificados do servidor do Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543587"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="2519f-103">Verificar os certificados do servidor do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2519f-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2519f-104">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="2519f-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2519f-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="2519f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2519f-106">Mensal</span><span class="sxs-lookup"><span data-stu-id="2519f-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2519f-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="2519f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2519f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2519f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2519f-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="2519f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2519f-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2519f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2519f-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="2519f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="2519f-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2519f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2519f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="2519f-113">Description</span></span>

<span data-ttu-id="2519f-114">O cmdlet Get-CsCertificate permite que você recupere informações sobre cada um dos seus certificados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2519f-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="2519f-115">Isso é especialmente importante porque os certificados têm uma data de vencimento interna.</span><span class="sxs-lookup"><span data-stu-id="2519f-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="2519f-116">Por exemplo, os certificados emitidos de forma privada normalmente expiram após 12 meses.</span><span class="sxs-lookup"><span data-stu-id="2519f-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="2519f-117">Se qualquer um dos seus certificados do Lync Server expirar, você perderá a funcionalidade de acompanhamento até que esse certificado seja renovado ou substituído.</span><span class="sxs-lookup"><span data-stu-id="2519f-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2519f-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="2519f-118">Running the test</span></span>

<span data-ttu-id="2519f-119">Para retornar informações sobre cada um dos seus certificados do Lync Server, basta executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2519f-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="2519f-120">Ou você pode filtrar as informações do certificado de retorno com base na data de expiração.</span><span class="sxs-lookup"><span data-stu-id="2519f-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="2519f-121">Por exemplo, esse comando limita os dados retornados aos certificados que expiram (não podem ser usados após) 1 de junho de 2014:</span><span class="sxs-lookup"><span data-stu-id="2519f-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="2519f-122">Para obter mais informações, consulte a documentação de ajuda para o cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="2519f-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="2519f-123">Observe que, embora o cmdlet Test-CsCertificateConfiguration exista, ele não é muito útil para os administradores.</span><span class="sxs-lookup"><span data-stu-id="2519f-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="2519f-124">(Em vez disso, o cmdlet é usado principalmente pelo assistente de certificado.) Embora o cmdlet funcione, as informações que ele retorna são de valor mínimo, conforme mostrado no seguinte exemplo de saída:</span><span class="sxs-lookup"><span data-stu-id="2519f-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="2519f-125">Uso de impressão digital</span><span class="sxs-lookup"><span data-stu-id="2519f-125">Thumbprint Use</span></span>

<span data-ttu-id="2519f-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="2519f-126">\---------- ---</span></span>

<span data-ttu-id="2519f-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 padrão</span><span class="sxs-lookup"><span data-stu-id="2519f-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="2519f-128">Revisão da saída</span><span class="sxs-lookup"><span data-stu-id="2519f-128">Reviewing the output</span></span>

<span data-ttu-id="2519f-129">O cmdlet Get-CsCertificate retorna informações semelhantes às seguintes para cada um dos seus certificados do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2519f-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="2519f-130">Emissor: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="2519f-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="2519f-131">Não depois: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="2519f-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="2519f-132">Não antes: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="2519f-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="2519f-133">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="2519f-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="2519f-134">Subject: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="2519f-135">Alternativonames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="2519f-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="2519f-136">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="2519f-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="2519f-137">Impressão digital: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="2519f-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="2519f-138">Usar: padrão</span><span class="sxs-lookup"><span data-stu-id="2519f-138">Use : Default</span></span>

<span data-ttu-id="2519f-139">Como regra, os principais problemas que envolvem os certificados do Lync Server envolvem datas e horas, como quando os certificados entram em vigor (não antes) ou quando expiram (não depois).</span><span class="sxs-lookup"><span data-stu-id="2519f-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="2519f-140">Como essas datas e horários são tão importantes, talvez você queira limitar os dados retornados às informações como o uso do certificado, o número de série do certificado e a data de vencimento do certificado; em seguida, você pode revisar rapidamente todos os certificados e quando eles vão expirar.</span><span class="sxs-lookup"><span data-stu-id="2519f-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="2519f-141">Para retornar apenas essas informações, use o comando junto com as opções, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="2519f-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="2519f-142">Esse comando retorna dados semelhantes aos seguintes, com os certificados classificados em ordem de data de validade:</span><span class="sxs-lookup"><span data-stu-id="2519f-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="2519f-143">Usar SerialNumber não após</span><span class="sxs-lookup"><span data-stu-id="2519f-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="2519f-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="2519f-144">\--- ------------ --------</span></span>

<span data-ttu-id="2519f-145">611BB01200000000000C 12/28/2015 3:35:41 PM padrão</span><span class="sxs-lookup"><span data-stu-id="2519f-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="2519f-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="2519f-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="2519f-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="2519f-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="2519f-148">Se você tiver problemas com o certificado, convém revisar os outros osnames configurados para um certificado.</span><span class="sxs-lookup"><span data-stu-id="2519f-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="2519f-149">À primeira vista, isso parece ser um problema.</span><span class="sxs-lookup"><span data-stu-id="2519f-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="2519f-150">Por padrão, e dependendo do tamanho da janela do console, Get-CsCertificate pode não conseguir exibir todos os nomes:</span><span class="sxs-lookup"><span data-stu-id="2519f-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="2519f-151">Alternativonames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="2519f-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="2519f-152">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="2519f-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="2519f-153">Para ver todos os nomes alternativos atribuídos a um certificado, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="2519f-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="2519f-154">Isso deve mostrar todos os nomes alternativos no certificado:</span><span class="sxs-lookup"><span data-stu-id="2519f-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="2519f-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-155">sip.fabrikam.com</span></span>

<span data-ttu-id="2519f-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="2519f-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-157">meet.fabrikam.com</span></span>

<span data-ttu-id="2519f-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-158">admin.fabrikam.com</span></span>

<span data-ttu-id="2519f-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="2519f-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2519f-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2519f-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="2519f-161">See Also</span></span>


[<span data-ttu-id="2519f-162">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="2519f-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

