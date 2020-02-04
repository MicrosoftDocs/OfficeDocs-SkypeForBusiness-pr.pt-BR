---
title: 'Lync Server 2013: atribuir uma política de voz por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723401"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="f5bfe-102">Atribuir uma política de voz por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5bfe-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="f5bfe-103">Políticas de voz globais e em nível de site são automaticamente atribuídas a todas as contas de usuário do Lync Server 2013 habilitadas para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f5bfe-104">Você também pode atribuir políticas de voz a usuários específicos usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="f5bfe-105">Use os procedimentos deste tópico para atribuir explicitamente políticas por usuário a usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="f5bfe-106">Para atribuir uma política de voz específica do usuário usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="f5bfe-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f5bfe-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f5bfe-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f5bfe-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f5bfe-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f5bfe-110">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="f5bfe-111">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f5bfe-112">Em **Editar usuário do Lync Server** em **política de voz**, selecione a política de usuário que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="f5bfe-113">As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de política global e do servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f5bfe-114">Atribuir uma política de voz por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5bfe-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f5bfe-115">Você pode atribuir políticas de voz por usuário usando o Windows PowerShell e o cmdlet **Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="f5bfe-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="f5bfe-116">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f5bfe-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="f5bfe-118">Para atribuir uma política de voz por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="f5bfe-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="f5bfe-119">O comando a seguir atribui a RedmondVoicePolicy de política de voz por usuário ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="f5bfe-120">Para atribuir uma política de voz por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="f5bfe-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="f5bfe-121">Esse comando atribui a política de voz por usuário FinanceVoicePolicy a todos os usuários que têm contas na unidade organizacional Finance no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="f5bfe-122">Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="f5bfe-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="f5bfe-123">Para cancelar a atribuição de uma política de voz por usuário</span><span class="sxs-lookup"><span data-stu-id="f5bfe-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="f5bfe-124">O comando a seguir não atribui a atribuição de nenhuma política de voz por usuário atribuída anteriormente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f5bfe-125">Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="f5bfe-126">Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="f5bfe-127">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="f5bfe-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5bfe-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5bfe-128">See Also</span></span>


[<span data-ttu-id="f5bfe-129">Desabilitar um usuário para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5bfe-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="f5bfe-130">Shell de Gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5bfe-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

