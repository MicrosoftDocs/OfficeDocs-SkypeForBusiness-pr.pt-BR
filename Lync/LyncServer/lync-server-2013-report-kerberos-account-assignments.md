---
title: 'Lync Server 2013: relatar atribuições de conta Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 608757b71903ce5290f5f75936b5e5a3904f07fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536328"
---
# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="a638f-102">Relatar as atribuições de conta Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a638f-102">Report Kerberos account assignments in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a638f-103">_**Última modificação do tópico:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="a638f-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="a638f-104">Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a638f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a638f-105">Você pode usar o cmdlet **Get-CsKerberosAccountAssignment** para consultar informações sobre as atribuições de conta de autenticação Kerberos e relatar as informações sobre as atribuições atuais em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="a638f-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="a638f-106">Para consultar as atribuições da conta de autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="a638f-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="a638f-107">Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que executa o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="a638f-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="a638f-108">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a638f-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a638f-109">Na linha de comando, execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a638f-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="a638f-110">Para consultar todas as atribuições de conta de autenticação Kerberos em sua organização e retornar as informações de atribuição sobre cada um deles, execute o cmdlet sem parâmetros:</span><span class="sxs-lookup"><span data-stu-id="a638f-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="a638f-111">Para consultar todas as atribuições de conta de autenticação Kerberos em sua implantação e retornar as informações de atribuição sobre cada um deles, execute o cmdlet com o parâmetro Identity:</span><span class="sxs-lookup"><span data-stu-id="a638f-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="a638f-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a638f-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="a638f-113">Para consultar todas as atribuições de conta de autenticação Kerberos em um único site e retornar as informações de atribuição sobre cada um deles, execute o cmdlet com o parâmetro Filter:</span><span class="sxs-lookup"><span data-stu-id="a638f-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="a638f-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a638f-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a638f-115">Especificar \* SiteName para o parâmetro Filter retorna as informações sobre todos os sites que contêm o nome do site especificado em qualquer lugar no identificador de site (por exemplo, todos os sites que contêm a cadeia de caracteres Redmond no identificador de site).</span><span class="sxs-lookup"><span data-stu-id="a638f-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

