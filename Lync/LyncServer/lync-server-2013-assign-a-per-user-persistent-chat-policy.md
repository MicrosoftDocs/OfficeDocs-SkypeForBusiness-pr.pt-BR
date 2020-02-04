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
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722821"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="73235-102">Atribuir uma política de chat persistente por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73235-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="73235-103">Você pode atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73235-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="73235-104">Para obter detalhes sobre como criar políticas de usuário para o servidor de chat persistente, consulte [criar uma política de usuário para chat persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="73235-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="73235-105">Para atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="73235-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="73235-106">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="73235-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73235-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73235-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73235-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73235-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73235-109">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="73235-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="73235-110">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="73235-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="73235-111">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="73235-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="73235-112">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="73235-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="73235-113">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="73235-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="73235-114">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="73235-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="73235-115">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="73235-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="73235-116">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="73235-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="73235-117">Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="73235-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="73235-118">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="73235-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="73235-119">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="73235-119">Click **Find**.</span></span>

6.  <span data-ttu-id="73235-120">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="73235-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="73235-121">Se quiser que a mesma política de chat persistente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="73235-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="73235-122">Em **atribuir políticas**, em **política de chat persistente**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="73235-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="73235-123">Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="73235-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="73235-124">Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.</span><span class="sxs-lookup"><span data-stu-id="73235-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="73235-125">Selecione \*\* \<automático\> \*\* para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="73235-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="73235-126">Clique no nome de uma política de chat persistente por usuário definida anteriormente na página **política de chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="73235-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="73235-127">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="73235-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="73235-128">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73235-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="73235-129">Atribuir uma política de chat persistente por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73235-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="73235-130">Você também pode atribuir políticas de bate-papo persistentes por usuário usando o cmdlet **Grant-CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="73235-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="73235-131">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73235-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="73235-132">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="73235-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="73235-133">Para atribuir uma política de chat persistente por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="73235-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="73235-134">O comando a seguir atribui a política de chat persistente por usuário RedmondPersistentChatPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="73235-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="73235-135">Para atribuir uma política de chat persistente por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="73235-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="73235-136">Esse comando atribui a política de chat persistente por usuário RedmondUsersPersistentChatPolicy a todos os usuários que trabalham para o departamento de ti.</span><span class="sxs-lookup"><span data-stu-id="73235-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="73235-137">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="73235-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="73235-138">Para cancelar a atribuição de uma política de chat persistente por usuário</span><span class="sxs-lookup"><span data-stu-id="73235-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="73235-139">O comando a seguir não atribui atribuições de qualquer política de chat persistente por usuário atribuída anteriormente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="73235-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="73235-140">Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="73235-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="73235-141">Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="73235-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="73235-142">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="73235-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="73235-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="73235-143">See Also</span></span>


[<span data-ttu-id="73235-144">Criar uma política de usuário para Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73235-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

