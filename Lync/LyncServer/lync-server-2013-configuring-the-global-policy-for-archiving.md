---
title: 'Lync Server 2013: Configurando a política global para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589c249f772b130eeed80abb97e272b8053dfdc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532378"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="8d2e4-102">Configurando a política global para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d2e4-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d2e4-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8d2e4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8d2e4-104">Ao implantar seus servidores front-end, o Lync Server cria uma política global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="8d2e4-105">Por padrão, o arquivamento está desabilitado na política global.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="8d2e4-106">A política global controla se o arquivamento está habilitado para comunicações internas e externas para toda a sua implantação, a menos que você configure políticas de site ou de usuário, que substituem a política global ou se você usar a integração do Microsoft Exchange para alguns ou todos os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="8d2e4-107">Se você usar a integração com o Microsoft Exchange, a política global não se aplicará a nenhum usuário hospedado no Exchange 2013 e ter as caixas de correio colocadas em In-Place isenção.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="8d2e4-108">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d2e4-109">Se você habilitar a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlará se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e se suas caixas de correio serão colocadas In-Place isenção.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8d2e4-110">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="8d2e4-111">Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="8d2e4-112">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="8d2e4-113">Para configurar a política global para arquivamento ao utilizar bancos de dados de arquivamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8d2e4-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="8d2e4-114">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8d2e4-115">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="8d2e4-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8d2e4-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8d2e4-117">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="8d2e4-118">Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8d2e4-119">Em **Editar Política de Arquivamento - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8d2e4-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="8d2e4-120">Em **Nome**, se não desejar usar o nome padrão de global, especifique um novo nome para a política global.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="8d2e4-121">Em **Descrição**, forneça informações sobre o que a política é (por exemplo, a política global para *divisionName*).</span><span class="sxs-lookup"><span data-stu-id="8d2e4-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="8d2e4-122">Para controlar o arquivamento de comunicações internas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="8d2e4-123">Para controlar o arquivamento de comunicações externas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="8d2e4-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8d2e4-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

