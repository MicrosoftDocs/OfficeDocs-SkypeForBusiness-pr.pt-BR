---
title: 'Lync Server 2013: exibir informações de PIN do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f2e9a8c5013a17a35a6f13cf67d9924a9fed78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a><span data-ttu-id="64ea5-102">Exibir informações de PIN do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64ea5-102">View user PIN information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64ea5-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="64ea5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="64ea5-104">Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Lync Server 2013 com credenciais do AD DS (serviços de domínio Active Directory) requer um PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="64ea5-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="64ea5-105">Você pode exibir as informações de PIN de um usuário no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64ea5-105">You can view a user’s PIN information from Lync Server 2013 Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64ea5-106">Você pode exibir as informações de status de PIN, como se o PIN foi definido ou quando ele foi alterado pela última vez, mas não pode ver o PIN atual consultando o status de PIN.</span><span class="sxs-lookup"><span data-stu-id="64ea5-106">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="64ea5-107">Se um usuário perder seu PIN, você poderá redefini-lo seguindo os procedimentos em <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">definir PIN de conferência discada de um usuário no Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="64ea5-107">If a user has lost their PIN, you can reset it by following the procedures in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Set a user's dial-in conferencing PIN in Lync Server 2013</A></span></span>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="64ea5-108">Para exibir o PIN de um usuário no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="64ea5-108">To view a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="64ea5-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="64ea5-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64ea5-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64ea5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64ea5-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64ea5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64ea5-112">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="64ea5-112">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="64ea5-113">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="64ea5-113">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="64ea5-114">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="64ea5-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="64ea5-115">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="64ea5-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="64ea5-116">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="64ea5-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="64ea5-117">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="64ea5-117">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="64ea5-118">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="64ea5-118">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="64ea5-119">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="64ea5-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="64ea5-120">Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="64ea5-120">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="64ea5-121">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="64ea5-121">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="64ea5-122">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="64ea5-122">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64ea5-p104">Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em <STRONG>Ação</STRONG> e depois em <STRONG>Desbloquear PIN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="64ea5-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="64ea5-125">Clique em um usuário nos resultados da pesquisa, em **Ação** e depois em **Exibir status do PIN**.</span><span class="sxs-lookup"><span data-stu-id="64ea5-125">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="64ea5-126">Exibindo informações de PIN do usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ea5-126">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="64ea5-127">Você pode exibir as informações de PIN do usuário usando o cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="64ea5-127">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="64ea5-128">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64ea5-128">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="64ea5-129">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="64ea5-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-user-pin-information"></a><span data-ttu-id="64ea5-130">Para exibir as informações de PIN do usuário</span><span class="sxs-lookup"><span data-stu-id="64ea5-130">To view user PIN information</span></span>

  - <span data-ttu-id="64ea5-131">Para exibir as informações de PIN de um usuário, digite um comando semelhante ao seguinte no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="64ea5-131">To view PIN information for a user, type a command similar to the following in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    <span data-ttu-id="64ea5-132">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="64ea5-132">That will return information similar to this:</span></span>
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

<span data-ttu-id="64ea5-133">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .</span><span class="sxs-lookup"><span data-stu-id="64ea5-133">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64ea5-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="64ea5-134">See Also</span></span>


[<span data-ttu-id="64ea5-135">Definir PIN de conferência discada de um usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64ea5-135">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[<span data-ttu-id="64ea5-136">Bloquear ou desbloquear um PIN de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64ea5-136">Lock or unlock a user PIN in Lync Server 2013</span></span>](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

