---
title: Modificar a ação padrão para clientes não explicitamente suportados ou restritos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ff08d05c9c8c18b7f81f22b04e2168a14f1a8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="fb352-102">Modificar a ação padrão para clientes não explicitamente suportados ou restritos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb352-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb352-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fb352-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fb352-104">Além de especificar a versão de clientes que você deseja suportar no seu ambiente do Lync Server 2013, você também pode especificar uma ação padrão para clientes que ainda não têm uma política de versão definida.</span><span class="sxs-lookup"><span data-stu-id="fb352-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="fb352-105">Isso permite que você restrinja quais versões do cliente são usadas no seu ambiente do Lync Server, o que pode ajudá-lo a controlar os custos associados ao suporte a várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="fb352-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="fb352-106">Para modificar a ação padrão para clientes não explicitamente suportados ou restritos</span><span class="sxs-lookup"><span data-stu-id="fb352-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="fb352-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fb352-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb352-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb352-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fb352-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fb352-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fb352-110">Na barra de navegação esquerda, clique em **Clientes** e em **Configuração de Versão de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="fb352-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="fb352-111">Na página **Configuração de Versão de Cliente**, clique duas vezes na configuração **Global** da lista.</span><span class="sxs-lookup"><span data-stu-id="fb352-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="fb352-112">Na caixa de diálogo **Editar Configuração de Versão de Cliente**, verifique se que a caixa de seleção **Habilitar Controle de Versão** está marcada e, em **Ação padrão**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fb352-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="fb352-113">**Permitir**   permite que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="fb352-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="fb352-114">**Bloquear**   impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="fb352-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="fb352-115">**Bloquear com URL**   impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** e incluir uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.</span><span class="sxs-lookup"><span data-stu-id="fb352-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="fb352-116">**Permitir com URL**   permite que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de **políticas de versão do cliente** e incluir uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.</span><span class="sxs-lookup"><span data-stu-id="fb352-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="fb352-117">Se você tiver selecionado **Bloquear com URL**, digite a URL de download do cliente para incluir na mensagem de erro na caixa **URL**.</span><span class="sxs-lookup"><span data-stu-id="fb352-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="fb352-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fb352-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="fb352-119">Para desabilitar o controle de versão de cliente</span><span class="sxs-lookup"><span data-stu-id="fb352-119">To disable client version control</span></span>

  - <span data-ttu-id="fb352-120">Para desabilitar o controle de versão para permitir que todos os clientes façam logon, independentemente da versão de cliente, desmarque a caixa de seleção **Habilitar controle de versão** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fb352-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb352-121">Modificar a ação padrão usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb352-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fb352-122">A ação padrão a ser tomada quando os usuários tentam fazer logon usando clientes que não são explicitamente suportados ou restritos por uma política de versão do cliente podem ser gerenciados usando a interface de linha de comando do Windows PowerShell e o cmdlet **set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="fb352-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="fb352-123">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb352-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fb352-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="fb352-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="fb352-125">Para configurar a ação padrão para bloquear o acesso</span><span class="sxs-lookup"><span data-stu-id="fb352-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="fb352-p104">O seguinte comando define a ação padrão para o bloqueio do site de Redmond. Isso bloqueará o registro de qualquer cliente para o qual nenhuma regra de configuração de versão do cliente existir.</span><span class="sxs-lookup"><span data-stu-id="fb352-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="fb352-128">Para configurar a ação padrão para permitir o acesso</span><span class="sxs-lookup"><span data-stu-id="fb352-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="fb352-p105">Neste exemplo, a ação padrão para o site de Redmond é definir como Permitir. Isso permitirá o registro de qualquer cliente para o qual nenhuma regra de configuração de versão do cliente existir.</span><span class="sxs-lookup"><span data-stu-id="fb352-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="fb352-131">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="fb352-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb352-132">Confira Também</span><span class="sxs-lookup"><span data-stu-id="fb352-132">See Also</span></span>


[<span data-ttu-id="fb352-133">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb352-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

