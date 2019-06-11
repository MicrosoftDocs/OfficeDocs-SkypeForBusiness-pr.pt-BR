---
title: 'Lync Server 2013: Atribuir uma conta de autenticação Kerberos a um site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c706f9fdd8932456a9f1617e55dc9231dbd6a84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="78d8f-102">Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d8f-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d8f-103">_**Tópico da última modificação:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="78d8f-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="78d8f-104">Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="78d8f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="78d8f-105">Depois de criar a conta Kerberos, você deve atribuí-la a um site.</span><span class="sxs-lookup"><span data-stu-id="78d8f-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="78d8f-106">Este é um site do Lync Server 2013, não um site do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78d8f-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="78d8f-107">Você pode criar várias contas de autenticação Kerberos por implantação, mas só pode atribuir uma conta a um site.</span><span class="sxs-lookup"><span data-stu-id="78d8f-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="78d8f-108">Use o procedimento a seguir para atribuir uma conta de autenticação Kerberos criada anteriormente a um site.</span><span class="sxs-lookup"><span data-stu-id="78d8f-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="78d8f-109">Para obter detalhes sobre como criar a conta Kerberos, consulte [criar uma conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="78d8f-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="78d8f-110">Para atribuir uma conta de autenticação Kerberos a um site</span><span class="sxs-lookup"><span data-stu-id="78d8f-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="78d8f-111">Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="78d8f-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="78d8f-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78d8f-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="78d8f-113">Na linha de comando, execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="78d8f-113">From the command line, run the following two commands:</span></span>
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```
        Enable-CsTopology
       ```
    
    <span data-ttu-id="78d8f-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="78d8f-114">For example:</span></span>
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="78d8f-115">Você deve especificar o parâmetro USERACCOUNT usando o formato domínio \ usuário.</span><span class="sxs-lookup"><span data-stu-id="78d8f-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="78d8f-116">Não há suporte para o formato de usuário @ domínio. extensão para fazer referência aos objetos de computador criados para fins de autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="78d8f-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="78d8f-117">**Opcional**: você pode ter configurado um FQDN (nome de domínio totalmente qualificado) de substituição para seus serviços Web, de acordo com [as alterações na URL de serviços Web no Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="78d8f-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="78d8f-118">Se esse for o caso, você precisará adicionar um SPN para esse FQDN também.</span><span class="sxs-lookup"><span data-stu-id="78d8f-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="78d8f-119">Por exemplo, se o FQDN era WebServices. contoso. local, você deve executar:</span><span class="sxs-lookup"><span data-stu-id="78d8f-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
        setspn -S http/webservices.contoso.local kerbauth

5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="78d8f-120">Depois de fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78d8f-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

