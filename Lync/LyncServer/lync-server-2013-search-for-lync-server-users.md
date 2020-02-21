---
title: 'Lync Server 2013: Pesquisar usuários do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f503736b22453f6c3aafd76bc2fac7211f11dec7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="c333a-102">Pesquisar usuários do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c333a-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c333a-103">_**Última modificação do tópico:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="c333a-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="c333a-104">Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c333a-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="c333a-105">É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.</span><span class="sxs-lookup"><span data-stu-id="c333a-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="c333a-106">É possível pesquisar por usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c333a-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="c333a-107">O procedimento a seguir descreve como usar o painel de controle do Lync Server para pesquisar usuários.</span><span class="sxs-lookup"><span data-stu-id="c333a-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c333a-108">Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura por um usuário pelo endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="c333a-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="c333a-109">Em vez disso, você pode pesquisar usuários especificando um prefixo de endereço SIP, por exemplo, SIP: nome, adicione um filtro de pesquisa e selecione um endereço SIP que contenha um endereço de email parcial ou use o cmdlet <STRONG>Get-CSUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c333a-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="c333a-110">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="c333a-110">To search for one or more users</span></span>

1.  <span data-ttu-id="c333a-111">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c333a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c333a-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c333a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c333a-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c333a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c333a-114">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c333a-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c333a-115">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c333a-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="c333a-116">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="c333a-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="c333a-117">Clique no botão de seta de expansão no canto superior direito da tela acima **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c333a-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="c333a-118">Insira a propriedade do usuário digitando-a ou clicando na seta na lista suspensa para selecionar uma propriedade do usuário.</span><span class="sxs-lookup"><span data-stu-id="c333a-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="c333a-119">Na lista **igual a** , clique em **igual a** ou diferente **de**.</span><span class="sxs-lookup"><span data-stu-id="c333a-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="c333a-120">Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c333a-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="c333a-121">Os resultados da pesquisa são exibidos em **resultados da pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="c333a-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="c333a-122">Você pode selecionar qualquer um ou todos os usuários na lista e realizar tarefas de configuração nos usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="c333a-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c333a-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="c333a-123">See Also</span></span>


[<span data-ttu-id="c333a-124">Exibindo informações sobre contas de usuário habilitadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c333a-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="c333a-125">Habilitando e desabilitando usuários para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c333a-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

