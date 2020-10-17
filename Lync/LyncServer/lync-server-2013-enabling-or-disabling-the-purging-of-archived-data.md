---
title: 'Lync Server 2013: habilitando ou desabilitando a limpeza de dados arquivados'
description: 'Lync Server 2013: habilitando ou desabilitando a limpeza de dados arquivados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 442b99e2cfa6db303ca8edd216cbdf3b5c13cea9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546457"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="22328-103">Habilitando ou desabilitando a limpeza de dados arquivados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22328-103">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22328-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="22328-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="22328-105">No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar a limpeza e configurar como a limpeza é implementada.</span><span class="sxs-lookup"><span data-stu-id="22328-105">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="22328-106">Isso inclui as seguintes configurações de Arquivamento:</span><span class="sxs-lookup"><span data-stu-id="22328-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="22328-107">Uma configuração global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22328-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="22328-108">Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.</span><span class="sxs-lookup"><span data-stu-id="22328-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="22328-109">Inicialmente, as configurações de Arquivamento são definidas ao implantar o Arquivamento, mas você pode alterar, adicionar e excluir configurações depois da implantação.</span><span class="sxs-lookup"><span data-stu-id="22328-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="22328-110">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="22328-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22328-111">Para usar o arquivamento para usuários hospedados no Lync Server 2013, você deve configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento para comunicações internas, para comunicações externas ou para ambos.</span><span class="sxs-lookup"><span data-stu-id="22328-111">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="22328-112">Por padrão, o arquivamento não é habilitado para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="22328-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="22328-113">Antes de habilitar o Arquivamento em qualquer política, você deve especificar as configurações apropriadas de Arquivamento para sua Implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="22328-113">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="22328-114">Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="22328-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="22328-115">Se você decidir depois de implantar o arquivamento que deseja usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento nos servidores do Exchange 2013 e todos os usuários estão hospedados em seus servidores do Exchange 2013, você deve remover a configuração de banco de dados do SQL Server da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="22328-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="22328-116">Você deve usar o construtor de topologias para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="22328-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="22328-117">Para obter detalhes, consulte <A href="lync-server-2013-changing-archiving-database-options.md">mudança de opções de banco de dados de arquivamento no Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="22328-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="22328-118">Para habilitar ou desabilitar a limpeza do arquivamento</span><span class="sxs-lookup"><span data-stu-id="22328-118">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="22328-119">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22328-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22328-120">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22328-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22328-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22328-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22328-122">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="22328-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="22328-123">Clique no nome da configuração global, local ou do pool adequado na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22328-123">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="22328-124">Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="22328-124">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="22328-125">Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="22328-125">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="22328-126">Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="22328-126">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="22328-127">Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="22328-127">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="22328-128">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22328-128">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="22328-129">Habilitar ou desabilitar a limpeza de dados de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22328-129">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="22328-130">Habilitar e desabilitar a limpeza automatizada de dados de arquivamento pode ser gerenciada usando o Windows PowerShell e o cmdlet **set-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="22328-130">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="22328-131">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22328-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="22328-132">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="22328-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="22328-133">Para habilitar a limpeza de todos os dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="22328-133">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="22328-134">Para habilitar a exclusão de todos os dados de arquivamento, defina a propriedade **EnablePurging** para verdadeiro ($True).</span><span class="sxs-lookup"><span data-stu-id="22328-134">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="22328-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22328-135">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="22328-136">Depois que esse comando for executado, todos os dias que o Lync Server excluirá todos os registros de arquivamento mais antigos do que o valor especificado para a propriedade **KeepArchivingDataForDays** .</span><span class="sxs-lookup"><span data-stu-id="22328-136">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="22328-137">Para habilitar a limpeza apenas de dados de arquivamento exportados</span><span class="sxs-lookup"><span data-stu-id="22328-137">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="22328-138">Para limitar a limpeza aos registros de arquivamento que foram exportados para um arquivo de dados (usando o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), você também deve definir a propriedade PurgeExportedArchivesOnly como True ($true).</span><span class="sxs-lookup"><span data-stu-id="22328-138">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="22328-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22328-139">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="22328-140">Após este comando ser executado, o Lync Server excluirá apenas os registros de arquivamento que atendem a dois critérios: 1) eles são mais antigos do que o valor especificado para a propriedade **KeepArchivingDataForDays** ; e 2) eles foram exportados usando o cmdlet **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="22328-140">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="22328-141">Para desabilitar a limpeza de todos os dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="22328-141">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="22328-142">Para desabilitar a exclusão automática dos registros de arquivamento, defina a propriedade **EnablePurging** para False ($False).</span><span class="sxs-lookup"><span data-stu-id="22328-142">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="22328-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22328-143">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="22328-144">Para obter mais informações, incluindo opções adicionais para a limpeza de dados de arquivamento, consulte o tópico de ajuda referente ao cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="22328-144">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22328-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="22328-145">See Also</span></span>


[<span data-ttu-id="22328-146">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22328-146">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="22328-147">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22328-147">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="22328-148">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</span><span class="sxs-lookup"><span data-stu-id="22328-148">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

