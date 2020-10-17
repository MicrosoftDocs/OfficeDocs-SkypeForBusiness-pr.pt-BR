---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuários públicos'
description: 'Lync Server 2013: configurar políticas para controlar o acesso de usuários públicos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d44437cc288d1515784af8c635f4b28902c4fa1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548727"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="1340f-103">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1340f-103">Configure policies to control public user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1340f-104">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="1340f-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="1340f-105">A conectividade de mensagens instantâneas (IM) pública permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores de serviço de IM públicos, incluindo a rede do Windows Live de serviços de Internet, Yahoo \! e AOL.</span><span class="sxs-lookup"><span data-stu-id="1340f-105">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="1340f-106">Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários públicos podem colaborar com usuários internos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1340f-106">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="1340f-107">A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração de sua implantação e dos usuários.</span><span class="sxs-lookup"><span data-stu-id="1340f-107">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="1340f-108">Também depende do provisionamento do serviço no provedor de IM público.</span><span class="sxs-lookup"><span data-stu-id="1340f-108">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="1340f-109">Para obter informações sobre como provisionar sua implantação para usar os provedores públicos, consulte o guia "Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server e Live Communications Server": [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="1340f-109">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="1340f-110">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="1340f-110">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1340f-111">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1340f-111">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1340f-112">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="1340f-112">Messenger until the service shut down date.</span></span> <span data-ttu-id="1340f-113">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1340f-113">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1340f-114">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="1340f-114">has been announced.</span></span> <span data-ttu-id="1340f-115">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1340f-115">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="1340f-116">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1340f-116">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1340f-117">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="1340f-117">Messenger.</span></span> <span data-ttu-id="1340f-118">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="1340f-118">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="1340f-119">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="1340f-119">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1340f-120">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="1340f-120">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1340f-121">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="1340f-121">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1340f-122">Para acessar o site de provisionamento da conectividade de IM pública do Microsoft Lync Server, use o seguinte link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="1340f-122">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="1340f-123">Para controlar o acesso do usuário público, é possível configurar políticas no nível global, site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="1340f-123">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="1340f-124">Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte [Configurando o suporte para acesso de usuário externo no Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) na documentação de implantação ou na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1340f-124">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="1340f-125">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="1340f-125">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1340f-126">A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência).</span><span class="sxs-lookup"><span data-stu-id="1340f-126">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1340f-127">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="1340f-127">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="1340f-p106">No caso de convites de IM, a resposta depende do software cliente. A solicitação é aceita a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas de cliente **Permitir** e **Bloquear** do usuário). Além disso, os convites de IM podem ser bloqueados se um usuário optar por bloquear toda IM de usuários que não estão na lista **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="1340f-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1340f-131">É possível configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1340f-131">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="1340f-132">No entanto, as políticas configuradas entram em vigor somente quando a federação está habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1340f-132">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="1340f-133">Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="1340f-133">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="1340f-134">Além disso, se você especificar uma política de usuário para controlar o acesso de usuário público, a política será aplicada somente aos usuários habilitados para o Lync Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="1340f-134">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="1340f-135">Para obter detalhes sobre como especificar usuários públicos que podem entrar no Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync server 2013</A> na documentação de implantação ou na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="1340f-135">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="1340f-136">Use o procedimento a seguir para configurar uma política para suportar o acesso de usuários de um ou mais provedores de IM público.</span><span class="sxs-lookup"><span data-stu-id="1340f-136">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="1340f-137">Para configurar uma política de acesso externo para suportar o acesso de usuário público</span><span class="sxs-lookup"><span data-stu-id="1340f-137">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="1340f-138">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1340f-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1340f-139">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1340f-139">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1340f-140">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1340f-140">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1340f-141">Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="1340f-141">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1340f-142">Na página **Política de Acesso Externo**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="1340f-142">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1340f-143">Para configurar a política global a fim de suportar o acesso de usuário público, clique na política global, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="1340f-143">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="1340f-p109">Para criar uma nova política de site, clique em **Novo** e clique em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1340f-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="1340f-p110">Para criar uma nova política de usuário, clique em **Novo** e clique em **Política de Usuário**. Em **Nova Política de Acesso Externo**, crie um nome exclusivo no campo **Nome** que indica o que a política de usuário cobre (por exemplo, **EnablePublicUsers** para uma política de usuário que permite comunicações para usuários públicos).</span><span class="sxs-lookup"><span data-stu-id="1340f-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="1340f-148">Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="1340f-148">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1340f-149">(Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="1340f-149">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="1340f-150">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="1340f-150">Do one of the following:</span></span>
    
      - <span data-ttu-id="1340f-151">Para habilitar o acesso de usuários públicos à política, marque a caixa de seleção **Habilitar comunicações com usuários públicos**.</span><span class="sxs-lookup"><span data-stu-id="1340f-151">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="1340f-152">Para desabilitar o acesso de usuários públicos à política, desmarque a caixa de seleção **Habilitar comunicações com usuários públicos**.</span><span class="sxs-lookup"><span data-stu-id="1340f-152">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="1340f-153">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1340f-153">Click **Commit**.</span></span>

<span data-ttu-id="1340f-154">Para habilitar o acesso do usuário público, você também deve habilitar o suporte para federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1340f-154">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="1340f-155">Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1340f-155">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="1340f-156">Se for uma política de usuário, também será necessário aplicar a política aos usuários públicos para os quais você deseja permitir a colaboração com usuários públicos.</span><span class="sxs-lookup"><span data-stu-id="1340f-156">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="1340f-157">Para obter detalhes, consulte [atribuir políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1340f-157">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1340f-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="1340f-158">See Also</span></span>


[<span data-ttu-id="1340f-159">Criar ou editar provedores federados SIP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1340f-159">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="1340f-160">Gerenciar provedores federados SIP para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1340f-160">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

