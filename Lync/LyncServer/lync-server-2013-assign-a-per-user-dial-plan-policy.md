---
title: 'Lync Server 2013: atribuir uma política de plano de discagem por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043703"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="bd0cc-102">Atribuir uma política de plano de discagem por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd0cc-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="bd0cc-103">Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferência discada, o usuário deve receber um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="bd0cc-104">As contas de usuário usarão automaticamente o plano de discagem global ou, se houver um, o plano de discagem no nível do site quando você não atribuir explicitamente um plano de discagem por usuário existente.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="bd0cc-105">Se quiser usar o plano de discagem global ou de site para todos os usuários habilitados para o Enterprise Voice, você pode ignorar esta seção.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="bd0cc-106">Para atribuir um plano de discagem usando o painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd0cc-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="bd0cc-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd0cc-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bd0cc-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bd0cc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bd0cc-110">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bd0cc-111">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="bd0cc-112">Na tabela, clique na conta de usuário para a qual você deseja atribuir um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="bd0cc-113">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="bd0cc-114">Na página **Editar Lync Server**, em **Telefonia**, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="bd0cc-115">Clique em **política do plano de discagem**e escolha o plano de discagem desejado.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="bd0cc-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-116">Click **Commit**.</span></span>

<span data-ttu-id="bd0cc-117">Para obter detalhes sobre como configurar planos de discagem, consulte o tópico [Configuring dial Plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="bd0cc-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bd0cc-118">Atribuir um plano de discagem por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0cc-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bd0cc-119">Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet **Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="bd0cc-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="bd0cc-120">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bd0cc-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="bd0cc-122">Para atribuir um plano de discagem por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="bd0cc-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="bd0cc-123">O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="bd0cc-124">Para atribuir um plano de discagem por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="bd0cc-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="bd0cc-125">Este comando atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="bd0cc-126">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="bd0cc-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="bd0cc-127">Para cancelar a atribuição de um plano de discagem por usuário</span><span class="sxs-lookup"><span data-stu-id="bd0cc-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="bd0cc-128">O comando a seguir retira a atribuição de qualquer plano de discagem por usuário anteriormente atribuído a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="bd0cc-129">Após o plano de discagem por usuário não ser atribuído, Ken Myer será automaticamente gerenciado usando o plano de discagem global, seu plano de discagem de site local (se houver) ou o plano de discagem de escopo de serviço atribuído ao seu registrador ou gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="bd0cc-130">Um plano de discagem de escopo de serviço tem precedência sobre qualquer plano de discagem de site e um plano de discagem de site tem preferência sobre o plano de discagem global.</span><span class="sxs-lookup"><span data-stu-id="bd0cc-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="bd0cc-131">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="bd0cc-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd0cc-132">Confira Também</span><span class="sxs-lookup"><span data-stu-id="bd0cc-132">See Also</span></span>


[<span data-ttu-id="bd0cc-133">Configurando planos de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd0cc-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="bd0cc-134">Contas de usuário habilitadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd0cc-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

