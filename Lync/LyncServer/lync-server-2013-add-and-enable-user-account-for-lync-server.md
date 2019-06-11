---
title: 'Lync Server 2013: Adicionar e habilitar a conta de usuário para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc52e76d480e323669b88c1ee461eeccf9aef38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="952e0-102">Adicionar e habilitar a conta de usuário para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="952e0-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="952e0-103">_**Tópico da última modificação:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="952e0-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="952e0-104">Depois de habilitar uma conta de usuário em usuários e computadores do Active Directory, você pode usar o painel de controle do Lync Server para criar e habilitar as novas contas de usuário do Lync Server 2013 adicionando um usuário do Active Directory ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="952e0-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="952e0-105">Para adicionar e habilitar um novo usuário do Lync Server</span><span class="sxs-lookup"><span data-stu-id="952e0-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="952e0-106">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="952e0-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="952e0-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="952e0-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="952e0-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="952e0-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="952e0-109">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="952e0-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="952e0-110">Clique em **habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="952e0-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="952e0-111">Na caixa de diálogo **novo usuário do Lync Server** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="952e0-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="952e0-112">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome, o nome para exibição, o nome, o sobrenome, o nome da conta do Gerenciador de contas de segurança (Sam), o endereço de email, o nome UPN ou o número de telefone da conta de usuário do Active Directory que você deseja e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="952e0-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="952e0-113">Na tabela, selecione a conta que você deseja adicionar ao Lync Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="952e0-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="952e0-114">Atribua o usuário a um pool, especifique os detalhes adicionais e atribua as políticas ao usuário desejado e, em seguida, clique em **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="952e0-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="952e0-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="952e0-115">See Also</span></span>


[<span data-ttu-id="952e0-116">Desabilitar ou habilitar novamente a conta de usuário para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="952e0-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="952e0-117">Remover uma conta de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="952e0-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="952e0-118">Habilitando e desabilitando usuários do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="952e0-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

