---
title: 'Lync Server 2013: criar ou modificar uma nova política de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8464e64c3de1e85f823bb3e1b5dac4dd1837effd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="55c38-102">Criar ou modificar uma nova política de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c38-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55c38-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="55c38-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="55c38-104">Você pode usar políticas de versão do cliente para especificar as versões dos clientes que são compatíveis com o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="55c38-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="55c38-105">O uso do controle de versão do cliente pode ajudar a reduzir os custos associados ao suporte a várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="55c38-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="55c38-106">Também pode melhorar a experiência geral do usuário, porque quando as versões anteriores e posteriores dos clientes interagem, os recursos disponíveis podem ser limitados pela versão anterior do cliente.</span><span class="sxs-lookup"><span data-stu-id="55c38-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="55c38-107">Você pode criar ou modificar políticas de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55c38-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="55c38-108">Para criar ou modificar políticas de versão do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="55c38-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="55c38-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="55c38-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="55c38-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55c38-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55c38-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55c38-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55c38-112">Na barra de navegação esquerda, clique em **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="55c38-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55c38-113">A guia <STRONG>Política de Versões de Clientes</STRONG> está selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="55c38-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="55c38-114">Na página **política de versão do cliente** , execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="55c38-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="55c38-115">Para criar uma política de versão de cliente, clique em **novo**, selecione **política de site**, **política de pool**ou **política de usuário**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="55c38-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="55c38-116">Para modificar a política global ou outra política de versão de cliente existente, selecione a política, clique em **Editar**e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="55c38-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="55c38-117">Na página **Editar política de versão do cliente** , crie ou modifique regras, conforme descrito em [criar ou modificar uma nova regra de política de versão do cliente no Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="55c38-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="55c38-118">Criando ou modificando políticas de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55c38-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="55c38-119">Você pode criar políticas de versão do cliente usando o cmdlet **New-CsClientVersionPolicy** e modificá-las usando o cmdlet **set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="55c38-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="55c38-120">Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55c38-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="55c38-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="55c38-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="55c38-122">Para criar uma nova política de versão de cliente com escopo de site</span><span class="sxs-lookup"><span data-stu-id="55c38-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="55c38-123">O comando a seguir cria uma nova política de versão do cliente aplicada ao site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="55c38-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="55c38-124">Como nenhum parâmetro adicional é especificado, a nova política usará as configurações de versão do cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="55c38-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="55c38-125">Para criar uma nova política de versão do cliente por usuário</span><span class="sxs-lookup"><span data-stu-id="55c38-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="55c38-126">Para criar uma política por usuário, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="55c38-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="55c38-127">Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) e o cmdlet [set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="55c38-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

