---
title: 'Lync Server 2013: gerenciar política de acesso externo para sua organização'
description: 'Lync Server 2013: gerenciar política de acesso externo para sua organização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f0bb0e6764f67403065187c62debef13c77fcc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558407"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="00d95-103">Gerenciar política de acesso externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-103">Manage external access policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00d95-104">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="00d95-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="00d95-105">Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso externo que terão suporte na sua organização.</span><span class="sxs-lookup"><span data-stu-id="00d95-105">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="00d95-p101">Por padrão, não há políticas configuradas para suportar o acesso de usuário externo, incluindo o acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o suporte de acesso de usuário externo para sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo suportado para cada política. Os escopos da política a seguir estão disponíveis para criação e configuração. Por padrão, a política global é criada, mas não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="00d95-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="00d95-110">**Política global**   A política global é criada quando você implanta seus Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="00d95-110">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="00d95-111">Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global.</span><span class="sxs-lookup"><span data-stu-id="00d95-111">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="00d95-112">Para suportar o acesso do usuário externo a nível global, você deve configurar a política global para suportar um ou mais tipos de opções de acesso do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="00d95-112">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="00d95-113">A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global.</span><span class="sxs-lookup"><span data-stu-id="00d95-113">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="00d95-114">Ao excluir a política global, ela não é removida.</span><span class="sxs-lookup"><span data-stu-id="00d95-114">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="00d95-115">Ao invés, é redefinida para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="00d95-115">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="00d95-116">**Política de site**   Você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos.</span><span class="sxs-lookup"><span data-stu-id="00d95-116">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="00d95-117">A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.</span><span class="sxs-lookup"><span data-stu-id="00d95-117">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="00d95-118">Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico.</span><span class="sxs-lookup"><span data-stu-id="00d95-118">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="00d95-119">Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.</span><span class="sxs-lookup"><span data-stu-id="00d95-119">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="00d95-120">**Política de usuário**   Você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="00d95-120">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="00d95-121">A configuração da política de usuário substitui a política global e a do local, mas apenas para usuários específicos aos quais a política de usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="00d95-121">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="00d95-122">Por exemplo, se você ativar o acesso de usuário remoto na política global e na de local, deve especificar uma política de usuário que a desative e depois atribuir essa política de usuário a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="00d95-122">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="00d95-123">Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que ela surta efeito.</span><span class="sxs-lookup"><span data-stu-id="00d95-123">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="00d95-124">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="00d95-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="00d95-125">A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência).</span><span class="sxs-lookup"><span data-stu-id="00d95-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="00d95-126">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="00d95-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="00d95-127">Essas opções incluem os seguintes tipos de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="00d95-127">These options include the following types of external access:</span></span>

  - <span data-ttu-id="00d95-128">**Habilitar comunicações com usuários federados**   Habilite esta opção se desejar oferecer suporte para o acesso de usuários a domínios parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="00d95-128">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="00d95-129">Essa configuração configura a capacidade de os usuários se comunicarem com outros domínios federados SIP, bem como provedores hospedados como o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00d95-129">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="00d95-130">Selecionar essa configuração permite que você selecione a opção para permitir a comunicação com domínios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="00d95-130">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="00d95-p107">Como opção, você pode selecionar **Permitir comunicações com parceiros XMPP federados** se você primeiro selecionar **Permitir comunicações com usuários federados**. A federação XMPP é uma federação com organizações que utilizam o XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="00d95-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00d95-133">Se você habilitar a Federação XMPP, também deverá optar por implantar a <STRONG>Federação XMPP</STRONG> na seção configuração de pools de borda do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="00d95-133">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="00d95-134">A configuração da Federação do XMPP implanta um proxy do XMPP no servidor de borda e um Gateway XMPP no servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="00d95-134">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="00d95-135">**Habilitar comunicações com usuários**     remotos Habilite essa opção se quiser que os usuários em sua organização que estejam fora do firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server pela Internet.</span><span class="sxs-lookup"><span data-stu-id="00d95-135">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="00d95-136">**Habilitar comunicações com usuários públicos**     Habilite essa opção se quiser que usuários internos possam se comunicar com contatos do provedor de mensagens instantâneas públicos, como os fornecidos pelo Windows Live, Yahoo \! e America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="00d95-136">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="00d95-137">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="00d95-137">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="00d95-138">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="00d95-138">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="00d95-139">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="00d95-139">Messenger until the service shut down date.</span></span> <span data-ttu-id="00d95-140">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="00d95-140">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="00d95-141">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="00d95-141">has been announced.</span></span> <span data-ttu-id="00d95-142">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00d95-142">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="00d95-143">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="00d95-143">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="00d95-144">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="00d95-144">Messenger.</span></span> <span data-ttu-id="00d95-145">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="00d95-145">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="00d95-146">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="00d95-146">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="00d95-147">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="00d95-147">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="00d95-148">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="00d95-148">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="00d95-149">Além de habilitar o suporte ao acesso de usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuário externo na organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="00d95-149">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="00d95-150">Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00d95-150">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="00d95-151">**Para exibir políticas de acesso externo usando os cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="00d95-151">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="00d95-152">Você pode visualizar as políticas de acesso externo usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="00d95-152">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="00d95-153">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00d95-153">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="00d95-154">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="00d95-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="00d95-155">Para exibir informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de Gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="00d95-155">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="00d95-156">Esse comando retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="00d95-156">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="00d95-157">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="00d95-157">In This Section</span></span>

  - [<span data-ttu-id="00d95-158">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-158">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="00d95-159">Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-159">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="00d95-160">Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-160">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="00d95-161">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-161">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="00d95-162">Atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-162">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="00d95-163">Redefinindo ou excluindo políticas de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d95-163">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

