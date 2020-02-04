---
title: 'Lync Server 2013: Remover autenticação Kerberos de um site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88f3de6f653354087d1abd0f7884ee09eda2f36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="25c7f-102">No Lync Server 2013, remover autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="25c7f-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25c7f-103">_**Tópico da última modificação:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="25c7f-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="25c7f-104">Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="25c7f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="25c7f-105">Se precisar remover a autenticação Kerberos de um site ou de remover um site, você deve remover a atribuição de conta de autenticação Kerberos do site usando o cmdlet **Remove-CsKerberosAccountAssignment** .</span><span class="sxs-lookup"><span data-stu-id="25c7f-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="25c7f-106">Use o procedimento a seguir para remover a atribuição de conta de autenticação Kerberos, que remove a atribuição de todos os computadores do site.</span><span class="sxs-lookup"><span data-stu-id="25c7f-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="25c7f-107">Se você estiver desativando permanentemente a conta habilitada para Kerberos, use os usuários e computadores do Active Directory para excluí-la dos serviços de domínio Active Directory depois de ter removido a tarefa.</span><span class="sxs-lookup"><span data-stu-id="25c7f-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="25c7f-108">Se você planeja usar o objeto no futuro, talvez queira manter o objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="25c7f-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="25c7f-109">Para remover a autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="25c7f-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="25c7f-110">Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="25c7f-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="25c7f-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="25c7f-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="25c7f-112">Na linha de comando, execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="25c7f-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="25c7f-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="25c7f-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="25c7f-114">Depois de fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25c7f-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

