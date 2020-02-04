---
title: Testar e relatar prontidão funcional para autenticação Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="433e5-102">Testar e relatar prontidão funcional para autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="433e5-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="433e5-103">_**Tópico da última modificação:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="433e5-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="433e5-104">Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="433e5-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="433e5-105">Você pode usar o cmdlet **Test-CsKerberosAccountAssignment** do Windows PowerShell para testar e relatar a prontidão funcional de uma atribuição de site para a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="433e5-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="433e5-106">Esse comando consulta o site especificado no parâmetro Identity necessário.</span><span class="sxs-lookup"><span data-stu-id="433e5-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="433e5-107">O parâmetro de relatório opcional faz com que o cmdlet escreva um relatório HTML para\\C: registra o computador no qual o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="433e5-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="433e5-108">O parâmetro detalhado opcional relata as informações de atividade para a tela.</span><span class="sxs-lookup"><span data-stu-id="433e5-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="433e5-109">Para testar e relatar a prontidão funcional para a autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="433e5-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="433e5-110">Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou no computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="433e5-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="433e5-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="433e5-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="433e5-112">Na linha de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="433e5-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="433e5-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="433e5-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

