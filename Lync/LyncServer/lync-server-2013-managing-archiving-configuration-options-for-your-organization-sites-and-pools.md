---
title: 'Lync Server 2013: Gerenciando opções de configuração de arquivamento para sua organização, sites e pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="9b788-102">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</span><span class="sxs-lookup"><span data-stu-id="9b788-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b788-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9b788-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9b788-104">No painel de controle do Lync Server 2013, você usa configurações de arquivamento para especificar como o arquivamento é implementado.</span><span class="sxs-lookup"><span data-stu-id="9b788-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="9b788-105">Isso inclui as seguintes configurações de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="9b788-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="9b788-106">Uma configuração global criada por padrão quando você implanta o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b788-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="9b788-107">Configurações opcionais de nível de site e de pool que você pode criar e usar para especificar como o arquivamento é implementado para sites ou pools específicos.</span><span class="sxs-lookup"><span data-stu-id="9b788-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="9b788-108">Inicialmente, você define o arquivamento de configurações ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="9b788-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9b788-109">No painel de controle do Lync Server 2013, você pode usar a página de **configuração de arquivamento** do grupo **arquivamento e monitoramento** para gerenciar as configurações no nível global, no nível do site e no nível do pool.</span><span class="sxs-lookup"><span data-stu-id="9b788-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="9b788-110">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia de configurações de arquivamento, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="9b788-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b788-111">Para usar o arquivamento, configure as políticas de arquivamento para especificar se o arquivamento deve ser habilitado para comunicações internas, para comunicações externas ou para todos os usuários em um local no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b788-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="9b788-112">Por padrão, o arquivamento não está habilitado para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="9b788-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="9b788-113">Se você usa a integração do Microsoft Exchange, deve habilitar e configurar o Exchange 2013 para dar suporte ao arquivamento para todos os usuários hospedados no Exchange 2013 que tiveram suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="9b788-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="9b788-114">Antes de habilitar o arquivamento, você deve especificar as configurações de arquivamento adequadas para a sua implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="9b788-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="9b788-115">Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar e atribuir políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9b788-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="9b788-116">**Para exibir as informações de configuração de arquivamento usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9b788-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="9b788-117">Você pode exibir informações de configuração de arquivamento usando o Windows PowerShell e o cmdlet **Get-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9b788-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="9b788-118">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b788-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9b788-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="9b788-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="9b788-120">No Shell de gerenciamento do Lync Server, use o seguinte comando para exibir informações sobre todas as suas configurações de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="9b788-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="9b788-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9b788-121">In This Section</span></span>

  - [<span data-ttu-id="9b788-122">Criando uma configuração de arquivamento no Lync Server 2013 para gerenciar o arquivamento de sites ou pools específicos</span><span class="sxs-lookup"><span data-stu-id="9b788-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="9b788-123">Habilitar ou desabilitar o arquivamento de sessões de mensagens instantâneas ou de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b788-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="9b788-124">Habilitar ou desabilitar a limpeza de dados arquivados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b788-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="9b788-125">Habilitar ou desabilitar o modo crítico no Lync Server 2013 para bloquear ou permitir sessões de mensagens instantâneas e webconferência se o arquivamento falhar</span><span class="sxs-lookup"><span data-stu-id="9b788-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="9b788-126">Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b788-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="9b788-127">Habilitando ou desabilitando a integração do Lync Server 2013 com armazenamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="9b788-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="9b788-128">Excluindo uma configuração de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b788-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b788-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="9b788-129">See Also</span></span>


[<span data-ttu-id="9b788-130">Gerenciando Arquivamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b788-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

