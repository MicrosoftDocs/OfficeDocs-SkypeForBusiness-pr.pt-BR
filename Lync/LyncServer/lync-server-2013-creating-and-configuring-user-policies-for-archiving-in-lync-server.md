---
title: Criando e Configurando políticas de usuário para arquivamento no Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40425957d472da2d31d91472634f268dde5b8c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504668"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="43232-102">Criando e Configurando políticas de usuário para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43232-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43232-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="43232-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="43232-104">Para habilitar ou desabilitar o arquivamento para usuários específicos hospedados no Lync Server, você deve primeiro criar uma política de usuário e, em seguida, aplicar a política a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="43232-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="43232-105">Para obter detalhes sobre como aplicar políticas de usuário a usuários específicos e grupos de usuários, consulte [aplicando uma política de arquivamento do Lync Server a um usuário no Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="43232-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="43232-106">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, na documentação de implantação ou na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="43232-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="43232-107">Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlam se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e que suas caixas de correio sejam colocadas In-Place isenção.</span><span class="sxs-lookup"><span data-stu-id="43232-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="43232-108">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="43232-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="43232-109">Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="43232-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="43232-110">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="43232-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="43232-111">Para configurar uma política de arquivamento para usuários hospedados no Lync Server</span><span class="sxs-lookup"><span data-stu-id="43232-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="43232-112">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="43232-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43232-113">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43232-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="43232-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="43232-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43232-115">Na barra de navegação esquerda, clique em **Monitoração e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="43232-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="43232-116">Clique em **Novo** e em **Política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="43232-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="43232-117">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="43232-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="43232-118">Em **Nome**, especifique o nome da política de usuário.</span><span class="sxs-lookup"><span data-stu-id="43232-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="43232-119">Em **Descrição**, forneça informações sobre a política de usuário (por exemplo, política de usuário do departamento jurídico).</span><span class="sxs-lookup"><span data-stu-id="43232-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="43232-120">Para controlar o arquivamento das comunicações internas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="43232-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="43232-121">Para controlar o arquivamento das comunicações externas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="43232-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="43232-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="43232-122">Click **Commit**.</span></span>

<span data-ttu-id="43232-123">Uma política de usuário aplica-se somente aos usuários aos quais você a atribui.</span><span class="sxs-lookup"><span data-stu-id="43232-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="43232-124">Para obter detalhes sobre como aplicar uma política de usuário a usuários específicos, consulte [aplicando uma política de arquivamento do Lync Server a um usuário no Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="43232-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

