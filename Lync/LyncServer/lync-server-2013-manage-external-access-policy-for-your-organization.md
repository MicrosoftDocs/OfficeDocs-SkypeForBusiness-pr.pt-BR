---
title: 'Lync Server 2013: Gerenciar política de acesso externo para sua organização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="cbd5a-102">Gerenciar política de acesso externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbd5a-103">_**Tópico da última modificação:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="cbd5a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="cbd5a-104">Após implantar um ou mais servidores de borda, você deve habilitar os tipos de acesso externo que terão suporte para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="cbd5a-105">Por padrão, não há políticas configuradas para dar suporte a acesso externo a usuários, incluindo acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o acesso de usuário externo à sua organização.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="cbd5a-106">Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo com suporte para cada política.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="cbd5a-107">Os seguintes escopos de política estão disponíveis para criação e configuração.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="cbd5a-108">Por padrão, a política global é criada, mas não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="cbd5a-109">**Política global a**   política global é criada quando você implanta seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="cbd5a-110">Por padrão, nenhuma opção de acesso de usuário externo está habilitada na política global.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="cbd5a-111">Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de opções de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="cbd5a-112">A política global aplica-se a todos os usuários em sua organização, mas políticas de site e políticas de usuário substituem a política global.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="cbd5a-113">Se você excluir a política global, não a removerá.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="cbd5a-114">Em vez disso, redefina-o para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="cbd5a-115">**Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="cbd5a-116">A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="cbd5a-117">Por exemplo, se você habilitar o acesso de usuário remoto na política global, poderá especificar uma política de site que desabilite o acesso de usuário remoto para um site específico.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="cbd5a-118">Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política do site.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="cbd5a-119">**Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte para acesso de usuário remoto a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="cbd5a-120">A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política de usuário está atribuída.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="cbd5a-121">Por exemplo, se você habilitar o acesso de usuário remoto na política global e na política do site, poderá especificar uma política de usuário que desabilite o acesso de usuário remoto e atribua essa política de usuário a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="cbd5a-122">Se você criar uma política de usuário, deverá aplicá-la a um ou mais usuários antes de entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cbd5a-123">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="cbd5a-124">A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="cbd5a-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="cbd5a-125">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="cbd5a-126">Essas opções incluem os seguintes tipos de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="cbd5a-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="cbd5a-127">**Habilitar comunicações com usuários**   federados habilitá-lo se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="cbd5a-128">Essa configuração define a capacidade dos usuários de se comunicarem com outros domínios federados do SIP, bem como provedores hospedados como o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="cbd5a-129">Selecionar essa configuração permite que você selecione a opção para permitir a comunicação com domínios federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="cbd5a-130">Como opção, você pode selecionar **habilitar comunicações com parceiros federados do XMPP** se selecionar **habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="cbd5a-131">A Federação do XMPP é uma federação com organizações que usam Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="cbd5a-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbd5a-132">Se você habilitar a Federação do XMPP, também deverá selecionar para implantar a <STRONG>Federação do XMPP</STRONG> na seção configuração de pools de borda do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="cbd5a-133">A configuração para a Federação do XMPP implanta um proxy XMPP no servidor de borda e um Gateway XMPP no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="cbd5a-134">**Habilitar comunicações com usuários**   remotos habilite essa opção se você quiser que os usuários em sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server pela Internet.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="cbd5a-135">**Habilitar comunicações com usuários**   públicos habilite essa opção se você quiser que os usuários internos possam se comunicar com contatos públicos do provedor de mensagens de chat, como aqueles fornecidos pelo\!Windows Live, Yahoo e America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="cbd5a-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="cbd5a-136">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="cbd5a-137">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cbd5a-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cbd5a-138">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="cbd5a-139">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cbd5a-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cbd5a-140">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-140">has been announced.</span></span> <span data-ttu-id="cbd5a-141">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cbd5a-142">O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cbd5a-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cbd5a-143">Spam.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-143">Messenger.</span></span> <span data-ttu-id="cbd5a-144">A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cbd5a-145">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cbd5a-146">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cbd5a-147">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="cbd5a-148">Além de habilitar o suporte ao acesso do usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuários externos em sua organização antes que qualquer tipo de acesso de usuário externo esteja disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="cbd5a-149">Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="cbd5a-150">**Para exibir as políticas de acesso externo usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cbd5a-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="cbd5a-151">Você pode exibir as políticas de acesso externo usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="cbd5a-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="cbd5a-152">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cbd5a-153">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="cbd5a-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="cbd5a-154">Para ver as informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="cbd5a-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="cbd5a-155">Este comando retorna informações semelhantes para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cbd5a-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="cbd5a-156">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="cbd5a-156">In This Section</span></span>

  - [<span data-ttu-id="cbd5a-157">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="cbd5a-158">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="cbd5a-159">Configurar políticas para controle de acesso de usuário remoto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="cbd5a-160">Configurar políticas para controlar o acesso de usuário público no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="cbd5a-161">Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="cbd5a-162">Redefinindo ou excluindo políticas de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbd5a-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

