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
ms.openlocfilehash: e160af5920f58b3813bd168c7f4fbe2e0f0cf95c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="08cb3-102">Testar e relatar prontidão funcional para autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08cb3-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08cb3-103">_**Última modificação do tópico:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="08cb3-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="08cb3-104">Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="08cb3-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="08cb3-105">Você pode usar o cmdlet **Test-CsKerberosAccountAssignment** do Windows PowerShell para testar e relatar a prontidão funcional de uma atribuição de site para autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="08cb3-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="08cb3-106">Esse comando consulta o site especificado no parâmetro Identity necessário.</span><span class="sxs-lookup"><span data-stu-id="08cb3-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="08cb3-107">O parâmetro de relatório opcional faz com que o cmdlet grave um relatório HTML em\\C: logs no computador no qual o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="08cb3-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="08cb3-108">O parâmetro Verbose opcional mostra as informações de atividade na tela.</span><span class="sxs-lookup"><span data-stu-id="08cb3-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="08cb3-109">Para testar e relatar a prontidão funcional da autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="08cb3-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="08cb3-110">Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que executa o Lync Server 2013 ou no computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="08cb3-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="08cb3-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="08cb3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="08cb3-112">Na linha de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08cb3-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="08cb3-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="08cb3-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

