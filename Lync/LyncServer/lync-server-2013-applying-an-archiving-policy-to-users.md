---
title: 'Lync Server 2013: aplicando uma política de arquivamento aos usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0128d17f3089207eccd94b175057bcbcb5d467f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="aa184-102">Aplicando uma política de arquivamento aos usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa184-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa184-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aa184-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aa184-104">Se um usuário tiver sido habilitado para o Lync Server 2013 e você tiver criado uma ou mais políticas de usuário para arquivamento para usuários hospedados no Lync Server 2013, poderá implementar o suporte de arquivamento para usuários específicos aplicando as políticas apropriadas aos usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="aa184-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="aa184-105">Por exemplo, se você criar uma política para oferecer suporte ao arquivamento de comunicações internas, você pode aplicá-la a pelo menos um usuário ou grupo de usuários para dar suporte ao arquivamento das comunicações do Lync Server 2013 do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa184-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa184-106">Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="aa184-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="aa184-107">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="aa184-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="aa184-108">Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="aa184-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="aa184-109">Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="aa184-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="aa184-110">Use o procedimento descrito neste tópico para aplicar uma política de usuário de arquivamento criada anteriormente a uma ou mais contas de usuário ou a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="aa184-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="aa184-111">Para aplicar uma política de usuário de arquivamento a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="aa184-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="aa184-112">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="aa184-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aa184-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa184-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aa184-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aa184-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aa184-115">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="aa184-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="aa184-116">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="aa184-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="aa184-117">Em **Editar usuário do Lync Server** em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="aa184-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa184-118">As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação padrão do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa184-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="aa184-119">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="aa184-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="aa184-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="aa184-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aa184-121">Atribuindo uma política de arquivamento por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa184-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aa184-122">As políticas de arquivamento por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="aa184-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="aa184-123">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa184-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aa184-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="aa184-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="aa184-125">Para atribuir uma política de arquivamento por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="aa184-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="aa184-126">O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="aa184-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="aa184-127">Para atribuir uma política de arquivamento por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="aa184-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="aa184-128">Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que possuem contas hospedadas no pool de registradores atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="aa184-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="aa184-129">Para obter detalhes sobre o parâmetro Filter usado nesse comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="aa184-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="aa184-130">Para atribuir uma política de arquivamento por usuário</span><span class="sxs-lookup"><span data-stu-id="aa184-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="aa184-p108">O comando a seguir cancela a atribuição de todas as políticas de arquivamento por usuário atribuídas anteriormente a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado pela política global ou pela política de seu site local (se houver uma). Uma política de site prevalece sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="aa184-p108">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="aa184-134">Para obter detalhes, consulte a documentação do cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="aa184-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa184-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="aa184-135">See Also</span></span>


[<span data-ttu-id="aa184-136">Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa184-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="aa184-137">Atribuindo políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa184-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

