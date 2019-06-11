---
title: 'Lync Server 2013: Configurar suporte para domínios externos bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="1e12a-102">Configurar suporte para domínios externos bloqueados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e12a-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e12a-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1e12a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1e12a-104">Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios serão bloqueados a partir da Federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e12a-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="1e12a-105">A lista de domínios bloqueados atuará como uma lista de blocos (lista de entradas explícitas que não são permitidas) e será aplicada à descoberta de domínio federado, se você tiver essa opção habilitada.</span><span class="sxs-lookup"><span data-stu-id="1e12a-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="1e12a-106">Para obter detalhes, consulte [habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="1e12a-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="1e12a-107">Bloquear um ou mais domínios externos para se conectar à sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e12a-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="1e12a-108">Para fazer isso, adicione o domínio à lista de domínios bloqueados.</span><span class="sxs-lookup"><span data-stu-id="1e12a-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="1e12a-109">Para adicionar um domínio externo à lista de domínios bloqueados</span><span class="sxs-lookup"><span data-stu-id="1e12a-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="1e12a-110">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1e12a-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1e12a-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e12a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1e12a-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1e12a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1e12a-113">Na barra de navegação à esquerda, clique em **acesso de usuário externo**.</span><span class="sxs-lookup"><span data-stu-id="1e12a-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="1e12a-114">Clique em **domínios federados**, clique em **novo**e, em seguida, clique em **domínio bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="1e12a-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="1e12a-115">Em **novos domínios federados**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1e12a-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="1e12a-116">Em **nome do domínio (ou FQDN)**, digite o nome do domínio do parceiro federado que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="1e12a-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1e12a-117">O nome não pode exceder 256 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="1e12a-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="1e12a-118">A pesquisa no nome de domínio do parceiro federado executa uma correspondência de sufixo.</span><span class="sxs-lookup"><span data-stu-id="1e12a-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="1e12a-119">Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1e12a-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="1e12a-120">Um domínio de parceiro federado não pode ser bloqueado e permitido simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="1e12a-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="1e12a-121">O Lync Server 2013 evita que isso aconteça para que você não precise sincronizar suas listas.</span><span class="sxs-lookup"><span data-stu-id="1e12a-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="1e12a-122">Adicionais Em **Comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.</span><span class="sxs-lookup"><span data-stu-id="1e12a-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="1e12a-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1e12a-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="1e12a-124">Repita as etapas 4 a 6 para cada parceiro federado que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="1e12a-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="1e12a-125">Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para o acesso de usuários federados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e12a-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="1e12a-126">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1e12a-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="1e12a-127">Além disso, você deve configurar e aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="1e12a-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="1e12a-128">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1e12a-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

