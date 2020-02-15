---
title: 'Lync Server 2013: configurar políticas de site para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fd9e63ad6aec440c090b4303a32cba37953e1d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="17d3e-102">Configurando políticas de site para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17d3e-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17d3e-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="17d3e-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="17d3e-104">Você pode habilitar ou desabilitar o arquivamento de sites específicos criando e configurando uma política de arquivamento para cada um desses sites.</span><span class="sxs-lookup"><span data-stu-id="17d3e-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="17d3e-105">Uma política de site substitui a política global, mas as políticas de usuário substituem as políticas de site.</span><span class="sxs-lookup"><span data-stu-id="17d3e-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="17d3e-106">As políticas de arquivamento só se aplicam se você não usar a integração com o Microsoft Exchange ou se você usar a integração com o Microsoft Exchange, mas têm alguns usuários que não estão hospedados no Exchange 2013 e têm suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="17d3e-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="17d3e-107">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17d3e-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17d3e-108">Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="17d3e-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="17d3e-109">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="17d3e-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="17d3e-110">Você deve especificar todas as opções adequadas nas configurações de Arquivamento antes de habilitar o Arquivamento de comunicações internas e externas nas políticas de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="17d3e-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="17d3e-111">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="17d3e-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="17d3e-112">Para criar uma política de arquivamento para um site</span><span class="sxs-lookup"><span data-stu-id="17d3e-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="17d3e-113">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="17d3e-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17d3e-114">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17d3e-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="17d3e-115">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="17d3e-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="17d3e-116">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17d3e-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="17d3e-117">Clique em **Novo** e, em seguida, em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="17d3e-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="17d3e-118">Em **selecionar um site**, clique no site ao qual a política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="17d3e-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="17d3e-119">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="17d3e-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="17d3e-120">Em **nome**, especifique o nome da política de site.</span><span class="sxs-lookup"><span data-stu-id="17d3e-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="17d3e-121">Em **Descrição**, forneça informações sobre o que é a política de site (por exemplo, política de site para Redmond).</span><span class="sxs-lookup"><span data-stu-id="17d3e-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="17d3e-122">Para controlar o arquivamento de comunicações internas do site especificado, marque ou desmarque a caixa de seleção **arquivar comunicações internas** .</span><span class="sxs-lookup"><span data-stu-id="17d3e-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="17d3e-123">Para controlar o arquivamento de comunicações externas para o site especificado, marque ou desmarque a caixa de seleção **arquivar comunicações externas** .</span><span class="sxs-lookup"><span data-stu-id="17d3e-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="17d3e-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="17d3e-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

