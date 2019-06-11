---
title: Sincronizar uma senha de conta de autenticação Kerberos com o IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="3d2ff-102">Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d2ff-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d2ff-103">_**Tópico da última modificação:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="3d2ff-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="3d2ff-104">Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="3d2ff-105">Em um site, os servidores de front-end, os servidores de edição padrão e os directors podem usar uma conta de autenticação Kerberos para fins de autenticação de solicitações para o serviço de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="3d2ff-106">Esse procedimento localiza cada servidor que executa serviços Web em um site que tenha sido atribuído a uma conta Kerberos e atualiza as configurações de configuração dos serviços de informações da Internet (IIS) para usar a conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="3d2ff-107">Para obter detalhes, consulte [definir uma senha da conta de autenticação Kerberos em um servidor no Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d2ff-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="3d2ff-108">Para definir e configurar uma senha da conta de autenticação Kerberos</span><span class="sxs-lookup"><span data-stu-id="3d2ff-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="3d2ff-109">Faça logon em um computador de origem (por exemplo, fe01.contoso.com) como membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3d2ff-110">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3d2ff-111">Na linha de comando do Shell de gerenciamento do Lync Server, execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="3d2ff-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="3d2ff-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3d2ff-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="3d2ff-113">O nome do computador de origem e do computador de destino deve ser um nome de domínio totalmente qualificado (FQDN) do servidor.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="3d2ff-114">Você não pode usar o FQDN do pool, a menos que o nome do pool seja igual ao nome do computador que você está usando como computador de origem ou de destino.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="3d2ff-115">Depois de fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d2ff-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

