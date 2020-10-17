---
title: 'Lync Server 2013: remover uma conta de usuário do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 782077cc532dc751076d3152467de865fe799a29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536508"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="bf712-102">Remover uma conta de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf712-102">Remove a user account from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf712-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="bf712-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bf712-104">Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf712-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf712-105">Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="bf712-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="bf712-106">Se quiser desabilitar temporariamente uma conta de usuário, confira o tópico <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">desabilitar ou reabilitar a conta de usuário do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bf712-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="bf712-107">Para remover uma conta de usuário usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="bf712-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="bf712-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="bf712-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bf712-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf712-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf712-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bf712-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf712-111">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="bf712-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bf712-112">Na caixa **Pesquisar usuários**, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Encontrar**.</span><span class="sxs-lookup"><span data-stu-id="bf712-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="bf712-113">Na tabela, clique na conta de usuário que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="bf712-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="bf712-114">No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.</span><span class="sxs-lookup"><span data-stu-id="bf712-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="bf712-115">Na caixa de diálogo, selecione **OK** para remover o usuário.</span><span class="sxs-lookup"><span data-stu-id="bf712-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bf712-116">Removendo contas de usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf712-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bf712-117">Você pode remover contas de usuário usando o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="bf712-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="bf712-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf712-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="bf712-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="bf712-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="bf712-120">Para remover uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="bf712-120">To remove a user account</span></span>

  - <span data-ttu-id="bf712-p104">Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf712-p104">To remove a user account, use the Disable-CsUser cmdlet. For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="bf712-p105">Após este comando ser executado, não há forma de reabilitar a conta e suas configurações anteriores. Ao invés disso, você precisará usar o cmdlet Enable-CsUser para criar uma nova conta para Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bf712-p105">After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="bf712-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="bf712-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf712-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf712-126">See Also</span></span>


[<span data-ttu-id="bf712-127">Desabilitar ou reabilitar a conta de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf712-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="bf712-128">Habilitando e desabilitando usuários para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf712-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

