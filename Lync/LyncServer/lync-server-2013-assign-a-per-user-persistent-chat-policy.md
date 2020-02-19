---
title: 'Lync Server 2013: atribuir uma política de chat persistente por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134407"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="15936-102">Atribuir uma política de chat persistente por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15936-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="15936-103">Você pode atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15936-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="15936-104">Para obter detalhes sobre como criar políticas de usuário para o servidor de chat persistente, consulte [criar uma política de usuário para chat persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="15936-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="15936-105">Para atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="15936-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="15936-106">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="15936-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="15936-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15936-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15936-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="15936-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="15936-109">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="15936-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="15936-110">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="15936-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="15936-111">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="15936-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="15936-112">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="15936-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="15936-113">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="15936-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="15936-114">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="15936-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="15936-115">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="15936-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="15936-116">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="15936-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="15936-117">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="15936-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="15936-118">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="15936-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="15936-119">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="15936-119">Click **Find**.</span></span>

6.  <span data-ttu-id="15936-120">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="15936-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="15936-121">Se você deseja que a mesma política de chat persistente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="15936-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="15936-122">Em **atribuir políticas**, em **política de chat persistente**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="15936-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="15936-123">Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="15936-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="15936-124">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="15936-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="15936-125">Selecione \*\* \<automático\> \*\* para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="15936-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="15936-126">Clique no nome de uma política de chat persistente por usuário definida anteriormente na página **política de chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="15936-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="15936-127">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="15936-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="15936-128">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="15936-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="15936-129">Atribuir uma política de chat persistente por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15936-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="15936-130">Você também pode atribuir políticas de chat persistente por usuário usando o cmdlet **Grant-CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="15936-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="15936-131">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15936-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="15936-132">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="15936-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="15936-133">Para atribuir uma política de chat persistente por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="15936-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="15936-134">O comando a seguir atribui a política de chat persistente por usuário RedmondPersistentChatPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="15936-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="15936-135">Para atribuir uma política de chat persistente por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="15936-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="15936-136">Este comando atribui a política de chat persistente por usuário RedmondUsersPersistentChatPolicy a todos os usuários que trabalham no departamento de ti.</span><span class="sxs-lookup"><span data-stu-id="15936-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="15936-137">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="15936-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="15936-138">Para cancelar a atribuição de uma política de chat persistente por usuário</span><span class="sxs-lookup"><span data-stu-id="15936-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="15936-139">O comando a seguir retira a atribuição de qualquer política de chat persistente por usuário atribuída anteriormente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="15936-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="15936-140">Depois que a atribuição da política for desfeita, Ken Myer será automaticamente gerenciado usando a política global ou, se houver, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="15936-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="15936-141">Uma política de site tem preferência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="15936-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="15936-142">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="15936-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="15936-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="15936-143">See Also</span></span>


[<span data-ttu-id="15936-144">Criar uma política de usuário para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15936-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

