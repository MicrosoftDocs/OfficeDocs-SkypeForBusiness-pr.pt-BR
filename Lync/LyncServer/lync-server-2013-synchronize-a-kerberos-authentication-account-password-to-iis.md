---
title: Sincronizar uma senha de conta de autenticação Kerberos com o IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811134697ea04f1dab3637e648ff89455fca07d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="cfe7c-102">Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfe7c-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfe7c-103">_**Última modificação do tópico:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="cfe7c-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="cfe7c-104">Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="cfe7c-105">Em um site, servidores front-end, servidores Standard Edition e diretores podem usar uma conta de autenticação Kerberos para fins de autenticação de solicitações para o serviço de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="cfe7c-106">Este procedimento localiza cada servidor que executa os serviços Web em um site que tenha sido atribuído a uma conta Kerberos e atualiza as definições de configuração do IIS (serviços de informações da Internet) para usar a conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="cfe7c-107">Para obter detalhes, consulte [definir uma senha de conta de autenticação Kerberos em um servidor no Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="cfe7c-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="cfe7c-108">Para definir e configurar uma senha de autenticação de conta Kerberos</span><span class="sxs-lookup"><span data-stu-id="cfe7c-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="cfe7c-109">Conecte-se a um computador de origem (como um fe01.contoso.com) como membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="cfe7c-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cfe7c-111">Na linha de comando do Shell de gerenciamento do Lync Server, execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cfe7c-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="cfe7c-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cfe7c-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="cfe7c-p102">O nome do computador de origem e do computador de desinto deve ser um nome de domínio Totalmente qualificado (FQDN) do servidor. Você não pode usar o FQDN do pool, a não ser que o nome do pool seja o mesmo do nome do computador sendo usado como computador de origem ou de destino.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="cfe7c-115">Após fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar o <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfe7c-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

