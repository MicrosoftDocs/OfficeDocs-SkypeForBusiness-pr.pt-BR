---
title: 'Lync Server 2013: Configurar políticas para controlar o acesso de usuário público'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="5fd17-102">Configurar políticas para controlar o acesso de usuário público no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fd17-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fd17-103">_**Tópico da última modificação:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5fd17-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5fd17-104">A conectividade de mensagens instantâneas públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos pelos provedores de serviços públicos de mensagens instantâneas, incluindo a rede do Windows Live dos serviços de Internet, o Yahoo\!e o AOL.</span><span class="sxs-lookup"><span data-stu-id="5fd17-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="5fd17-105">Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários públicos podem colaborar com usuários internos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fd17-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="5fd17-106">A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração da sua implantação e dos usuários.</span><span class="sxs-lookup"><span data-stu-id="5fd17-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="5fd17-107">Ele também depende do provisionamento do serviço no provedor público de IM.</span><span class="sxs-lookup"><span data-stu-id="5fd17-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="5fd17-108">Para obter informações sobre como provisionar sua implantação para usar os provedores públicos, consulte o guia "guia de provisionamento de conectividade pública de IM para Microsoft Lync Server, Office Communications Server e Live Communications Server":[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="5fd17-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="5fd17-109">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="5fd17-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5fd17-110">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fd17-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5fd17-111">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="5fd17-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="5fd17-112">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fd17-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5fd17-113">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="5fd17-113">has been announced.</span></span> <span data-ttu-id="5fd17-114">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5fd17-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="5fd17-115">O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fd17-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5fd17-116">Spam.</span><span class="sxs-lookup"><span data-stu-id="5fd17-116">Messenger.</span></span> <span data-ttu-id="5fd17-117">A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</span><span class="sxs-lookup"><span data-stu-id="5fd17-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="5fd17-118">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="5fd17-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5fd17-119">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="5fd17-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5fd17-120">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="5fd17-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5fd17-121">Para acessar o site de configuração de conectividade de mensagens instantâneas públicas do Microsoft Lync Server, use o seguinte link:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="5fd17-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="5fd17-122">Para controlar o acesso do usuário público, você pode configurar políticas nos níveis global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="5fd17-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="5fd17-123">Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte Configurando o [suporte para acesso de usuários externos no Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) na documentação de implantação ou documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5fd17-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="5fd17-124">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="5fd17-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5fd17-125">A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="5fd17-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5fd17-126">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="5fd17-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="5fd17-127">No caso de convites por mensagem instantânea, a resposta depende do software cliente.</span><span class="sxs-lookup"><span data-stu-id="5fd17-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="5fd17-128">A solicitação é aceita, a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas **permitir** e **Bloquear** do cliente do usuário).</span><span class="sxs-lookup"><span data-stu-id="5fd17-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="5fd17-129">Além disso, os convites de mensagem instantânea podem ser bloqueados se um usuário optar por bloquear todas as mensagens instantâneas de usuários que não estão na sua lista de **permissões** .</span><span class="sxs-lookup"><span data-stu-id="5fd17-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fd17-130">Você pode configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5fd17-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="5fd17-131">No entanto, as políticas que você configura são efetivadas apenas quando você tem a Federação habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5fd17-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="5fd17-132">Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="5fd17-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="5fd17-133">Além disso, se você especificar uma política de usuário para controlar o acesso ao usuário público, a política se aplicará somente aos usuários habilitados para o Lync Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="5fd17-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="5fd17-134">Para obter detalhes sobre como especificar usuários públicos que podem entrar no Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync server 2013</A> na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="5fd17-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="5fd17-135">Use o procedimento a seguir para configurar uma política para dar suporte ao acesso por usuários de um ou mais provedores de mensagens de chat públicos.</span><span class="sxs-lookup"><span data-stu-id="5fd17-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="5fd17-136">Para configurar uma política de acesso externo para dar suporte ao acesso de usuários públicos</span><span class="sxs-lookup"><span data-stu-id="5fd17-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="5fd17-137">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5fd17-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5fd17-138">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fd17-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fd17-139">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fd17-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fd17-140">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="5fd17-141">Na página **política de acesso externo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fd17-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5fd17-142">Para configurar a política global para dar suporte ao acesso a usuários públicos, clique na política global, clique em **Editar**e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="5fd17-143">Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="5fd17-144">Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="5fd17-145">Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="5fd17-146">Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indique a capa da política do usuário (por exemplo, **EnablePublicUsers** para uma política de usuário que permita comunicações para usuários públicos).</span><span class="sxs-lookup"><span data-stu-id="5fd17-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="5fd17-147">Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5fd17-148">Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="5fd17-149">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fd17-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="5fd17-150">Para habilitar o acesso de usuário público para a política, marque a caixa de seleção **habilitar comunicações com usuários públicos** .</span><span class="sxs-lookup"><span data-stu-id="5fd17-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="5fd17-151">Para desabilitar o acesso de usuário público para a política, desmarque a caixa de seleção **habilitar comunicações com usuários públicos** .</span><span class="sxs-lookup"><span data-stu-id="5fd17-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="5fd17-152">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5fd17-152">Click **Commit**.</span></span>

<span data-ttu-id="5fd17-153">Para habilitar o acesso de usuário público, você também deve habilitar o suporte para Federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5fd17-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="5fd17-154">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5fd17-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="5fd17-155">Se esta for uma política de usuário, você também deverá aplicar a política a usuários públicos que você deseja que possam colaborar com usuários públicos.</span><span class="sxs-lookup"><span data-stu-id="5fd17-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="5fd17-156">Para obter detalhes, consulte [atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5fd17-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fd17-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="5fd17-157">See Also</span></span>


[<span data-ttu-id="5fd17-158">Criar ou editar fornecedores SIP públicos federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fd17-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="5fd17-159">Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fd17-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

