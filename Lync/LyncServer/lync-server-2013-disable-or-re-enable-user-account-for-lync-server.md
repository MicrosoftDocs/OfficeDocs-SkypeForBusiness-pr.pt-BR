---
title: 'Lync Server 2013: desabilitar ou reabilitar a conta de usuário do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7ed0572d36a87532c4845df887dc87ccb34eec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="2678a-102">Desabilitar ou reabilitar a conta de usuário do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2678a-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2678a-103">_**Última modificação do tópico:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="2678a-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="2678a-104">Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Lync Server 2013 sem perder as configurações do Lync Server que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="2678a-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="2678a-105">Como você não perde as configurações da conta de usuário do Lync Server, você pode reabilitar uma conta de usuário previamente habilitada sem precisar reconfigurar a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="2678a-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2678a-106">Simplesmente desabilitar uma conta de usuário no Active Directory <STRONG>não</STRONG> impedirá que o usuário se conecte ou use o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2678a-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="2678a-107">Isso ocorre porque o Lync usa autenticação de certificado que simplifica o processo de autenticação e esses certificados de cliente são válidos por 180 dias.</span><span class="sxs-lookup"><span data-stu-id="2678a-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="2678a-108">Se quiser interromper a desabilitação de contas do Active Directory que foram habilitadas para que o Lync tenha acesso ao Lync Server, você deve usar o cmdlet <STRONG>Disable-CsUser</STRONG> ou usar o <STRONG>painel de controle do Lync Server</STRONG> conforme apresentado neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2678a-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="2678a-109">Quando o usuário estiver desabilitado no Lync e o repositório de gerenciamento central tiver sido replicado no ambiente, os usuários não poderão mais entrar.</span><span class="sxs-lookup"><span data-stu-id="2678a-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="2678a-110">Além disso, os usuários que estiverem conectados serão desconectados.</span><span class="sxs-lookup"><span data-stu-id="2678a-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="2678a-111">Para desabilitar ou reabilitar uma conta de usuário previamente habilitada para o Lync Server</span><span class="sxs-lookup"><span data-stu-id="2678a-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="2678a-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2678a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2678a-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2678a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2678a-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2678a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2678a-115">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="2678a-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2678a-116">Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="2678a-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="2678a-117">Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.</span><span class="sxs-lookup"><span data-stu-id="2678a-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="2678a-118">No menu **Ação**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2678a-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="2678a-119">Para desabilitar temporariamente a conta de usuário para o Lync Server 2013, clique em **desabilitar temporariamente para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2678a-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="2678a-120">Para habilitar a conta de usuário para o Lync Server 2013, clique em **reabilitar para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2678a-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="2678a-121">Usando o Windows PowerShell para desabilitar ou reabilitar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="2678a-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="2678a-122">As contas de usuário podem ser desabilitadas temporariamente e, posteriormente, habilitadas novamente, usando o cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="2678a-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="2678a-123">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2678a-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2678a-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="2678a-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="2678a-125">Para desabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="2678a-125">To disable a user account</span></span>

  - <span data-ttu-id="2678a-126">Para desabilitar uma conta temporariamente, defina o valor da propriedade Enabled como falso ($False).</span><span class="sxs-lookup"><span data-stu-id="2678a-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="2678a-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2678a-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="2678a-128">Para reabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="2678a-128">To re-enable a user account</span></span>

  - <span data-ttu-id="2678a-129">Para reabilitar uma conta de usuário, defina o valor da propriedade Enabled como verdadeiro ($True).</span><span class="sxs-lookup"><span data-stu-id="2678a-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="2678a-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2678a-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="2678a-131">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="2678a-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2678a-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="2678a-132">See Also</span></span>


[<span data-ttu-id="2678a-133">Adicionar e habilitar a conta de usuário para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2678a-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="2678a-134">Habilitando e desabilitando usuários para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2678a-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

