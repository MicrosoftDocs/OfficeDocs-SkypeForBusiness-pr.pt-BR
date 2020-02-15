---
title: 'Lync Server 2013: criar uma conta de autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="bbe76-102">Criar uma conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe76-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbe76-103">_**Última modificação do tópico:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="bbe76-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="bbe76-104">Para concluir com êxito esse procedimento, você deve estar conectado ao servidor ou domínio no mínimo como membro do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="bbe76-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="bbe76-105">Você pode criar contas de autenticação Kerberos para cada site ou pode criar uma única conta de autenticação Kerberos e usá-la para todos os sites.</span><span class="sxs-lookup"><span data-stu-id="bbe76-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="bbe76-106">Você usa os cmdlets do Windows PowerShell para criar e gerenciar as contas, incluindo a identificação das contas atribuídas a cada site.</span><span class="sxs-lookup"><span data-stu-id="bbe76-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="bbe76-107">O construtor de topologias e o painel de controle do Lync Server 2013 não exibem contas de autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bbe76-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="bbe76-108">Use o procedimento a seguir para criar uma ou mais contas de usuário a serem usadas para autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bbe76-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="bbe76-109">Para criar uma conta Kerberos</span><span class="sxs-lookup"><span data-stu-id="bbe76-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="bbe76-110">Como membro do grupo Administradores de domínio, faça logon em um computador no domínio que executa o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="bbe76-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="bbe76-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bbe76-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bbe76-112">Na linha de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="bbe76-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="bbe76-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bbe76-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="bbe76-114">Confirme se o objeto Computer foi criado abrindo Usuário e Computadores do Active Directory, expanda o contêiner **Usuários** e confirme se o objeto Computer da conta do usuário está no contêiner.</span><span class="sxs-lookup"><span data-stu-id="bbe76-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

