---
title: 'Lync Server 2013: habilitando ou desabilitando o modo crítico para bloquear ou permitir mensagens de mensagens instantâneas e webconferência se o arquivamento falhar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="df700-102">Habilitar ou desabilitar o modo crítico no Lync Server 2013 para bloquear ou permitir sessões de mensagens instantâneas e webconferência se o arquivamento falhar</span><span class="sxs-lookup"><span data-stu-id="df700-102">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df700-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="df700-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="df700-104">No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar o modo crítico.</span><span class="sxs-lookup"><span data-stu-id="df700-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable critical mode.</span></span> <span data-ttu-id="df700-105">Isso inclui as seguintes configurações de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="df700-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="df700-106">Uma configuração global criada por padrão quando você implanta o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df700-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="df700-107">Configurações opcionais de nível de site e de pool que você pode criar e usar para especificar como o arquivamento é implementado para sites ou pools específicos.</span><span class="sxs-lookup"><span data-stu-id="df700-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="df700-108">Inicialmente, você define o arquivamento de configurações ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="df700-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="df700-109">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia de configurações de arquivamento, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, implantação documentação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="df700-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df700-110">Para usar o arquivamento, configure as políticas de arquivamento para especificar se o arquivamento de comunicações internas deve ser habilitado, para comunicações externas ou para os usuários hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df700-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="df700-111">Por padrão, o arquivamento não está habilitado para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="df700-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="df700-112">Antes de habilitar o arquivamento em qualquer política, você deve especificar as configurações de arquivamento adequadas para sua implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="df700-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="df700-113">Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar e atribuir políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="df700-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="df700-114">Se você decidir após implantar o arquivamento em que deseja usar a integração com o Exchange Server para armazenar arquivos de arquivamento e arquivos em servidores Exchange 2013 e todos os usuários estiverem hospedados em seus servidores Exchange 2013, você deve remover a configuração de banco de dados SQL Server de sua topologia.</span><span class="sxs-lookup"><span data-stu-id="df700-114">If you decide after you deploy Archiving that you want to use Exchange Server integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="df700-115">Você deve usar o construtor de topologias para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="df700-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="df700-116">Para obter detalhes, consulte <A href="lync-server-2013-changing-archiving-database-options.md">alterando as opções de arquivamento de banco de dados no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="df700-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="df700-117">Para habilitar ou desabilitar o bloqueio de sessões de mensagens instantâneas e webconferências se o arquivamento falhar</span><span class="sxs-lookup"><span data-stu-id="df700-117">To enable or disable blocking of IM and web conferencing sessions if archiving fails</span></span>

1.  <span data-ttu-id="df700-118">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="df700-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df700-119">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df700-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df700-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df700-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df700-121">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="df700-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="df700-122">Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="df700-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>

5.  <span data-ttu-id="df700-123">Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de webconferência e mensagens instantâneas (IM) se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="df700-123">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>

6.  <span data-ttu-id="df700-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="df700-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df700-125">Habilitando e desabilitando o modo crítico usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df700-125">Enabling and Disabling Critical Mode by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="df700-126">Você pode habilitar ou desabilitar o modo crítico usando o cmdlet **set-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="df700-126">You can enable or disable critical mode using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="df700-127">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df700-127">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df700-128">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="df700-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-critical-mode"></a><span data-ttu-id="df700-129">Para habilitar o modo crítico</span><span class="sxs-lookup"><span data-stu-id="df700-129">To enable critical mode</span></span>

  - <span data-ttu-id="df700-130">Para habilitar o modo crítico, defina o valor da propriedade BlockOnArchiveFailure como true ($True).</span><span class="sxs-lookup"><span data-stu-id="df700-130">To enable critical mode, set the value of the BlockOnArchiveFailure property to True ($True).</span></span> <span data-ttu-id="df700-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="df700-131">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a><span data-ttu-id="df700-132">Para desabilitar o modo crítico</span><span class="sxs-lookup"><span data-stu-id="df700-132">To disable critical mode</span></span>

  - <span data-ttu-id="df700-133">Para desabilitar o modo crítico, defina o valor da propriedade BlockOnArchiveFailure como false ($False).</span><span class="sxs-lookup"><span data-stu-id="df700-133">To disable critical mode, set the value of the BlockOnArchiveFailure property to False ($False).</span></span> <span data-ttu-id="df700-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="df700-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

<span data-ttu-id="df700-135">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="df700-135">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df700-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="df700-136">See Also</span></span>


[<span data-ttu-id="df700-137">Alterar as opções de banco de dados de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df700-137">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)  


[<span data-ttu-id="df700-138">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df700-138">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="df700-139">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</span><span class="sxs-lookup"><span data-stu-id="df700-139">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

