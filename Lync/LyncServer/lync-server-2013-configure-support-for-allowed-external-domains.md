---
title: 'Lync Server 2013: configurar suporte para domínios externos permitidos'
description: 'Lync Server 2013: configurar suporte para domínios externos permitidos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13845638bca8791d43b8644c5dcb30ec73751a5b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553977"
---
# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="3fa41-103">Configurar suporte para domínios externos permitidos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fa41-103">Configure support for allowed external domains in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fa41-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3fa41-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3fa41-p101">Se você configurou suporte para parceiros federados, você pode gerenciar quais domínios federar com a sua organização. Você configura um ou mais domínios externos específicos como domínios federados permitidos. Para fazer isso, adicione cada domínio à lista de domínios permitidos. Mesmo se a descoberta de parceiro estiver habilitada para sua organização, faça isso se o domínio for um parceiro federado que talvez precise se comunicar com mais de 1.000 usuários ou talvez precise enviar mais de 20 mensagens por segundo. Se a descoberta de parceiro não estiver habilitada para a sua organização, somente os usuários de domínios externos que você adiciona à lista de domínios permitidos podem participar em conferência e mensagens instantâneas com usuários em sua organização. Se você quiser restringir o acesso de um domínio federado a um servidor específico que executa o serviço de Borda de Acesso do parceiro federado, poderá especificar o nome de domínio do servidor que executa o serviço de Borda de Acesso para cada domínio na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="3fa41-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fa41-111">Este procedimento descreve como configurar o suporte para domínios específicos, mas implementar suporte para usuários federados também exige que você habilite o suporte para usuários federados de sua organização, bem como configure e aplique políticas para controlar quais usuários podem colaborar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="3fa41-111">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="3fa41-112">Para obter detalhes sobre como habilitar o suporte a usuários federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3fa41-112">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="3fa41-113">Para obter detalhes sobre a configuração de políticas para controlar a Federação, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure Policies to Control Federated User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3fa41-113">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="3fa41-114">Para adicionar um domínio externo à lista de domínios permitidos</span><span class="sxs-lookup"><span data-stu-id="3fa41-114">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="3fa41-115">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3fa41-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3fa41-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3fa41-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3fa41-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3fa41-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3fa41-118">Na barra de navegação esquerda, clique em **Acesso de Usuário Externo** e em **Domínios Federados**.</span><span class="sxs-lookup"><span data-stu-id="3fa41-118">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="3fa41-119">Na página **Domínios Federados**, clique em **Novo** e em **Domínio permitido**.</span><span class="sxs-lookup"><span data-stu-id="3fa41-119">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="3fa41-120">Em **Novos Domínios Federados**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3fa41-120">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="3fa41-121">Em **Nome de domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="3fa41-121">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3fa41-p104">Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para este servidor que executa o serviço de Borda de Acesso. O nome não pode exceder 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3fa41-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="3fa41-p105">A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3fa41-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="3fa41-126">Um domínio de parceiro federado não pode ser simultaneamente bloqueado e permitido.</span><span class="sxs-lookup"><span data-stu-id="3fa41-126">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="3fa41-127">O Lync Server 2013 impede que isso aconteça para que você não precise sincronizar suas listas.</span><span class="sxs-lookup"><span data-stu-id="3fa41-127">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="3fa41-128">Se você quiser restringir o acesso para esse domínio federado a usuários de um servidor específico que execute o serviço de Borda de Acesso, em **Serviço de Borda de Acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="3fa41-128">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="3fa41-129">Se você quiser fornecer informações adicionais, em **Comentário**, digite as informações que deseja compartilhar com outros administradores de sistema sobre essa configuração.</span><span class="sxs-lookup"><span data-stu-id="3fa41-129">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="3fa41-130">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3fa41-130">Click **Commit**.</span></span>

7.  <span data-ttu-id="3fa41-131">Repita as etapas 4 a 6 para cada domínio de parceiro federado que deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="3fa41-131">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="3fa41-132">Para habilitar o acesso de usuário federado, habilite também o suporte para acesso de usuário federado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fa41-132">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="3fa41-133">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3fa41-133">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="3fa41-134">Além disso, você deve configurar e aplicar a política a usuários que possam colaborar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="3fa41-134">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="3fa41-135">Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3fa41-135">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

