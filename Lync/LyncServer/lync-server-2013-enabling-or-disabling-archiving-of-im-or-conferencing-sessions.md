---
title: Habilitando ou desabilitando o arquivamento de mensagens instantâneas ou sessões de conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2e8ae6928b13c92445a2d61aadab56893231bbe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="2b636-102">Habilitar ou desabilitar o arquivamento de sessões de IM ou de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b636-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b636-103">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="2b636-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="2b636-104">No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar o arquivamento de mensagens instantâneas, sessões de conferência ou ambas.</span><span class="sxs-lookup"><span data-stu-id="2b636-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="2b636-105">Isso inclui as seguintes configurações de Arquivamento:</span><span class="sxs-lookup"><span data-stu-id="2b636-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="2b636-106">Uma configuração global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b636-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2b636-107">Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.</span><span class="sxs-lookup"><span data-stu-id="2b636-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="2b636-108">Inicialmente, as configurações de Arquivamento são definidas ao implantar o Arquivamento, mas você pode alterar, adicionar e excluir configurações depois da implantação.</span><span class="sxs-lookup"><span data-stu-id="2b636-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="2b636-109">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="2b636-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2b636-110">Para usar o arquivamento, você deve configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento de comunicações internas, para comunicações externas ou para usuários hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b636-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="2b636-111">Por padrão, o arquivamento não está ativado para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="2b636-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="2b636-112">Antes de ativar o Arquivamento em qualquer política, é necessário especificar os configurações de Arquivamento apropriadas para a implantação e, opcionalmente, para sites e pools específicos, como descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="2b636-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="2b636-113">Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2b636-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2b636-114">Se você decidir depois de implantar o arquivamento que deseja usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento nos servidores do Exchange 2013 e todos os usuários estão hospedados em seus servidores do Exchange 2013, você deve remover a configuração de banco de dados do SQL Server da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="2b636-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="2b636-115">Você deve usar o construtor de topologias para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="2b636-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="2b636-116">Para obter detalhes, consulte <A href="lync-server-2013-changing-archiving-database-options.md">mudança de opções de banco de dados de arquivamento no Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="2b636-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="2b636-117">Para ativar ou desativar o arquivamento de IM ou sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="2b636-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="2b636-118">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2b636-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b636-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b636-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2b636-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2b636-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2b636-121">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="2b636-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="2b636-122">Selecione a configuração global, de site ou de pool apropriada na lista de configurações de arquivo, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="2b636-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="2b636-123">Para habilitar o arquivamento apenas para sessões de IM (mensagem instantânea), clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="2b636-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="2b636-124">Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.</span><span class="sxs-lookup"><span data-stu-id="2b636-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="2b636-125">Para desabilitar o arquivamento para a política, clique em **Desabilitar arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="2b636-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="2b636-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2b636-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b636-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b636-127">See Also</span></span>


[<span data-ttu-id="2b636-128">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</span><span class="sxs-lookup"><span data-stu-id="2b636-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="2b636-129">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b636-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

