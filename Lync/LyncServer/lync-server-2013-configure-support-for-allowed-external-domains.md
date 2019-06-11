---
title: 'Lync Server 2013: Configurar suprote para domínios externos permitidos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="5e2e3-102">Configurar suprote para domínios externos permitidos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e2e3-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e2e3-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5e2e3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5e2e3-104">Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios específicos podem federar a sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-104">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="5e2e3-105">Você pode configurar um ou mais domínios externos específicos como domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-105">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="5e2e3-106">Para fazer isso, adicione cada domínio à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-106">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="5e2e3-107">Mesmo se a descoberta de parceiro estiver habilitada para sua organização, faça isso se o domínio for um parceiro federado que pode precisar se comunicar com mais de 1.000 de seus usuários ou talvez precise enviar mais de 20 mensagens por segundo.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-107">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="5e2e3-108">Se a descoberta de parceiro não estiver habilitada para sua organização, somente os usuários de domínios externos que você adicionar à lista de domínios permitidos poderão participar de mensagens instantâneas e conferência com os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-108">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="5e2e3-109">Se quiser restringir o acesso de um domínio federado a um servidor específico executando o serviço de borda de acesso do parceiro federado, você pode especificar o nome de domínio do servidor que executa o serviço de borda de acesso para cada domínio na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-109">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e2e3-110">Este procedimento descreve como configurar o suporte para domínios específicos, mas a implementação do suporte a usuários federados também requer que você habilite o suporte para usuários federados para sua organização e configure e aplique políticas para controlar quais usuários podem Colabore com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="5e2e3-111">Para obter detalhes sobre como habilitar o suporte a usuários federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="5e2e3-112">Para obter detalhes sobre a configuração de políticas para controlar a Federação, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="5e2e3-113">Para adicionar um domínio externo à lista de domínios permitidos</span><span class="sxs-lookup"><span data-stu-id="5e2e3-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="5e2e3-114">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5e2e3-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5e2e3-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5e2e3-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5e2e3-117">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **domínios federados**.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="5e2e3-118">Na página **domínios federados** , clique em **novo**e, em seguida, clique em **domínio permitido**.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="5e2e3-119">Em **novos domínios federados**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5e2e3-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="5e2e3-120">Em **nome do domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5e2e3-121">Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para este servidor que está executando o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-121">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="5e2e3-122">O nome não pode exceder 256 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-122">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="5e2e3-123">A pesquisa no nome de domínio do parceiro federado executa uma correspondência de sufixo.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-123">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="5e2e3-124">Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-124">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="5e2e3-125">Um domínio de parceiro federado não pode ser bloqueado e permitido simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="5e2e3-126">O Lync Server 2013 evita que isso aconteça para que você não precise sincronizar suas listas.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="5e2e3-127">Se você quiser restringir o acesso para esse domínio federado para os usuários de um servidor específico executando o serviço de borda de acesso, no **serviço de borda de acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="5e2e3-128">Se você quiser fornecer informações adicionais, em **Comentário**, digite as informações que deseja compartilhar com outros administradores de sistema sobre essa configuração.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="5e2e3-129">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="5e2e3-130">Repita as etapas 4 a 6 para cada domínio de parceiro federado que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="5e2e3-131">Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para o acesso de usuários federados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="5e2e3-132">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5e2e3-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="5e2e3-133">Além disso, você deve configurar e aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="5e2e3-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="5e2e3-134">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5e2e3-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

