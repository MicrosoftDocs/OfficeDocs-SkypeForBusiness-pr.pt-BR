---
title: 'Lync Server 2013: Atribuir uma conta de autenticação Kerberos a um site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230341bfc6b26bebd22b55195280ffdff130873d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="fc21b-102">Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc21b-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc21b-103">_**Tópico da última modificação:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="fc21b-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="fc21b-104">Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fc21b-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="fc21b-105">Depois de criar a conta Kerberos, você deve atribuí-la a um site.</span><span class="sxs-lookup"><span data-stu-id="fc21b-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="fc21b-106">Este é um site do Lync Server 2013, não um site do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc21b-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="fc21b-107">Você pode criar várias contas de autenticação Kerberos por implantação, mas só pode atribuir uma conta a um site.</span><span class="sxs-lookup"><span data-stu-id="fc21b-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="fc21b-108">Use o procedimento a seguir para atribuir uma conta de autenticação Kerberos criada anteriormente a um site.</span><span class="sxs-lookup"><span data-stu-id="fc21b-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="fc21b-109">Para obter detalhes sobre como criar a conta Kerberos, consulte [criar uma conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="fc21b-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="fc21b-110">Para atribuir uma conta de autenticação Kerberos a um site</span><span class="sxs-lookup"><span data-stu-id="fc21b-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="fc21b-111">Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="fc21b-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="fc21b-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fc21b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fc21b-113">Na linha de comando, execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="fc21b-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="fc21b-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fc21b-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="fc21b-115">Você deve especificar o parâmetro USERACCOUNT usando o formato domínio \ usuário.</span><span class="sxs-lookup"><span data-stu-id="fc21b-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="fc21b-116">Não há suporte para o formato de extensão User@Domain. para fazer referência aos objetos de computador criados para fins de autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="fc21b-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="fc21b-117">**Opcional**: você pode ter configurado um FQDN (nome de domínio totalmente qualificado) de substituição para seus serviços Web, de acordo com [as alterações na URL de serviços Web no Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="fc21b-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="fc21b-118">Se esse for o caso, você precisará adicionar um SPN para esse FQDN também.</span><span class="sxs-lookup"><span data-stu-id="fc21b-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="fc21b-119">Por exemplo, se o FQDN era WebServices. contoso. local, você deve executar:</span><span class="sxs-lookup"><span data-stu-id="fc21b-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fc21b-120">Depois de fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc21b-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

