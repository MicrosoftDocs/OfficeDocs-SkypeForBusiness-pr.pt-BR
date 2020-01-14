---
title: Gerenciando o arquivamento de comunicações internas e externas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891318ba677891916af678b74365026d20d69016
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="21b20-102">Gerenciar o arquivamento de comunicações internas e externas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21b20-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21b20-103">_**Tópico da última modificação:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="21b20-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="21b20-104">No Lync Server 2013, você usa políticas de arquivamento para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas se você não usar a integração com o Microsoft Exchange ou se tiver usuários que não são hospedados no Exchange 2013 com suas caixas de correio colocadas em Bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="21b20-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="21b20-105">Isso inclui as seguintes políticas de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="21b20-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="21b20-106">Uma política global criada por padrão quando você implanta o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21b20-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="21b20-107">Políticas opcionais no nível do site e no nível do usuário que você pode criar e usar para especificar como o arquivamento é implementado para sites ou usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="21b20-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="21b20-108">Inicialmente, você define as políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir políticas após a implantação.</span><span class="sxs-lookup"><span data-stu-id="21b20-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="21b20-109">No painel de controle do Lync Server 2013, você pode usar a página **política de arquivamento** do grupo **arquivamento e monitoramento** para gerenciar políticas em nível global, nível de site e nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="21b20-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="21b20-110">Se você integrar o armazenamento do Lync Server ao armazenamento do Exchange 2013, as políticas de usuário do Exchange terão precedência sobre as políticas de arquivamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21b20-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="21b20-111">Para obter detalhes sobre como as políticas são implementadas, incluindo a hierarquia de políticas, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="21b20-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="21b20-112">Para controlar a implementação do arquivamento, você deve especificar opções em configurações de arquivamento, como se deseja arquivar mensagens instantâneas ou conferências, o uso do modo crítico e as opções de limpeza.</span><span class="sxs-lookup"><span data-stu-id="21b20-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="21b20-113">Por padrão, nenhuma opção é habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="21b20-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="21b20-114">Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento para comunicações internas ou externas nas políticas de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="21b20-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="21b20-115">Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="21b20-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="21b20-116">Se você habilitar a integração do Microsoft Exchange para a implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="21b20-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="21b20-117">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="21b20-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21b20-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="21b20-118">In This Section</span></span>

  - [<span data-ttu-id="21b20-119">Criar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos</span><span class="sxs-lookup"><span data-stu-id="21b20-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="21b20-120">Alterar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sua organização, sites ou usuários</span><span class="sxs-lookup"><span data-stu-id="21b20-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="21b20-121">Aplicação de uma política de arquivamento a usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21b20-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="21b20-122">Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="21b20-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="21b20-123">Excluindo uma política de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21b20-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

