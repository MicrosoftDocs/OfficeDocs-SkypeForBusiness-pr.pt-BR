---
title: 'Lync Server 2013: configurar suporte para domínios externos bloqueados'
description: 'Lync Server 2013: configurar suporte para domínios externos bloqueados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c2c76dc32dd5e8d458dad4e91ff375d2ab005c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576677"
---
# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="a2d86-103">Configurar suporte para domínios externos bloqueados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d86-103">Configure support for blocked external domains in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2d86-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a2d86-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a2d86-105">Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios serão impedidos de Federação na sua organização.</span><span class="sxs-lookup"><span data-stu-id="a2d86-105">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="a2d86-106">A lista de domínios bloqueados atuará como uma lista de bloqueios (lista de entradas explícitas que não devem ser permitidas) e será aplicada em descoberta de domínio federado, se você tiver essa opção habilitada.</span><span class="sxs-lookup"><span data-stu-id="a2d86-106">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="a2d86-107">Para obter detalhes, consulte [habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="a2d86-107">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="a2d86-108">Bloquear um ou mais domínios externos para se conectar à sua organização.</span><span class="sxs-lookup"><span data-stu-id="a2d86-108">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="a2d86-109">Para fazer isso, adicione o domínio à lista de domínios bloqueados.</span><span class="sxs-lookup"><span data-stu-id="a2d86-109">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="a2d86-110">Para adicionar um domínio externo à lista de domínios bloqueados</span><span class="sxs-lookup"><span data-stu-id="a2d86-110">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="a2d86-111">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a2d86-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a2d86-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2d86-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2d86-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a2d86-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2d86-114">Na barra de navegação esquerda, clique em **Acesso de Usuário Externo**.</span><span class="sxs-lookup"><span data-stu-id="a2d86-114">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="a2d86-115">Clique em **domínios federados**, clique em **novo**e em **domínio bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="a2d86-115">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="a2d86-116">Em **Novos Domínios Federados**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a2d86-116">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="a2d86-117">Em **nome de domínio (ou FQDN)**, digite o nome do domínio de parceiro federado que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="a2d86-117">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2d86-118">O nome não pode exceder 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a2d86-118">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="a2d86-p104">A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2d86-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="a2d86-121">Um domínio de parceiro federado não pode ser simultaneamente bloqueado e permitido.</span><span class="sxs-lookup"><span data-stu-id="a2d86-121">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="a2d86-122">O Lync Server 2013 impede que isso aconteça para que você não precise sincronizar suas listas.</span><span class="sxs-lookup"><span data-stu-id="a2d86-122">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2d86-123">Opcion Em **Comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.</span><span class="sxs-lookup"><span data-stu-id="a2d86-123">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="a2d86-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a2d86-124">Click **Commit**.</span></span>

7.  <span data-ttu-id="a2d86-125">Repita as etapas de 4 a 6 para cada parceiro federado que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="a2d86-125">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="a2d86-126">Para habilitar o acesso de usuário federado, habilite também o suporte para acesso de usuário federado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a2d86-126">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="a2d86-127">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a2d86-127">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="a2d86-128">Além disso, você deve configurar e aplicar a política a usuários que possam colaborar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="a2d86-128">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a2d86-129">Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a2d86-129">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

