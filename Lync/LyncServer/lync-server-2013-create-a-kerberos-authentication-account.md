---
title: 'Lync Server 2013: criar uma conta de autenticação Kerberos'
description: 'Lync Server 2013: criar uma conta de autenticação Kerberos.'
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
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542127"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="7f407-103">Criar uma conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f407-103">Create a Kerberos authentication account in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f407-104">_**Última modificação do tópico:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="7f407-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="7f407-105">Para concluir com êxito esse procedimento, você deve estar conectado ao servidor ou domínio no mínimo como membro do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="7f407-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="7f407-106">Você pode criar contas de autenticação Kerberos para cada site ou pode criar uma única conta de autenticação Kerberos e usá-la para todos os sites.</span><span class="sxs-lookup"><span data-stu-id="7f407-106">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="7f407-107">Você usa os cmdlets do Windows PowerShell para criar e gerenciar as contas, incluindo a identificação das contas atribuídas a cada site.</span><span class="sxs-lookup"><span data-stu-id="7f407-107">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="7f407-108">O construtor de topologias e o painel de controle do Lync Server 2013 não exibem contas de autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7f407-108">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="7f407-109">Use o procedimento a seguir para criar uma ou mais contas de usuário a serem usadas para autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7f407-109">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="7f407-110">Para criar uma conta Kerberos</span><span class="sxs-lookup"><span data-stu-id="7f407-110">To create a Kerberos account</span></span>

1.  <span data-ttu-id="7f407-111">Como membro do grupo Administradores de domínio, faça logon em um computador no domínio que executa o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="7f407-111">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="7f407-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7f407-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7f407-113">Na linha de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7f407-113">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="7f407-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7f407-114">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="7f407-115">Confirme se o objeto Computer foi criado abrindo Usuário e Computadores do Active Directory, expanda o contêiner **Usuários** e confirme se o objeto Computer da conta do usuário está no contêiner.</span><span class="sxs-lookup"><span data-stu-id="7f407-115">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

