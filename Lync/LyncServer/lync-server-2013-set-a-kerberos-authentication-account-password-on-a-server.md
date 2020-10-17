---
title: 'Lync Server 2013: definir uma senha de conta de autenticação Kerberos em um servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20229f7bbc600b6a54bf28b13b9d5c14e8cbeb28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510038"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="cf735-102">Definir uma senha de conta de autenticação Kerberos em um servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf735-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf735-103">_**Última modificação do tópico:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="cf735-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="cf735-104">Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf735-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="cf735-105">Você deve configurar uma senha na conta Kerberos para cada site que possua Servidores front end, servidores Standard Edition e Diretores.</span><span class="sxs-lookup"><span data-stu-id="cf735-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="cf735-106">Você pode configurar a senha executando o cmdlet **set-CsKerberosAccountPassword**do   Windows PowerShell em um servidor no site (por exemplo, um servidor front-end).</span><span class="sxs-lookup"><span data-stu-id="cf735-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="cf735-107">Para cada site, você deve executar o cmdlet **set-CsKerberosAccountPassword**   .</span><span class="sxs-lookup"><span data-stu-id="cf735-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="cf735-108">O cmdlet configura o IIS (serviços de informações da Internet) para o serviço de serviços Web e, em seguida, define a senha na conta do computador nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cf735-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="cf735-109">Um método alternativo, com base no parâmetro usado com o cmdlet, configura o IIS em um servidor enquanto usa outro servidor que tenha sido configurado como origem da senha da conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cf735-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="cf735-110">Ao usar o cmdlet **Set-CsKerberosAccountPassword** para definir uma senha, o Kerberos define a senha para uma cadeia de caracteres gerada de forma aleatória.</span><span class="sxs-lookup"><span data-stu-id="cf735-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="cf735-111">Este cmdlet contata todas as instâncias do IIS em todos os sites centrais do Lync Server 2013 aos quais essa conta é atribuída.</span><span class="sxs-lookup"><span data-stu-id="cf735-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="cf735-112">Para definir uma senha para uma conta de autenticação Kerberos</span><span class="sxs-lookup"><span data-stu-id="cf735-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="cf735-113">Faça logon em qualquer computador do domínio com o Shell de gerenciamento do Lync Server instalado como um membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf735-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="cf735-114">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cf735-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cf735-115">Na linha de comando, execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf735-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="cf735-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf735-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf735-p103">Você deve especificar o parâmetro UserAccount usando o formato Domínio\Usuário. O formato Usuário@Domínio.extensão não é compatível para referenciar os objetos computador criados para fins de autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cf735-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf735-119">Após fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar o <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf735-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

