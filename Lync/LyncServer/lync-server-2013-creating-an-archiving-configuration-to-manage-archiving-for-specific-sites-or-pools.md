---
title: 'Lync Server 2013: criar uma configuração de arquivamento para gerenciar o arquivamento de sites ou pools específicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c9e12c01efe461da65fc9b87b4a1f87d526e52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="eafbe-102">Criar uma configuração de arquivamento no Lync Server 2013 para gerenciar o arquivamento de sites ou pools específicos</span><span class="sxs-lookup"><span data-stu-id="eafbe-102">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eafbe-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eafbe-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eafbe-104">No painel de controle do Lync Server 2013, você usa configurações de arquivamento para controlar como o arquivamento é implementado em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="eafbe-104">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="eafbe-105">Isso inclui as seguintes configurações de Arquivamento:</span><span class="sxs-lookup"><span data-stu-id="eafbe-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="eafbe-106">Uma configuração global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eafbe-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="eafbe-107">Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.</span><span class="sxs-lookup"><span data-stu-id="eafbe-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="eafbe-108">Inicialmente, as configurações de Arquivamento são definidas ao implantar o Arquivamento, mas você pode alterar, adicionar e excluir configurações depois da implantação.</span><span class="sxs-lookup"><span data-stu-id="eafbe-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="eafbe-109">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="eafbe-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eafbe-110">Para usar o arquivamento, você deve configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento de comunicações internas, para comunicações externas ou para usuários hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eafbe-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="eafbe-111">Por padrão, o arquivamento não está ativado para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="eafbe-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="eafbe-112">Antes de ativar o Arquivamento em qualquer política, é necessário especificar os configurações de Arquivamento apropriadas para a implantação e, opcionalmente, para sites e pools específicos, como descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="eafbe-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="eafbe-113">Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="eafbe-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="eafbe-114">Se você decidir depois de implantar o arquivamento que deseja usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento nos servidores do Exchange 2013 e todos os usuários estão hospedados em seus servidores do Exchange 2013, você deve remover a configuração de banco de dados do SQL Server da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="eafbe-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="eafbe-115">Você deve usar o construtor de topologias para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="eafbe-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="eafbe-116">Para obter detalhes, consulte <A href="lync-server-2013-changing-archiving-database-options.md">mudança de opções de banco de dados de arquivamento no Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="eafbe-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="eafbe-117">Para criar uma configuração de arquivamento de um site ou pool</span><span class="sxs-lookup"><span data-stu-id="eafbe-117">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="eafbe-118">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="eafbe-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eafbe-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eafbe-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eafbe-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eafbe-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eafbe-121">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="eafbe-122">Na página **Configuração de arquivamento**, clique em \*\*Novo \*\* e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="eafbe-122">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="eafbe-123">Para criar uma configuração de arquivamento local, clique em **Configuração local** e, em **Selecionar um local**, selecione o local a ser configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="eafbe-123">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="eafbe-124">Para criar uma configuração de arquivamento do pool, clique em **Configuração do pool** e, em **Selecionar um pool**, selecione o pool a ser configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="eafbe-124">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="eafbe-125">Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="eafbe-125">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="eafbe-126">Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-126">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="eafbe-127">Para habilitar o arquivamento para sessões de IM e conferências da Web, clique em **Arquivar sessões de IM e conferência da Web**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-127">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="eafbe-128">Para desabilitar o arquivamento da política, clique em **Desabilitar arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-128">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="eafbe-129">Também em **Nova configuração de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eafbe-129">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="eafbe-130">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-130">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="eafbe-131">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração com o Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="eafbe-131">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="eafbe-132">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="eafbe-132">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="eafbe-133">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="eafbe-133">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="eafbe-134">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-134">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="eafbe-135">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eafbe-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eafbe-136">Criar definições de configuração de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eafbe-136">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eafbe-137">As definições de configuração de arquivamento podem ser criadas usando o Windows PowerShell e o cmdlet New-CsArchivingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="eafbe-137">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="eafbe-138">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eafbe-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eafbe-139">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="eafbe-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="eafbe-140">Para criar um novo conjunto de definições de configuração de arquivamento para um site</span><span class="sxs-lookup"><span data-stu-id="eafbe-140">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="eafbe-141">O comando a seguir cria um novo conjunto de definições de configuração de arquivamento para o local Redmond:</span><span class="sxs-lookup"><span data-stu-id="eafbe-141">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="eafbe-142">Para criar um novo conjunto de definições de configuração de arquivamento que permitam apenas o arquivamento de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="eafbe-142">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="eafbe-p107">Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi associado no comando anterior, o novo conjunto de definições de configuração usará os valores padrões para todas as suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar um conjunto de definições de configuração de arquivamento que, por padrão, permite o arquivamento de sessões de mensagem instantânea, use apenas um comando como este:</span><span class="sxs-lookup"><span data-stu-id="eafbe-p107">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="eafbe-146">Para especificar vários valores de propriedade ao criar definições de configuração de arquivamento</span><span class="sxs-lookup"><span data-stu-id="eafbe-146">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="eafbe-p108">Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, este comando define a nova configuração para arquivar sessões de mensagem instantânea e o bloqueio de mensagem instantânea do serviço de arquivamento não está disponível:</span><span class="sxs-lookup"><span data-stu-id="eafbe-p108">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="eafbe-149">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="eafbe-149">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eafbe-150">Confira Também</span><span class="sxs-lookup"><span data-stu-id="eafbe-150">See Also</span></span>


[<span data-ttu-id="eafbe-151">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eafbe-151">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="eafbe-152">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</span><span class="sxs-lookup"><span data-stu-id="eafbe-152">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

