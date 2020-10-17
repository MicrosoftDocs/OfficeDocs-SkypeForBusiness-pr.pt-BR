---
title: 'Lync Server 2013: criar ou modificar uma política de mobilidade'
description: 'Lync Server 2013: criar ou modificar uma política de mobilidade.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcf593c568a8ecf1bd6791641affc4076672b250
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566097"
---
# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="fde92-103">Criar ou modificar uma política de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde92-103">Create or modify a mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fde92-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fde92-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fde92-105">Você pode criar ou modificar a política de mobilidade para permitir que usuários móveis usem os dispositivos móveis suportados para a funcionalidade Lync, como mensagens instântaneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="fde92-105">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fde92-106">Você pode criar ou modificar políticas de mobilidade no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde92-106">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="fde92-107">Para criar uma política de mobilidade com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fde92-107">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fde92-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fde92-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fde92-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fde92-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fde92-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fde92-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fde92-111">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Política de Mobilidade**.</span><span class="sxs-lookup"><span data-stu-id="fde92-111">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="fde92-112">Na página **política de mobilidade** , clique em **novo**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fde92-112">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="fde92-113">Para criar uma política de mobilidade do site, clique em **Política do Site**, clique em um site e en **OK**; reveja as configurações e faça as mudanças desejadas, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="fde92-113">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="fde92-114">Para criar uma política de mobilidade do usuário, clique em **Política do Usuário**, digite um nome, reveja as configurações e faça as mudanças desejadas, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="fde92-114">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="fde92-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fde92-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="fde92-116">Para modificar uma política de mobilidade com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fde92-116">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fde92-117">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fde92-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fde92-118">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fde92-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fde92-119">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fde92-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fde92-120">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Política de Mobilidade**.</span><span class="sxs-lookup"><span data-stu-id="fde92-120">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="fde92-121">Na página **política de mobilidade** , clique em uma das políticas de mobilidade existentes.</span><span class="sxs-lookup"><span data-stu-id="fde92-121">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="fde92-122">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="fde92-122">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fde92-123">Edite as configurações.</span><span class="sxs-lookup"><span data-stu-id="fde92-123">Edit any of the settings.</span></span>

7.  <span data-ttu-id="fde92-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fde92-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fde92-125">Criar políticas de acesso externo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fde92-125">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fde92-126">Você pode criar políticas de mobilidade (no escopo do site ou no escopo por usuário) usando o Windows PowerShell e o cmdlet **New-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="fde92-126">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="fde92-127">Ademais, você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar qualquer política existente, incluindo a política global.</span><span class="sxs-lookup"><span data-stu-id="fde92-127">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="fde92-128">Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fde92-128">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fde92-129">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="fde92-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="fde92-130">Para criar uma política de mobilidade no escopo do site</span><span class="sxs-lookup"><span data-stu-id="fde92-130">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="fde92-131">Esse comando cria uma nova política de mobilidade para o site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="fde92-131">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="fde92-132">Já que nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando precedente, as políticas usarão os valores padrão para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="fde92-132">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="fde92-133">Para criar uma política de mobilidade no escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="fde92-133">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="fde92-134">Para criar uma política de mobilidade no escopo por usuário, especifique uma Identidade exclusiva para a política:</span><span class="sxs-lookup"><span data-stu-id="fde92-134">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="fde92-135">Para alterar um único valor de propriedade ao criar uma política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="fde92-135">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="fde92-p105">Para criar políticas que usam diferentes valores de propriedade, inclua o parâmetro e o valor de parâmetro adequados. Por exemplo, esse comando cria a política de mobilidade que desabilita Chamada via Trabalho:</span><span class="sxs-lookup"><span data-stu-id="fde92-p105">To create policies that use different property values, include the appropriate parameter and parameter value. For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="fde92-138">Para alterar vários valores de propriedade ao criar uma política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="fde92-138">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="fde92-p106">Valores múltiplos de propriedade podem ser modificados incluindo parâmetros múltiplos. Por exemplo, esse comando cria uma política que desabilita mobilidade e Chamada via Trabalho:</span><span class="sxs-lookup"><span data-stu-id="fde92-p106">Multiple property values can be modified by including multiple parameters. For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="fde92-141">Para detalhes, consulte o tópico de ajuda para os cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) e [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="fde92-141">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fde92-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="fde92-142">See Also</span></span>


[<span data-ttu-id="fde92-143">Configurando a política de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fde92-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

