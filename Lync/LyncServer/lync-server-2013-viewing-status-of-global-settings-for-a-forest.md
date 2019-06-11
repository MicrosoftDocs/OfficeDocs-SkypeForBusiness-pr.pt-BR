---
title: 'Lync Server 2013: exibindo o status de configurações globais para uma floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="a0592-102">Exibir o status das configurações globais de uma floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0592-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0592-103">_**Tópico da última modificação:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a0592-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="a0592-104">Os administradores devem analisar as configurações globais para uma implantação do Lync Server 2013 mensalmente.</span><span class="sxs-lookup"><span data-stu-id="a0592-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="a0592-105">O objetivo seria revisar as configurações implementadas em relação a um conjunto de configurações conhecidas, uma configuração de linha de base para ajudar a garantir que as configurações sejam válidas e determinar se a documentação da linha de base deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="a0592-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="a0592-106">As alterações na configuração global devem ser implementadas por meio de um processo de controle de alterações que deve incluir a documentação das novas configurações.</span><span class="sxs-lookup"><span data-stu-id="a0592-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="a0592-107">As configurações globais que devem ser analisadas estão descritas nas seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="a0592-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="a0592-108">Verificar as configurações gerais</span><span class="sxs-lookup"><span data-stu-id="a0592-108">Check general settings</span></span>

<span data-ttu-id="a0592-109">Verifique as configurações gerais, incluindo os domínios SIP (Session Initiation Protocol) com suporte para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0592-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="a0592-110">As informações do domínio SIP podem ser retornadas usando o Windows PowerShell e o cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="a0592-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="a0592-111">Para retornar essas informações, execute o `Get-CsSipDomain` comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0592-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="a0592-112">Get-CsSipDomain retornará informações semelhantes para todos os domínios SIP autorizados:</span><span class="sxs-lookup"><span data-stu-id="a0592-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="a0592-113">Nome da identidade-padrão</span><span class="sxs-lookup"><span data-stu-id="a0592-113">Identity Name IsDefault</span></span>

<span data-ttu-id="a0592-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="a0592-114"></span></span>

<span data-ttu-id="a0592-115">fabrikam.com fabrikam.com verdadeiro</span><span class="sxs-lookup"><span data-stu-id="a0592-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="a0592-116">na.fabrikam.com na.fabrikam.com falso</span><span class="sxs-lookup"><span data-stu-id="a0592-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="a0592-117">Se a Propriedade IsDefault estiver definida como true, o domínio correspondente será o seu domínio SIP padrão.</span><span class="sxs-lookup"><span data-stu-id="a0592-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="a0592-118">Você pode usar o cmdlet Set-CsSipDomain para alterar o domínio SIP padrão de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a0592-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="a0592-119">No entanto, você não pode apenas excluir o domínio SIP padrão porque isso o deixaria sem um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="a0592-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="a0592-120">Se você quisesse excluir o domínio fabrikam.com (conforme mostrado no exemplo anterior), primeiro precisaria configurar na.fabrikam.com para ser o domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="a0592-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="a0592-121">Verificar as configurações da reunião</span><span class="sxs-lookup"><span data-stu-id="a0592-121">Check meeting settings</span></span>

<span data-ttu-id="a0592-122">As configurações de reunião incluem definições de política de reunião e suporte para a participação de usuários anônimos em reuniões.</span><span class="sxs-lookup"><span data-stu-id="a0592-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="a0592-123">As definições de configuração de reunião podem ser recuperadas usando o Windows PowerShell e o cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a0592-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="a0592-124">Por exemplo, esse comando retorna informações sobre as definições de configuração de reunião global:</span><span class="sxs-lookup"><span data-stu-id="a0592-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="a0592-125">Get-CsMeetingConfiguration – as configurações de reunião "global" de identidade também podem ser configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="a0592-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="a0592-126">Por isso, talvez você queira usar o seguinte comando, que retorna informações sobre todas as definições de configuração de reunião:</span><span class="sxs-lookup"><span data-stu-id="a0592-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="a0592-127">O cmdlet **Get-CsMeetingConfiguration** retorna informações semelhantes às seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0592-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="a0592-128">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-128">Identity : Global</span></span>

<span data-ttu-id="a0592-129">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="a0592-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="a0592-130">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="a0592-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="a0592-131">DesignateAsPresenter: empresa</span><span class="sxs-lookup"><span data-stu-id="a0592-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="a0592-132">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="a0592-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="a0592-133">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="a0592-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="a0592-134">Novamente, o item final na lista, **AdmitAnonymousUsersByDefault**, habilita ou desabilita a capacidade dos usuários anônimos de participarem de reuniões.</span><span class="sxs-lookup"><span data-stu-id="a0592-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="a0592-135">Ao verificar as configurações de reunião, talvez seja útil comparar as configurações atuais com relação aos equivalentes padrão.</span><span class="sxs-lookup"><span data-stu-id="a0592-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="a0592-136">Você pode visualizar as configurações de reunião padrão executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a0592-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="a0592-137">O comando anterior cria uma instância de configuração de reunião global somente na memória, uma instância que usa o valor padrão para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="a0592-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="a0592-138">Nenhuma configuração de reunião real é criada quando você executa o comando.</span><span class="sxs-lookup"><span data-stu-id="a0592-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="a0592-139">No entanto, todos os valores de propriedades padrão serão exibidos na tela.</span><span class="sxs-lookup"><span data-stu-id="a0592-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="a0592-140">Verificar os servidores de borda e suas configurações</span><span class="sxs-lookup"><span data-stu-id="a0592-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="a0592-141">As informações do servidor de borda podem ser recuperadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0592-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="a0592-142">Esse comando retorna informações sobre todos os servidores de borda configurados para uso em sua organização:</span><span class="sxs-lookup"><span data-stu-id="a0592-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="a0592-143">As informações retornadas incluem todas as configurações de FQDN e de porta para cada servidor de borda:</span><span class="sxs-lookup"><span data-stu-id="a0592-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="a0592-144">Identidade: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a0592-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="a0592-145">Registrador: registrar: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a0592-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="a0592-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="a0592-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="a0592-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="a0592-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="a0592-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="a0592-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="a0592-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="a0592-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="a0592-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="a0592-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="a0592-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="a0592-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="a0592-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="a0592-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="a0592-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="a0592-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="a0592-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="a0592-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="a0592-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="a0592-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="a0592-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="a0592-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="a0592-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="a0592-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="a0592-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a0592-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="a0592-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a0592-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="a0592-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="a0592-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="a0592-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="a0592-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="a0592-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a0592-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="a0592-163">DependentServiceList: {registrador: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="a0592-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="a0592-164">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="a0592-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="a0592-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="a0592-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="a0592-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="a0592-166">fabrikam.com}</span></span>

<span data-ttu-id="a0592-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="a0592-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="a0592-168">SiteId: site:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="a0592-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="a0592-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a0592-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="a0592-170">Versão: 5</span><span class="sxs-lookup"><span data-stu-id="a0592-170">Version : 5</span></span>

<span data-ttu-id="a0592-171">Função: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="a0592-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="a0592-172">Verificar as configurações de Federação</span><span class="sxs-lookup"><span data-stu-id="a0592-172">Check federation settings</span></span>

<span data-ttu-id="a0592-173">Verifique as configurações de Federação, como se ela está configurada e, se a resposta for "Sim", o FQDN e a porta.</span><span class="sxs-lookup"><span data-stu-id="a0592-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="a0592-174">A Federação está habilitada e desabilitada usando a coleção global de definições de configuração de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="a0592-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="a0592-175">Entre outras coisas, isso significa que a Federação está configurada com base em tudo ou nada: a Federação está habilitada para toda a organização ou a Federação está desabilitada para toda a organização</span><span class="sxs-lookup"><span data-stu-id="a0592-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="a0592-176">Suas configurações de borda de acesso podem ser retornadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0592-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="a0592-177">Para fazer isso, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a0592-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="a0592-178">Por sua vez, esse comando retornará dados semelhantes a isto:</span><span class="sxs-lookup"><span data-stu-id="a0592-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="a0592-179">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-179">Identity : Global</span></span>

<span data-ttu-id="a0592-180">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="a0592-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="a0592-181">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="a0592-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="a0592-182">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="a0592-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="a0592-183">Myclearinghouse: falso</span><span class="sxs-lookup"><span data-stu-id="a0592-183">BeClearingHouse : False</span></span>

<span data-ttu-id="a0592-184">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="a0592-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="a0592-185">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="a0592-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="a0592-186">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="a0592-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="a0592-187">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="a0592-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="a0592-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="a0592-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="a0592-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="a0592-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="a0592-190">Se a propriedade **AllowFederatedUsers** estiver definida como true, isso significa que a Federação está habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a0592-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="a0592-191">(Definir **AllowFederatedUsers** como true também significa que, em um cenário de domínio dividido, os usuários locais poderão se comunicar perfeitamente com seus usuários na nuvem.)</span><span class="sxs-lookup"><span data-stu-id="a0592-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="a0592-192">Para recuperar as configurações de FQDN e de porta do servidor de borda, consulte a tarefa anterior (servidores de borda e suas configurações).</span><span class="sxs-lookup"><span data-stu-id="a0592-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="a0592-193">Habilitar a Federação no escopo global apenas significa que os usuários podem se comunicar com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="a0592-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="a0592-194">Para determinar se os usuários individuais podem realmente se comunicar com usuários federados exigem que você examine a política de acesso de usuários externos atribuída a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="a0592-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="a0592-195">As informações de acesso do usuário externo podem ser retornadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0592-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="a0592-196">Por exemplo, esse comando retorna informações para a política de acesso externo ao usuário externo:</span><span class="sxs-lookup"><span data-stu-id="a0592-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="a0592-197">E esse comando retorna informações para todas as políticas de acesso externo do usuário:</span><span class="sxs-lookup"><span data-stu-id="a0592-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="a0592-198">As informações retornadas serão parecidas com isto:</span><span class="sxs-lookup"><span data-stu-id="a0592-198">The returned information will resemble this:</span></span>

<span data-ttu-id="a0592-199">Identidade: falso</span><span class="sxs-lookup"><span data-stu-id="a0592-199">Identity : False</span></span>

<span data-ttu-id="a0592-200">Descritivo</span><span class="sxs-lookup"><span data-stu-id="a0592-200">Description :</span></span>

<span data-ttu-id="a0592-201">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="a0592-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="a0592-202">EnablePublicCloudAccess: false</span><span class="sxs-lookup"><span data-stu-id="a0592-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="a0592-203">EnablePublicCloudAccessAudioVideoAccess: false</span><span class="sxs-lookup"><span data-stu-id="a0592-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="a0592-204">EnableOutsideAccess: false</span><span class="sxs-lookup"><span data-stu-id="a0592-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="a0592-205">Se **EnableFederationAccess** for definido como true, os usuários gerenciados pela política fornecida poderão se comunicar com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="a0592-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="a0592-206">Verificar as configurações de arquivamento</span><span class="sxs-lookup"><span data-stu-id="a0592-206">Check archiving settings</span></span>

<span data-ttu-id="a0592-207">Verifique as configurações de arquivamento para comunicações internas e federadas. Antes de verificar as configurações de arquivamento interno e externo, verifique se o arquivamento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a0592-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="a0592-208">As configurações de arquivamento podem ser verificadas usando o Windows PowerShell e o cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="a0592-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="a0592-209">Observe que as configurações de arquivamento também podem ser configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="a0592-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="a0592-210">Para retornar informações sobre todas as configurações de arquivamento, use este comando:</span><span class="sxs-lookup"><span data-stu-id="a0592-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="a0592-211">O cmdlet Get-CsArchivingConfiguration retorna dados semelhantes a este:</span><span class="sxs-lookup"><span data-stu-id="a0592-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="a0592-212">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-212">Identity : Global</span></span>

<span data-ttu-id="a0592-213">EnableArchiving: false</span><span class="sxs-lookup"><span data-stu-id="a0592-213">EnableArchiving : False</span></span>

<span data-ttu-id="a0592-214">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="a0592-214">EnablePurging : False</span></span>

<span data-ttu-id="a0592-215">PurgeExportedArchivesOnly: false</span><span class="sxs-lookup"><span data-stu-id="a0592-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="a0592-216">BlockOnArchiveFailure: false</span><span class="sxs-lookup"><span data-stu-id="a0592-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="a0592-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="a0592-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="a0592-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="a0592-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="a0592-219">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="a0592-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="a0592-220">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="a0592-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="a0592-221">Se a propriedade EnableArchiving estiver definida como false, isso significa que nenhuma sessão de comunicação será arquivada.</span><span class="sxs-lookup"><span data-stu-id="a0592-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="a0592-222">Se você quiser arquivar sessões de mensagens instantâneas somente, use um comando como o seguinte para habilitar o arquivamento de sessões de mensagens instantâneas:</span><span class="sxs-lookup"><span data-stu-id="a0592-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="a0592-223">Para arquivar sessões de conferência e sessões de mensagens instantâneas, use este comando:</span><span class="sxs-lookup"><span data-stu-id="a0592-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="a0592-224">Se quiser comparar as configurações atuais de arquivamento com as configurações padrão, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a0592-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="a0592-225">Esse comando cria uma instância somente na memória das configurações de configuração global de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="a0592-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="a0592-226">Este não é um conjunto real de configurações que é usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0592-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="a0592-227">No entanto, ele exibe os valores padrão para todas as propriedades de configuração de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="a0592-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="a0592-228">Você também pode usar esse comando para retornar o FQDN dos seus servidores de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="a0592-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="a0592-229">Depois de verificar se o arquivamento está habilitado, você pode ver as políticas de arquivamento para determinar se as sessões de comunicação internas e externas estão sendo arquivadas.</span><span class="sxs-lookup"><span data-stu-id="a0592-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="a0592-230">As informações da política de arquivamento podem ser recuperadas usando o cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="a0592-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="a0592-231">Por exemplo, esse comando retorna informações sobre a política de arquivamento global:</span><span class="sxs-lookup"><span data-stu-id="a0592-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="a0592-232">Como as políticas de arquivamento também podem ser configuradas no site e no escopo por usuário, você também pode querer usar esse comando, que retorna informações sobre todas as políticas de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="a0592-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="a0592-233">As informações recebidas do Get-CsArchivingPolicy serão parecidas com isso:</span><span class="sxs-lookup"><span data-stu-id="a0592-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="a0592-234">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-234">Identity : Global</span></span>

<span data-ttu-id="a0592-235">Descritivo</span><span class="sxs-lookup"><span data-stu-id="a0592-235">Description :</span></span>

<span data-ttu-id="a0592-236">ArchiveInternal: false</span><span class="sxs-lookup"><span data-stu-id="a0592-236">ArchiveInternal : False</span></span>

<span data-ttu-id="a0592-237">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="a0592-237">ArchiveExternal : False</span></span>

<span data-ttu-id="a0592-238">Observe que, por padrão, o arquivamento interno e externo está desabilitado em uma política de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="a0592-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="a0592-239">Verificar as configurações do CDR</span><span class="sxs-lookup"><span data-stu-id="a0592-239">Check CDR settings</span></span>

<span data-ttu-id="a0592-240">Verifique as configurações de CDR (registro de detalhes de chamadas) para gravação ponto a ponto, conferência e detalhes de chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="a0592-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="a0592-241">Informações detalhadas sobre as configurações do CDR podem ser retornadas usando o cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a0592-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="a0592-242">Por exemplo, esse comando retorna informações sobre a coleção global de definições de configuração de CDR:</span><span class="sxs-lookup"><span data-stu-id="a0592-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="a0592-243">Como a CDR também pode ser configurada no escopo do site, talvez você também queira executar esse comando, que retorna informações sobre todas as definições de configuração de CDR:</span><span class="sxs-lookup"><span data-stu-id="a0592-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="a0592-244">O cmdlet Get-CsCdrConfiguration retorna informações parecidas com isso para cada conjunto de definições de configuração de CDR:</span><span class="sxs-lookup"><span data-stu-id="a0592-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="a0592-245">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-245">Identity : Global</span></span>

<span data-ttu-id="a0592-246">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="a0592-246">EnableCDR : True</span></span>

<span data-ttu-id="a0592-247">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="a0592-247">EnablePurging : True</span></span>

<span data-ttu-id="a0592-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="a0592-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="a0592-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="a0592-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="a0592-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="a0592-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="a0592-251">Informações semelhantes podem ser retornadas para o monitoramento de QoE usando-se o cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a0592-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="a0592-252">Por exemplo, esse comando retorna informações sobre a coleção global de definições de configuração de QoE:</span><span class="sxs-lookup"><span data-stu-id="a0592-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="a0592-253">Essas informações serão parecidas com isso:</span><span class="sxs-lookup"><span data-stu-id="a0592-253">That information will resemble this:</span></span>

<span data-ttu-id="a0592-254">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-254">Identity : Global</span></span>

<span data-ttu-id="a0592-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="a0592-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="a0592-256">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="a0592-256">EnablePurging : True</span></span>

<span data-ttu-id="a0592-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="a0592-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="a0592-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="a0592-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="a0592-259">EnableExternalConsumer: false</span><span class="sxs-lookup"><span data-stu-id="a0592-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="a0592-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="a0592-260">ExternalConsumerName :</span></span>

<span data-ttu-id="a0592-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="a0592-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="a0592-262">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="a0592-262">EnableQoE : True</span></span>

<span data-ttu-id="a0592-263">Se você quiser comparar as configurações atuais de CDR com as configurações de CDR padrão, os valores padrão podem ser revisados executando este comando:</span><span class="sxs-lookup"><span data-stu-id="a0592-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="a0592-264">Da mesma forma, os valores padrão para monitoramento de QoE podem ser recuperados usando este comando:</span><span class="sxs-lookup"><span data-stu-id="a0592-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="a0592-265">Você também pode retornar o FQDN dos seus servidores de monitoração executando este comando:</span><span class="sxs-lookup"><span data-stu-id="a0592-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="a0592-266">Verificar as configurações de voz</span><span class="sxs-lookup"><span data-stu-id="a0592-266">Check voice settings</span></span>

<span data-ttu-id="a0592-267">As configurações de voz geralmente importantes para os administradores estão contidas em políticas de voz e rotas de voz: as políticas de voz contêm as configurações que determinam os recursos expostos a usuários individuais (como a capacidade de encaminhar ou transferir chamadas), enquanto as rotas de voz determinam como as chamadas (e se) são roteadas em toda a PSTN.</span><span class="sxs-lookup"><span data-stu-id="a0592-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="a0592-268">As informações da política de voz podem ser recuperadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0592-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="a0592-269">Por exemplo, esse comando retorna informações sobre a política de voz global:</span><span class="sxs-lookup"><span data-stu-id="a0592-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="a0592-270">E esse comando retorna informações sobre todas as políticas de voz configuradas para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="a0592-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="a0592-271">As informações retornadas pelo cmdlet Get-CsVoicePolicy são semelhantes às seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0592-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="a0592-272">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-272">Identity : Global</span></span>

<span data-ttu-id="a0592-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="a0592-273">PstnUsages : {}</span></span>

<span data-ttu-id="a0592-274">Descritivo</span><span class="sxs-lookup"><span data-stu-id="a0592-274">Description :</span></span>

<span data-ttu-id="a0592-275">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="a0592-275">AllowSimulRing : True</span></span>

<span data-ttu-id="a0592-276">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="a0592-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="a0592-277">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="a0592-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="a0592-278">Nome: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="a0592-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="a0592-279">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="a0592-279">EnableDelegation : True</span></span>

<span data-ttu-id="a0592-280">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="a0592-280">EnableTeamCall : True</span></span>

<span data-ttu-id="a0592-281">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="a0592-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="a0592-282">EnableCallPark: false</span><span class="sxs-lookup"><span data-stu-id="a0592-282">EnableCallPark : False</span></span>

<span data-ttu-id="a0592-283">EnableMaliciousCallTracing: false</span><span class="sxs-lookup"><span data-stu-id="a0592-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="a0592-284">EnableBWPolicyOverride: false</span><span class="sxs-lookup"><span data-stu-id="a0592-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="a0592-285">PreventPSTNTollBypass: false</span><span class="sxs-lookup"><span data-stu-id="a0592-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="a0592-286">Você também pode criar consultas que retornaram um subconjunto de suas políticas de voz.</span><span class="sxs-lookup"><span data-stu-id="a0592-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="a0592-287">Por exemplo, esse comando retorna todas as políticas de voz que permitem o encaminhamento de chamadas:</span><span class="sxs-lookup"><span data-stu-id="a0592-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="a0592-288">E esse comando retorna todas as políticas de voz que não permitem o encaminhamento de chamadas:</span><span class="sxs-lookup"><span data-stu-id="a0592-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="a0592-289">No Windows PowerShell, use o cmdlet Get-CsVoiceRouting para retornar informações sobre suas rotas de voz:</span><span class="sxs-lookup"><span data-stu-id="a0592-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="a0592-290">Esse comando retorna informações como esta para todas as rotas de voz:</span><span class="sxs-lookup"><span data-stu-id="a0592-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="a0592-291">Identidade: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="a0592-291">Identity : LocalRoute</span></span>

<span data-ttu-id="a0592-292">Prioridade: 0</span><span class="sxs-lookup"><span data-stu-id="a0592-292">Priority : 0</span></span>

<span data-ttu-id="a0592-293">Descritivo</span><span class="sxs-lookup"><span data-stu-id="a0592-293">Description :</span></span>

<span data-ttu-id="a0592-294">NumberPattern: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="a0592-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="a0592-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="a0592-295">PstnUsages : {}</span></span>

<span data-ttu-id="a0592-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="a0592-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="a0592-297">Nome: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="a0592-297">Name : LocalRoute</span></span>

<span data-ttu-id="a0592-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="a0592-298">SuppressCallerId :</span></span>

<span data-ttu-id="a0592-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="a0592-299">AlternateCallerId :</span></span>

<span data-ttu-id="a0592-300">O Lync Server permite criar rotas de voz que não têm um uso PSTN e não especificam um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="a0592-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="a0592-301">No entanto, você não pode realmente rotear chamadas por uma rota de voz que não tenha esses dois valores de propriedade configurados.</span><span class="sxs-lookup"><span data-stu-id="a0592-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="a0592-302">Por isso, talvez seja útil executar esse comando periodicamente, que retorna a identidade de qualquer rota de voz que não tenha um uso PSTN:</span><span class="sxs-lookup"><span data-stu-id="a0592-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="a0592-303">Da mesma forma, esse comando retorna a identidade de qualquer rota de voz que não tenha sido configurada para ter um gateway PSTN:</span><span class="sxs-lookup"><span data-stu-id="a0592-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="a0592-304">Verificar as configurações do atendedor de conferências</span><span class="sxs-lookup"><span data-stu-id="a0592-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="a0592-305">Verifique as configurações do atendedor de conferências para conferências discadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="a0592-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="a0592-306">As configurações do atendedor de conferência só podem ser recuperadas usando o cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a0592-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="a0592-307">Essas configurações não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0592-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="a0592-308">Para exibir as configurações do atendedor de conferência, use um comando do Windows PowerShell semelhante ao seguinte, que retorna a coleção global das configurações do atendedor de conferência:</span><span class="sxs-lookup"><span data-stu-id="a0592-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="a0592-309">Observe que as configurações do atendedor de conferências também podem ser configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="a0592-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="a0592-310">Para retornar informações sobre todas as configurações do atendedor de conferência, use este comando em vez disso:</span><span class="sxs-lookup"><span data-stu-id="a0592-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="a0592-311">O cmdlet Get-CsDialInConferencingConfiguration retorna dados semelhantes a este:</span><span class="sxs-lookup"><span data-stu-id="a0592-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="a0592-312">Identidade: global</span><span class="sxs-lookup"><span data-stu-id="a0592-312">Identity : Global</span></span>

<span data-ttu-id="a0592-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="a0592-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="a0592-314">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="a0592-314">EnableNameRecording : True</span></span>

<span data-ttu-id="a0592-315">EntryExitAnnouncementsEnabledByDefault: false</span><span class="sxs-lookup"><span data-stu-id="a0592-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="a0592-316">Se EntryExitAnnouncementsEnabledByDefault estiver definido como false, isso significa que os comunicados de conferência estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="a0592-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="a0592-317">Para habilitar os comunicados de entrada e saída, execute um comando do Windows PowerShell semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="a0592-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0592-318">Confira também</span><span class="sxs-lookup"><span data-stu-id="a0592-318">See Also</span></span>


[<span data-ttu-id="a0592-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="a0592-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="a0592-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0592-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="a0592-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="a0592-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="a0592-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0592-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="a0592-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a0592-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="a0592-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0592-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="a0592-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0592-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="a0592-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0592-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="a0592-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="a0592-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="a0592-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="a0592-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="a0592-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0592-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

