---
title: 'Lync Server 2013: exibindo o status das configurações globais de uma floresta'
description: 'Lync Server 2013: exibindo o status das configurações globais de uma floresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567587"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="0d63d-103">Exibir o status das configurações globais de uma floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d63d-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d63d-104">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="0d63d-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="0d63d-105">Os administradores devem examinar as configurações globais de uma implantação do Lync Server 2013 mensal.</span><span class="sxs-lookup"><span data-stu-id="0d63d-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="0d63d-106">O objetivo seria examinar as configurações implementadas em um conjunto de configurações conhecidas, uma configuração de linha de base para ajudar a garantir que as configurações sejam válidas e para determinar se a documentação da linha de base deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="0d63d-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="0d63d-107">As alterações na configuração global devem ser implementadas por meio de um processo de controle de alterações que deve incluir a documentação das novas configurações.</span><span class="sxs-lookup"><span data-stu-id="0d63d-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="0d63d-108">As configurações globais que devem ser analisadas são descritas nas seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="0d63d-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="0d63d-109">Verificar configurações gerais</span><span class="sxs-lookup"><span data-stu-id="0d63d-109">Check general settings</span></span>

<span data-ttu-id="0d63d-110">Verifique as configurações gerais, incluindo os domínios SIP (Session Initiation Protocol) suportados para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d63d-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="0d63d-111">As informações do domínio SIP podem ser retornadas usando o Windows PowerShell e o cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="0d63d-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="0d63d-112">Para retornar essas informações, execute o `Get-CsSipDomain` comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d63d-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="0d63d-113">Get-CsSipDomain retornará informações parecidas com isso para todos os domínios SIP autorizados:</span><span class="sxs-lookup"><span data-stu-id="0d63d-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="0d63d-114">Nome da identidade IsDefault</span><span class="sxs-lookup"><span data-stu-id="0d63d-114">Identity Name IsDefault</span></span>

<span data-ttu-id="0d63d-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="0d63d-115">\-------- ---- ---------</span></span>

<span data-ttu-id="0d63d-116">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="0d63d-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="0d63d-117">na.fabrikam.com na.fabrikam.com falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="0d63d-118">Se a Propriedade IsDefault estiver definida como true, o domínio correspondente será seu domínio SIP padrão.</span><span class="sxs-lookup"><span data-stu-id="0d63d-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="0d63d-119">Você pode usar o cmdlet Set-CsSipDomain para alterar o domínio SIP padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="0d63d-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="0d63d-120">No entanto, você não pode simplesmente excluir o domínio SIP padrão, pois isso deixaria sem um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="0d63d-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="0d63d-121">Se você quisesse excluir o domínio fabrikam.com (conforme mostrado no exemplo anterior), você primeiro precisaria configurar o na.fabrikam.com para ser seu domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="0d63d-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="0d63d-122">Verificar configurações de reunião</span><span class="sxs-lookup"><span data-stu-id="0d63d-122">Check meeting settings</span></span>

<span data-ttu-id="0d63d-123">As configurações de reunião incluem definições de política de reunião e suporte para participação de usuários anônimos em reuniões.</span><span class="sxs-lookup"><span data-stu-id="0d63d-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="0d63d-124">As definições de configuração de reunião podem ser recuperadas usando o Windows PowerShell e o cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0d63d-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="0d63d-125">Por exemplo, este comando retorna informações sobre as definições de configuração de reunião global:</span><span class="sxs-lookup"><span data-stu-id="0d63d-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="0d63d-126">Get-CsMeetingConfiguration – Identity "global" as configurações de reunião também podem ser configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="0d63d-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="0d63d-127">Por isso, talvez você queira usar o seguinte comando, que retorna informações sobre todas as definições de configuração de reunião:</span><span class="sxs-lookup"><span data-stu-id="0d63d-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="0d63d-128">O cmdlet **Get-CsMeetingConfiguration** retorna informações semelhantes às seguintes:</span><span class="sxs-lookup"><span data-stu-id="0d63d-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="0d63d-129">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-129">Identity : Global</span></span>

<span data-ttu-id="0d63d-130">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="0d63d-131">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="0d63d-132">DesignateAsPresenter: empresa</span><span class="sxs-lookup"><span data-stu-id="0d63d-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="0d63d-133">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="0d63d-134">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="0d63d-135">Novamente, o item final na lista, **AdmitAnonymousUsersByDefault**, habilita ou desabilita a capacidade de usuários anônimos participarem de reuniões.</span><span class="sxs-lookup"><span data-stu-id="0d63d-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="0d63d-136">Ao verificar as definições de configuração da reunião, pode ser útil comparar as configurações atuais com os equivalentes padrão.</span><span class="sxs-lookup"><span data-stu-id="0d63d-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="0d63d-137">Você pode exibir as definições de configuração de reunião padrão executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0d63d-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0d63d-138">O comando anterior cria uma instância somente na memória das definições de configuração de reunião global, uma instância que usa o valor padrão para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="0d63d-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="0d63d-139">Nenhuma configuração real de reunião é criada quando você executa o comando.</span><span class="sxs-lookup"><span data-stu-id="0d63d-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="0d63d-140">No entanto, todos os valores de propriedade padrão serão exibidos na tela.</span><span class="sxs-lookup"><span data-stu-id="0d63d-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="0d63d-141">Verificar servidores de borda e suas configurações</span><span class="sxs-lookup"><span data-stu-id="0d63d-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="0d63d-142">As informações do servidor de borda podem ser recuperadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d63d-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="0d63d-143">Este comando retorna informações sobre todos os servidores de borda configurados para uso na sua organização:</span><span class="sxs-lookup"><span data-stu-id="0d63d-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="0d63d-144">As informações retornadas incluem todas as configurações de FQDN e de porta para cada servidor de borda:</span><span class="sxs-lookup"><span data-stu-id="0d63d-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="0d63d-145">Identidade: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0d63d-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="0d63d-146">Registrador: registrador: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0d63d-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="0d63d-147">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="0d63d-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="0d63d-148">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="0d63d-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="0d63d-149">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="0d63d-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="0d63d-150">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="0d63d-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="0d63d-151">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="0d63d-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="0d63d-152">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="0d63d-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="0d63d-153">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="0d63d-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="0d63d-154">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="0d63d-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="0d63d-155">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="0d63d-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="0d63d-156">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="0d63d-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="0d63d-157">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="0d63d-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="0d63d-158">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="0d63d-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="0d63d-159">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0d63d-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0d63d-160">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0d63d-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0d63d-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="0d63d-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="0d63d-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="0d63d-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="0d63d-163">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0d63d-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0d63d-164">DependentServiceList: {registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="0d63d-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="0d63d-165">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="0d63d-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="0d63d-166">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="0d63d-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="0d63d-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="0d63d-167">fabrikam.com}</span></span>

<span data-ttu-id="0d63d-168">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="0d63d-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="0d63d-169">SiteId: site:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="0d63d-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="0d63d-170">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0d63d-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0d63d-171">Versão: 5</span><span class="sxs-lookup"><span data-stu-id="0d63d-171">Version : 5</span></span>

<span data-ttu-id="0d63d-172">Função: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="0d63d-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="0d63d-173">Verificar configurações de Federação</span><span class="sxs-lookup"><span data-stu-id="0d63d-173">Check federation settings</span></span>

<span data-ttu-id="0d63d-174">Verifique as configurações de Federação, por exemplo, se ela está configurada e, se a resposta for "Sim", o FQDN e a porta.</span><span class="sxs-lookup"><span data-stu-id="0d63d-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="0d63d-175">A Federação é habilitada e desabilitada usando o conjunto global de definições de configuração de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="0d63d-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="0d63d-176">Entre outras coisas, isso significa que a Federação é configurada em uma base de tudo ou nada: a Federação está habilitada para toda a organização ou a Federação está desabilitada para toda a organização</span><span class="sxs-lookup"><span data-stu-id="0d63d-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="0d63d-177">Suas definições de configuração de borda de acesso podem ser retornadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d63d-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="0d63d-178">Para fazer isso, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0d63d-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="0d63d-179">Por sua vez, esse comando retornará dados similares a estes:</span><span class="sxs-lookup"><span data-stu-id="0d63d-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="0d63d-180">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-180">Identity : Global</span></span>

<span data-ttu-id="0d63d-181">AllowAnonymousUsers: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="0d63d-182">AllowFederatedUsers: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="0d63d-183">AllowOutsideUsers: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="0d63d-184">Beclearinghouse: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-184">BeClearingHouse : False</span></span>

<span data-ttu-id="0d63d-185">EnablePartnerDiscovery: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="0d63d-186">EnableArchivingDisclaimer: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="0d63d-187">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="0d63d-188">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="0d63d-189">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="0d63d-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="0d63d-190">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="0d63d-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="0d63d-191">Se a propriedade **AllowFederatedUsers** estiver definida como true, isso significa que a Federação está habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="0d63d-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="0d63d-192">(A configuração de **AllowFederatedUsers** como true também significa que, em um cenário de domínio dividido, seus usuários locais poderão se comunicar sem problemas com seus usuários na nuvem.)</span><span class="sxs-lookup"><span data-stu-id="0d63d-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="0d63d-193">Para recuperar as configurações de FQDN e de porta do servidor de borda, confira a tarefa anterior (servidores de borda e suas configurações).</span><span class="sxs-lookup"><span data-stu-id="0d63d-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="0d63d-194">Habilitar a Federação no escopo global significa que os usuários podem se comunicar potencialmente com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="0d63d-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="0d63d-195">Para determinar se os usuários individuais podem realmente se comunicar com os usuários federados exigem que você examine a política de acesso de usuário externo atribuída a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="0d63d-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="0d63d-196">As informações de acesso de usuário externo podem ser retornadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d63d-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="0d63d-197">Por exemplo, este comando retorna informações sobre a política de acesso de usuário externo global:</span><span class="sxs-lookup"><span data-stu-id="0d63d-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="0d63d-198">E este comando retorna informações de todas as políticas de acesso de usuário externo:</span><span class="sxs-lookup"><span data-stu-id="0d63d-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="0d63d-199">As informações retornadas serão parecidas com:</span><span class="sxs-lookup"><span data-stu-id="0d63d-199">The returned information will resemble this:</span></span>

<span data-ttu-id="0d63d-200">Identity: false</span><span class="sxs-lookup"><span data-stu-id="0d63d-200">Identity : False</span></span>

<span data-ttu-id="0d63d-201">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d63d-201">Description :</span></span>

<span data-ttu-id="0d63d-202">EnableFederationAccess: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="0d63d-203">EnablePublicCloudAccess: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="0d63d-204">EnablePublicCloudAccessAudioVideoAccess: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="0d63d-205">EnableOutsideAccess: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="0d63d-206">Se **EnableFederationAccess** for definido como true, os usuários gerenciados pela política determinada poderão se comunicar com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="0d63d-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="0d63d-207">Verificar configurações de arquivamento</span><span class="sxs-lookup"><span data-stu-id="0d63d-207">Check archiving settings</span></span>

<span data-ttu-id="0d63d-208">Verifique as configurações de arquivamento para comunicações internas e federadas. Antes de verificar as configurações de arquivamento interno e externo, você deve verificar se o arquivamento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0d63d-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="0d63d-209">As definições de configuração de arquivamento podem ser verificadas usando o Windows PowerShell e o cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="0d63d-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="0d63d-210">Observe que as configurações de arquivamento também podem ser configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="0d63d-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="0d63d-211">Para retornar informações sobre todas as configurações de arquivamento, use este comando:</span><span class="sxs-lookup"><span data-stu-id="0d63d-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="0d63d-212">O cmdlet Get-CsArchivingConfiguration retorna dados similares a estes:</span><span class="sxs-lookup"><span data-stu-id="0d63d-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="0d63d-213">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-213">Identity : Global</span></span>

<span data-ttu-id="0d63d-214">EnableArchiving: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-214">EnableArchiving : False</span></span>

<span data-ttu-id="0d63d-215">EnablePurging: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-215">EnablePurging : False</span></span>

<span data-ttu-id="0d63d-216">PurgeExportedArchivesOnly: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="0d63d-217">BlockOnArchiveFailure: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="0d63d-218">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="0d63d-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="0d63d-219">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="0d63d-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="0d63d-220">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="0d63d-221">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="0d63d-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="0d63d-222">Se a propriedade EnableArchiving estiver definida como false, isso significa que nenhuma sessão de comunicação será arquivada.</span><span class="sxs-lookup"><span data-stu-id="0d63d-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="0d63d-223">Se você deseja arquivar somente sessões de mensagens instantâneas, use um comando como o seguinte para habilitar o arquivamento de sessões de IM:</span><span class="sxs-lookup"><span data-stu-id="0d63d-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="0d63d-224">Para arquivar sessões de conferência e sessões de mensagens instantâneas, use este comando:</span><span class="sxs-lookup"><span data-stu-id="0d63d-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="0d63d-225">Se você quiser comparar suas configurações de arquivamento atuais com as configurações padrão, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0d63d-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0d63d-226">Esse comando cria uma instância somente na memória das definições de configuração de arquivamento global.</span><span class="sxs-lookup"><span data-stu-id="0d63d-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="0d63d-227">Este não é um conjunto real de configurações que é usado pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d63d-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="0d63d-228">No entanto, ele exibe os valores padrão para todas as propriedades de configuração de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0d63d-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="0d63d-229">Você também pode usar este comando para retornar o FQDN dos seus servidores de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="0d63d-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="0d63d-230">Depois de verificar se o arquivamento está habilitado, você pode exibir suas políticas de arquivamento para determinar se as sessões de comunicação interna e externa estão sendo arquivadas.</span><span class="sxs-lookup"><span data-stu-id="0d63d-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="0d63d-231">As informações de política de arquivamento podem ser recuperadas usando o cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="0d63d-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="0d63d-232">Por exemplo, este comando retorna informações sobre a política de arquivamento global:</span><span class="sxs-lookup"><span data-stu-id="0d63d-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="0d63d-233">Como as políticas de arquivamento também podem ser configuradas no site e no escopo por usuário, você também pode querer usar este comando, que retorna informações sobre todas as políticas de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="0d63d-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="0d63d-234">As informações recebidas de Get-CsArchivingPolicy serão parecidas com:</span><span class="sxs-lookup"><span data-stu-id="0d63d-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="0d63d-235">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-235">Identity : Global</span></span>

<span data-ttu-id="0d63d-236">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d63d-236">Description :</span></span>

<span data-ttu-id="0d63d-237">ArchiveInternal: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-237">ArchiveInternal : False</span></span>

<span data-ttu-id="0d63d-238">ArchiveExternal: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-238">ArchiveExternal : False</span></span>

<span data-ttu-id="0d63d-239">Observe que, por padrão, o arquivamento interno e externo está desabilitado em uma política de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0d63d-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="0d63d-240">Verificar configurações de CDR</span><span class="sxs-lookup"><span data-stu-id="0d63d-240">Check CDR settings</span></span>

<span data-ttu-id="0d63d-241">Verifique as configurações de CDR (registro de detalhes de chamadas) para gravação de detalhes de chamada de voz e ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="0d63d-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="0d63d-242">Informações detalhadas sobre as configurações de CDR podem ser retornadas usando o cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0d63d-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="0d63d-243">Por exemplo, este comando retorna informações sobre o conjunto global de definições de configuração de CDR:</span><span class="sxs-lookup"><span data-stu-id="0d63d-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="0d63d-244">Como o CDR também pode ser configurado no escopo do site, você também pode querer executar este comando, que retorna informações sobre todas as definições de configuração de CDR:</span><span class="sxs-lookup"><span data-stu-id="0d63d-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="0d63d-245">O cmdlet Get-CsCdrConfiguration retorna informações semelhantes a estas para cada coleção de definições de configuração de CDR:</span><span class="sxs-lookup"><span data-stu-id="0d63d-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="0d63d-246">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-246">Identity : Global</span></span>

<span data-ttu-id="0d63d-247">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-247">EnableCDR : True</span></span>

<span data-ttu-id="0d63d-248">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-248">EnablePurging : True</span></span>

<span data-ttu-id="0d63d-249">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="0d63d-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="0d63d-250">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="0d63d-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="0d63d-251">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="0d63d-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="0d63d-252">Informações semelhantes podem ser retornadas para monitoramento de QoE usando o cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="0d63d-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="0d63d-253">Por exemplo, este comando retorna informações sobre o conjunto global de definições de configuração de QoE:</span><span class="sxs-lookup"><span data-stu-id="0d63d-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="0d63d-254">Essa informação será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="0d63d-254">That information will resemble this:</span></span>

<span data-ttu-id="0d63d-255">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-255">Identity : Global</span></span>

<span data-ttu-id="0d63d-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="0d63d-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="0d63d-257">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-257">EnablePurging : True</span></span>

<span data-ttu-id="0d63d-258">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="0d63d-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="0d63d-259">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="0d63d-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="0d63d-260">EnableExternalConsumer: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="0d63d-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="0d63d-261">ExternalConsumerName :</span></span>

<span data-ttu-id="0d63d-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="0d63d-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="0d63d-263">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-263">EnableQoE : True</span></span>

<span data-ttu-id="0d63d-264">Se você deseja comparar suas configurações de CDR atuais com as configurações de CDR padrão, os valores padrão podem ser revisados executando este comando:</span><span class="sxs-lookup"><span data-stu-id="0d63d-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0d63d-265">Da mesma forma, os valores padrão para monitoramento de QoE podem ser recuperados usando este comando:</span><span class="sxs-lookup"><span data-stu-id="0d63d-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0d63d-266">Você também pode retornar o FQDN dos seus servidores de monitoramento executando este comando:</span><span class="sxs-lookup"><span data-stu-id="0d63d-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="0d63d-267">Verificar configurações de voz</span><span class="sxs-lookup"><span data-stu-id="0d63d-267">Check voice settings</span></span>

<span data-ttu-id="0d63d-268">As configurações de voz normalmente importantes para os administradores estão contidas em políticas de voz e rotas de voz: as políticas de voz contêm as configurações que determinam os recursos expostos a usuários individuais (como a capacidade de encaminhar ou transferir chamadas), enquanto as rotas de voz determinam como as chamadas (e IF) são roteadas através do PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d63d-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="0d63d-269">As informações da política de voz podem ser recuperadas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d63d-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="0d63d-270">Por exemplo, este comando retorna informações sobre a política de voz global:</span><span class="sxs-lookup"><span data-stu-id="0d63d-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="0d63d-271">E este comando retorna informações sobre todas as políticas de voz configuradas para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="0d63d-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="0d63d-272">As informações retornadas pelo cmdlet Get-CsVoicePolicy se assemelham ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="0d63d-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="0d63d-273">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-273">Identity : Global</span></span>

<span data-ttu-id="0d63d-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="0d63d-274">PstnUsages : {}</span></span>

<span data-ttu-id="0d63d-275">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d63d-275">Description :</span></span>

<span data-ttu-id="0d63d-276">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-276">AllowSimulRing : True</span></span>

<span data-ttu-id="0d63d-277">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="0d63d-278">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="0d63d-279">Nome: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="0d63d-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="0d63d-280">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-280">EnableDelegation : True</span></span>

<span data-ttu-id="0d63d-281">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-281">EnableTeamCall : True</span></span>

<span data-ttu-id="0d63d-282">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="0d63d-283">EnableCallPark: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-283">EnableCallPark : False</span></span>

<span data-ttu-id="0d63d-284">EnableMaliciousCallTracing: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="0d63d-285">EnableBWPolicyOverride: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="0d63d-286">PreventPSTNTollBypass: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="0d63d-287">Você também pode criar consultas que retornaram um subconjunto de suas políticas de voz.</span><span class="sxs-lookup"><span data-stu-id="0d63d-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="0d63d-288">Por exemplo, este comando retorna todas as políticas de voz que permitem o encaminhamento de chamadas:</span><span class="sxs-lookup"><span data-stu-id="0d63d-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="0d63d-289">E este comando retorna todas as políticas de voz que não permitem o encaminhamento de chamadas:</span><span class="sxs-lookup"><span data-stu-id="0d63d-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="0d63d-290">No Windows PowerShell, use o cmdlet Get-CsVoiceRouting para retornar informações sobre suas rotas de voz:</span><span class="sxs-lookup"><span data-stu-id="0d63d-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="0d63d-291">Esse comando retorna informações como esta para todas as rotas de voz:</span><span class="sxs-lookup"><span data-stu-id="0d63d-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="0d63d-292">Identidade: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="0d63d-292">Identity : LocalRoute</span></span>

<span data-ttu-id="0d63d-293">Prioridade: 0</span><span class="sxs-lookup"><span data-stu-id="0d63d-293">Priority : 0</span></span>

<span data-ttu-id="0d63d-294">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d63d-294">Description :</span></span>

<span data-ttu-id="0d63d-295">NumberPattern: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="0d63d-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="0d63d-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="0d63d-296">PstnUsages : {}</span></span>

<span data-ttu-id="0d63d-297">PstnGatewayList : {}</span><span class="sxs-lookup"><span data-stu-id="0d63d-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="0d63d-298">Nome: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="0d63d-298">Name : LocalRoute</span></span>

<span data-ttu-id="0d63d-299">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="0d63d-299">SuppressCallerId :</span></span>

<span data-ttu-id="0d63d-300">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="0d63d-300">AlternateCallerId :</span></span>

<span data-ttu-id="0d63d-301">O Lync Server permite que você crie rotas de voz que não têm um uso PSTN e não especificam um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d63d-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="0d63d-302">No entanto, você não pode rotear chamadas por uma rota de voz que não tenha esses dois valores de propriedade configurados.</span><span class="sxs-lookup"><span data-stu-id="0d63d-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="0d63d-303">Por causa disso, você pode achar útil executar este comando periodicamente, que retorna a identidade de qualquer rota de voz que não tenha um uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="0d63d-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="0d63d-304">Da mesma forma, este comando retorna a identidade de qualquer rota de voz que não tenha sido configurada para ter um gateway PSTN:</span><span class="sxs-lookup"><span data-stu-id="0d63d-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="0d63d-305">Verificar configurações de atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="0d63d-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="0d63d-306">Verifique as configurações de atendedor de conferência para conferência discada PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d63d-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="0d63d-307">As configurações de atendedor de conferência só podem ser recuperadas usando o cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0d63d-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="0d63d-308">Essas configurações não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d63d-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="0d63d-309">Para exibir suas configurações de atendedor de conferência, use um comando do Windows PowerShell semelhante ao seguinte, que retorna o conjunto global de configurações de atendedor de conferência:</span><span class="sxs-lookup"><span data-stu-id="0d63d-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="0d63d-310">Observe que as configurações do atendedor de conferência também podem ser configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="0d63d-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="0d63d-311">Para retornar informações sobre todas as configurações de atendedor de conferência, use este comando em vez disso:</span><span class="sxs-lookup"><span data-stu-id="0d63d-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="0d63d-312">O cmdlet Get-CsDialInConferencingConfiguration retorna dados similares a estes:</span><span class="sxs-lookup"><span data-stu-id="0d63d-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="0d63d-313">Identity: global</span><span class="sxs-lookup"><span data-stu-id="0d63d-313">Identity : Global</span></span>

<span data-ttu-id="0d63d-314">EntryExitAnnouncementsType: UseNames</span><span class="sxs-lookup"><span data-stu-id="0d63d-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="0d63d-315">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="0d63d-315">EnableNameRecording : True</span></span>

<span data-ttu-id="0d63d-316">EntryExitAnnouncementsEnabledByDefault: falso</span><span class="sxs-lookup"><span data-stu-id="0d63d-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="0d63d-317">Se EntryExitAnnouncementsEnabledByDefault estiver definido como false, isso significa que os comunicados de conferência estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0d63d-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="0d63d-318">Para habilitar os anúncios de entrada e saída, execute um comando do Windows PowerShell semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="0d63d-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d63d-319">Confira também</span><span class="sxs-lookup"><span data-stu-id="0d63d-319">See Also</span></span>


[<span data-ttu-id="0d63d-320">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="0d63d-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="0d63d-321">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d63d-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="0d63d-322">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0d63d-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="0d63d-323">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d63d-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="0d63d-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0d63d-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="0d63d-325">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d63d-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="0d63d-326">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d63d-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="0d63d-327">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d63d-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="0d63d-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="0d63d-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="0d63d-329">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="0d63d-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="0d63d-330">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d63d-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

