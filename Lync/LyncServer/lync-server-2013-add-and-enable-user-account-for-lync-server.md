---
title: 'Lync Server 2013: Adicionar e habilitar a conta de usuário para o Lync Server'
description: 'Lync Server 2013: Adicionar e habilitar a conta de usuário para o Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f70ae2da122a0db3986a75677c1d29234fbe0e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571807"
---
# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="8a67a-103">Adicionar e habilitar a conta de usuário para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a67a-103">Add and enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a67a-104">_**Última modificação do tópico:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="8a67a-104">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="8a67a-105">Depois de habilitar uma conta de usuário em usuários e computadores do Active Directory, você pode usar o painel de controle do Lync Server para criar e habilitar novas contas de usuário do Lync Server 2013 adicionando um usuário do Active Directory ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a67a-105">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="8a67a-106">Para adicionar e habilitar um novo usuário do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8a67a-106">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="8a67a-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8a67a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8a67a-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a67a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a67a-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8a67a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a67a-110">Na barra de navegação da esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="8a67a-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8a67a-111">Clique em **Habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="8a67a-111">Click **Enable users**.</span></span>

5.  <span data-ttu-id="8a67a-112">No diálogo **Novo Usuário do Lync Server**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8a67a-112">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="8a67a-113">Na caixa \*\*Pesquisar usuários \*\*, digite todo ou o primeiro nome, nome de exibição, nome, sobrenome, nome da conta SAM, endereço de email, UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="8a67a-113">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="8a67a-114">Na tabela, selecione a conta que você deseja adicionar ao Lync Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a67a-114">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="8a67a-115">Atribua o usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="8a67a-115">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a67a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a67a-116">See Also</span></span>


[<span data-ttu-id="8a67a-117">Desabilitar ou reabilitar a conta de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a67a-117">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="8a67a-118">Remover uma conta de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a67a-118">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="8a67a-119">Habilitando e desabilitando usuários para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a67a-119">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

