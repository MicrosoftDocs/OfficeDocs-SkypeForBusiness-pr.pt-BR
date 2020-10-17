---
title: 'Lync Server 2013: atribuir uma política de arquivamento por usuário'
description: 'Lync Server 2013: atribua uma política de arquivamento por usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559987"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="fdde4-103">Atribuir uma política de arquivamento por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdde4-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="fdde4-104">A política de arquivamento é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdde4-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="fdde4-105">A implantação de uma ou mais políticas de arquivamento por usuário é opcional.</span><span class="sxs-lookup"><span data-stu-id="fdde4-105">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="fdde4-106">Você também pode implantar apenas uma política de arquivamento de nível global ou política de arquivamento em nível de site.</span><span class="sxs-lookup"><span data-stu-id="fdde4-106">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="fdde4-107">Se você implantar políticas por usuário, deverá atribui-las explicitamente a usuários, grupos ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="fdde4-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="fdde4-108">Os requisitos de arquivamento são automaticamente padrão para aqueles definidos na política de conferência de nível global quando não há uma política específica de nível de site ou por usuário atribuída.</span><span class="sxs-lookup"><span data-stu-id="fdde4-108">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="fdde4-109">Depois de criar pelo menos uma política de arquivamento por usuário, use os procedimentos neste tópico para atribuir a política que especifica apropriadamente se as comunicações internas de um usuário específico, as comunicações externas ou ambas, serão arquivadas pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="fdde4-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="fdde4-110">Para obter detalhes sobre como criar políticas de arquivamento por usuário, consulte [criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="fdde4-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="fdde4-111">Para atribuir uma política de arquivamento por usuário</span><span class="sxs-lookup"><span data-stu-id="fdde4-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="fdde4-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fdde4-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fdde4-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdde4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fdde4-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fdde4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fdde4-115">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fdde4-116">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="fdde4-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="fdde4-117">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="fdde4-118">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="fdde4-119">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="fdde4-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="fdde4-120">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="fdde4-121">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="fdde4-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="fdde4-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="fdde4-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="fdde4-123">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="fdde4-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="fdde4-124">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fdde4-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="fdde4-125">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-125">Click **Find**.</span></span>

6.  <span data-ttu-id="fdde4-126">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="fdde4-127">Se você deseja que a mesma política de arquivamento por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fdde4-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="fdde4-128">Em **atribuir políticas**, em **política de arquivamento**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fdde4-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="fdde4-129">Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt; manter como está &gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fdde4-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="fdde4-130">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="fdde4-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="fdde4-131">Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="fdde4-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="fdde4-132">Clique no nome de uma política de arquivamento por usuário definida anteriormente na página **política de arquivamento** .</span><span class="sxs-lookup"><span data-stu-id="fdde4-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="fdde4-133">Para ajudar a decidir qual política você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos de usuário e as permissões definidas.</span><span class="sxs-lookup"><span data-stu-id="fdde4-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="fdde4-134">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdde4-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fdde4-135">Atribuindo uma política de arquivamento de Per-User usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdde4-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fdde4-136">Você pode atribuir políticas de arquivamento por usuário usando o Windows PowerShell e o cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="fdde4-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="fdde4-137">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdde4-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fdde4-138">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="fdde4-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="fdde4-139">Para atribuir uma política de arquivamento por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="fdde4-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="fdde4-140">O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="fdde4-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="fdde4-141">Para atribuir uma política de arquivamento por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="fdde4-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="fdde4-142">Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que têm contas hospedadas no pool de registradores atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fdde4-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fdde4-143">Para obter mais informações sobre o parâmetro Filter usado nesse comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="fdde4-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="fdde4-144">Para cancelar a atribuição de uma política de arquivamento por usuário</span><span class="sxs-lookup"><span data-stu-id="fdde4-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="fdde4-p106">O comando a seguir cancela a atribuição de todas as políticas de arquivamento por usuário atribuídas anteriormente a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado pela política global ou pela política de seu site local (se houver uma). Uma política de site prevalece sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="fdde4-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="fdde4-148">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="fdde4-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdde4-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="fdde4-149">See Also</span></span>


[<span data-ttu-id="fdde4-150">Criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos</span><span class="sxs-lookup"><span data-stu-id="fdde4-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="fdde4-151">Atribuindo políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdde4-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

