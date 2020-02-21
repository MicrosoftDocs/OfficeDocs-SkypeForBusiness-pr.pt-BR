---
title: 'Lync Server 2013: configurações novas e alteradas para o Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de4a1a82dbefb5a7f55a4c5872a6702933af08c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="790ed-102">Configurações novas e alteradas para o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="790ed-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="790ed-103">_**Última modificação do tópico:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="790ed-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="790ed-104">Este tópico discute alterações nos cmdlets do Shell de gerenciamento do Lync Server que se relacionam diretamente com o gerenciamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="790ed-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="790ed-105">O Lync Server 2013 introduz vários novos parâmetros e substitui parâmetros para recursos que podem ser configurados por outros meios.</span><span class="sxs-lookup"><span data-stu-id="790ed-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="790ed-106">Novos parâmetros de gerenciamento de cliente</span><span class="sxs-lookup"><span data-stu-id="790ed-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="790ed-107">Novo</span><span class="sxs-lookup"><span data-stu-id="790ed-107">New</span></span></th>
<th><span data-ttu-id="790ed-108">Cmdlet do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="790ed-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="790ed-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="790ed-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="790ed-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="790ed-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="790ed-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-112">Quando definido como true, o rastreamento de software será habilitado no Lync; Quando definido como false, o rastreamento de software será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="790ed-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="790ed-113">O rastreamento de software envolve a manutenção de um registro detalhado de tudo que o programa faz (incluindo chamadas de API de rastreamento).</span><span class="sxs-lookup"><span data-stu-id="790ed-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="790ed-114">O rastreamento é praticamente útil para desenvolvedores e para a equipe de suporte a aplicativos. Essa configuração equivale à configuração &quot;de política de grupo do Communications Server 2007 R2 ative o rastreamento para o Communicator. &quot; As configurações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="790ed-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="790ed-115">Off = o rastreamento está desabilitado e o usuário não pode alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="790ed-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="790ed-116">Light = o rastreamento mínimo é executado e o usuário não pode alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="790ed-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="790ed-117">On = o rastreamento detalhado é executado e o usuário não pode alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="790ed-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="790ed-118">Por padrão, TracingLevel é definido como um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="790ed-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="790ed-119">Isso significa que o rastreamento mínimo é executado, mas o usuário pode habilitar ou desabilitar esse rastreamento mínimo.</span><span class="sxs-lookup"><span data-stu-id="790ed-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="790ed-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="790ed-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-122">Quando definido como true ($True) permite que os fluxos de áudio e vídeo sejam separados de outro tráfego de rede, por sua vez, isso permite que os dispositivos cliente façam a codificação e decodificação de áudio e vídeo localmente.</span><span class="sxs-lookup"><span data-stu-id="790ed-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="790ed-123">O redirecionamento de mídia geralmente resulta em um menor uso de largura de banda, maior escalabilidade do servidor e uma experiência do usuário melhor em comparação com técnicas semelhantes como a compactação de codec ou dispositivo remoto.</span><span class="sxs-lookup"><span data-stu-id="790ed-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="790ed-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="790ed-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="790ed-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="790ed-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="790ed-126">Quando definido como true, todas as reuniões do Lync são &quot;tratadas como grandes reuniões. &quot; Com uma grande reunião, as restrições são colocadas no número de notificações enviadas aos participantes, além do tamanho da lista de reunião que é transmitida por padrão.</span><span class="sxs-lookup"><span data-stu-id="790ed-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="790ed-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="790ed-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="790ed-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="790ed-129">Quando definido como true ($True), os usuários não poderão adicionar anotações aos slides do PowerPoint usados em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="790ed-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="790ed-130">No entanto (dependendo do valor da propriedade AllowAnnotations), os usuários ainda terão acesso a outros recursos de quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="790ed-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="790ed-131">O valor padrão é false, o que significa que as anotações do PowerPoint são permitidas.</span><span class="sxs-lookup"><span data-stu-id="790ed-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="790ed-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="790ed-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="790ed-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="790ed-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="790ed-134">Quando definido como true (o valor padrão), os blocos de anotações abertos do OneNote vinculados à conferência serão automaticamente atualizados com informações como participantes da conferência e detalhes sobre o conteúdo compartilhado durante a conferência.</span><span class="sxs-lookup"><span data-stu-id="790ed-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="790ed-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="790ed-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="790ed-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="790ed-137">Usada junto com outros parâmetros novos do CsMeetingConfiguration para personalizar os convites de reunião gerados pelo suplemento de reunião online para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="790ed-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="790ed-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="790ed-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="790ed-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="790ed-140">Adiciona o logotipo da sua organização a todos os convites gerados pelo suplemento reunião online para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="790ed-141">Você especifica a URL de uma imagem GIF ou JPG.</span><span class="sxs-lookup"><span data-stu-id="790ed-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="790ed-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="790ed-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="790ed-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="790ed-144">Adiciona a URL de ajuda ou suporte da sua organização a todos os convites gerados pelo suplemento de reunião online para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="790ed-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="790ed-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="790ed-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="790ed-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="790ed-147">Adiciona texto legal ou aviso de isenção a todos os convites gerados pelo suplemento reunião online para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="790ed-148">Você especifica a URL para o local do texto.</span><span class="sxs-lookup"><span data-stu-id="790ed-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="790ed-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="790ed-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="790ed-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="790ed-151">Adiciona um rodapé personalizado a todos os convites gerados pelo suplemento reunião online para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="790ed-152">Você especifica a URL para o local do texto de rodapé personalizado.</span><span class="sxs-lookup"><span data-stu-id="790ed-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="790ed-153">Parâmetros de gerenciamento de cliente preteridos</span><span class="sxs-lookup"><span data-stu-id="790ed-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="790ed-154">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="790ed-154">Parameter</span></span></th>
<th><span data-ttu-id="790ed-155">Cmdlet do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="790ed-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="790ed-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="790ed-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="790ed-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="790ed-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="790ed-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-159">Esse parâmetro foi preterido para uso com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="790ed-160">Quando usado em conjunto com EnableEnterpriseCustomizedHelp, esse parâmetro permitiu que uma organização especificasse uma URL para que, quando os usuários clicarem no menu ajuda no Lync, a ajuda personalizada seja exibida.</span><span class="sxs-lookup"><span data-stu-id="790ed-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="790ed-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="790ed-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-163">Esse parâmetro foi preterido para uso com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="790ed-164">Quando usado em conjunto com o CustomizedHelpUrl, este parâmetro permitiu que as organizações exibam a ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="790ed-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="790ed-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="790ed-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="790ed-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-167">O parâmetro EnableSQMData do cmdlet Set-CSClientPolicy foi removido no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="790ed-168">Em vez disso, você pode usar a configuração da política de grupo compartilhada para dados de SQM (gerenciamento de qualidade de software) para determinar a interface do usuário para a opção de aperfeiçoamento da experiência do cliente na página Opções gerais do cliente do Lync:</span><span class="sxs-lookup"><span data-stu-id="790ed-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="790ed-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="790ed-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="790ed-170">Valores</span><span class="sxs-lookup"><span data-stu-id="790ed-170">Values:</span></span></p>
<p><span data-ttu-id="790ed-171">1 = exibir e marcar a caixa de seleção (o usuário pode desmarcar a caixa de seleção)</span><span class="sxs-lookup"><span data-stu-id="790ed-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="790ed-172">0 = desativar e desabilitar a caixa de seleção (o usuário não pode substituir)</span><span class="sxs-lookup"><span data-stu-id="790ed-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="790ed-173">NULL = o valor é determinado pela instalação do Office e a caixa de seleção é exibida para que os usuários definam como escolher</span><span class="sxs-lookup"><span data-stu-id="790ed-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="790ed-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="790ed-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-176">Esse parâmetro foi removido.</span><span class="sxs-lookup"><span data-stu-id="790ed-176">This parameter has been removed.</span></span> <span data-ttu-id="790ed-177">Em vez disso, ao implantar o Lync Server 2013 e publicar a topologia, o repositório unificado de contatos é habilitado para todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="790ed-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="790ed-178">Isso significa que todos os contatos de um usuário são mantidos no Exchange e estão disponíveis no Lync, Outlook e Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="790ed-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="790ed-179">Você pode usar o cmdlet Set-CsUserServicesPolicy para personalizar quais usuários têm o repositório unificado de contatos disponível.</span><span class="sxs-lookup"><span data-stu-id="790ed-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="790ed-180">Você pode habilitar os usuários globalmente, por site, por locatário ou por indivíduos ou grupos de pessoas.</span><span class="sxs-lookup"><span data-stu-id="790ed-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="790ed-181">Para obter detalhes, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">habilitar usuários para o repositório unificado de contatos no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="790ed-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="790ed-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="790ed-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="790ed-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-184">Este parâmetro não é usado pelo Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="790ed-185">Em versões anteriores, esse parâmetro especificou com que frequência o cliente recuperou dados MAPI de pastas públicas do Exchange</span><span class="sxs-lookup"><span data-stu-id="790ed-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="790ed-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="790ed-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="790ed-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="790ed-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="790ed-188">Este parâmetro foi preterido no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="790ed-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

