---
title: 'Lync Server 2013: bloquear ou desbloquear um PIN de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61892a19fde4f9584d39557eac2f3ae46c51092
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="fdfed-102">Bloquear ou desbloquear um PIN de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdfed-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdfed-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fdfed-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fdfed-104">Você pode bloquear ou desbloquear o PIN de um usuário na seção **usuários** do painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdfed-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="fdfed-105">Para bloquear o PIN de um usuário no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fdfed-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fdfed-106">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fdfed-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fdfed-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdfed-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fdfed-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fdfed-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fdfed-109">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fdfed-110">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="fdfed-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="fdfed-111">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="fdfed-112">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="fdfed-113">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="fdfed-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="fdfed-114">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="fdfed-115">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="fdfed-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="fdfed-116">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="fdfed-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="fdfed-117">Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="fdfed-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="fdfed-118">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fdfed-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="fdfed-119">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="fdfed-120">Clique no usuário, em **Ação** e, em seguida, em **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="fdfed-121">Para desbloquear o PIN de um usuário no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fdfed-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fdfed-122">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fdfed-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fdfed-123">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdfed-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fdfed-124">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fdfed-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fdfed-125">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fdfed-126">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="fdfed-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="fdfed-127">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="fdfed-128">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="fdfed-129">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="fdfed-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="fdfed-130">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="fdfed-131">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="fdfed-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="fdfed-132">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="fdfed-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="fdfed-133">Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="fdfed-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="fdfed-134">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fdfed-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="fdfed-135">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="fdfed-136">Clique no usuário, clique em **Ação** e, então, clique em **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="fdfed-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fdfed-137">Bloqueio e desbloqueio de PINs do usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdfed-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fdfed-138">Você pode bloquear e desbloquear PINs de usuário usando o Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="fdfed-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="fdfed-139">Você pode executar esses cmdlets do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdfed-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fdfed-140">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="fdfed-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="fdfed-141">Para bloquear um PIN de usuário</span><span class="sxs-lookup"><span data-stu-id="fdfed-141">To lock a user PIN</span></span>

  - <span data-ttu-id="fdfed-p104">Para bloquear o PIN de um usuário, utilize o cmdlet Lock-CsClientPin. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fdfed-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="fdfed-144">Para desbloquear um PIN de usuário</span><span class="sxs-lookup"><span data-stu-id="fdfed-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="fdfed-p105">Para desbloquear o PIN de um usuário, utilize o cmdlet Unlock-CsClientPin. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fdfed-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="fdfed-147">Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="fdfed-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

