---
title: 'Lync Server 2013: configurações novas e alteradas do Lync 2013'
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
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="0a7ce-102">Configurações novas e alteradas para o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0a7ce-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a7ce-103">_**Tópico da última modificação:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="0a7ce-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="0a7ce-104">Este tópico discute alterações nos cmdlets do Shell de gerenciamento do Lync Server relacionadas diretamente ao gerenciamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="0a7ce-105">O Lync Server 2013 introduz vários parâmetros novos e reprova parâmetros para recursos que podem ser configurados por meio de outros meios.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="0a7ce-106">Novos parâmetros de gerenciamento de cliente</span><span class="sxs-lookup"><span data-stu-id="0a7ce-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a7ce-107">Novo</span><span class="sxs-lookup"><span data-stu-id="0a7ce-107">New</span></span></th>
<th><span data-ttu-id="0a7ce-108">Cmdlet do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="0a7ce-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="0a7ce-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a7ce-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="0a7ce-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-112">Quando definido como true, o rastreamento de software será habilitado no Lync; Quando definida como false, o rastreamento de software será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="0a7ce-113">O rastreamento de software envolve manter um registro detalhado de tudo o que um programa faz (incluindo o rastreamento de chamadas de API).</span><span class="sxs-lookup"><span data-stu-id="0a7ce-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="0a7ce-114">O rastreamento é principalmente útil para desenvolvedores e para a equipe de suporte do aplicativo. Essa configuração é equivalente à configuração &quot;de política de grupo do Communications Server 2007 R2 ative o rastreamento para o Communicator. &quot; As configurações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="0a7ce-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="0a7ce-115">Off = o rastreamento está desabilitado e o usuário não pode alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="0a7ce-116">Light = o rastreamento mínimo é executado e o usuário não pode alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="0a7ce-117">On = o rastreamento detalhado é executado e o usuário não pode alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="0a7ce-118">Por padrão, TracingLevel é definido como um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="0a7ce-119">Isso significa que o rastreamento mínimo é executado, mas o usuário pode habilitar ou desabilitar esse rastreamento mínimo.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="0a7ce-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-122">Quando definida como true ($True) permite que os fluxos de áudio e vídeo sejam separados de outros tráfegos de rede, por sua vez, isso permite que os dispositivos cliente façam a codificação e decodifique de áudio e vídeo localmente.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="0a7ce-123">O redirecionamento de mídia normalmente resulta em uso de largura de banda menor, maior escalabilidade de servidor e uma experiência ideal para o usuário em comparação com técnicas semelhantes, como a compactação de dispositivo ou de compactação de codec.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="0a7ce-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="0a7ce-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-126">Quando definido como verdadeiro, todas as reuniões do Lync são &quot;tratadas como reuniões grandes. &quot; Com uma reunião grande, as restrições são colocadas no número de notificações enviadas aos participantes, além do tamanho da lista de reuniões transmitidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="0a7ce-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="0a7ce-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-129">Quando definido como verdadeiro ($True) os usuários não poderão adicionar anotações aos slides do PowerPoint usados em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="0a7ce-130">No entanto, dependendo do valor da propriedade AllowAnnotations, os usuários ainda terão acesso a outros recursos do whiteboard.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="0a7ce-131">O valor padrão é false, o que significa que as anotações do PowerPoint são permitidas.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="0a7ce-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="0a7ce-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-134">Quando definido como verdadeiro (o valor padrão), todos os blocos de anotações abertos do OneNote vinculados à conferência serão automaticamente atualizados com informações como participantes da conferência e detalhes sobre o conteúdo compartilhado durante a conferência.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="0a7ce-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7ce-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-137">Usado juntamente com outros parâmetros novos CsMeetingConfiguration para personalizar os convites de reunião gerados pelo suplemento de reunião online do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="0a7ce-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7ce-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-140">Adiciona o logotipo da sua organização a todos os convites gerados pelo suplemento de reunião online do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="0a7ce-141">Você especifica a URL de uma imagem GIF ou JPG.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="0a7ce-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7ce-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-144">Adiciona a ajuda ou a URL de suporte da sua organização a todos os convites gerados pelo suplemento de reunião online do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="0a7ce-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7ce-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-147">Adiciona texto legal ou texto de aviso de isenção a todos os convites gerados pelo suplemento de reunião online do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="0a7ce-148">Você especifica a URL para o local do texto.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="0a7ce-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7ce-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-151">Adiciona um rodapé personalizado a todos os convites gerados pelo suplemento de reunião online do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="0a7ce-152">Você especifica a URL para o local do texto do rodapé personalizado.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="0a7ce-153">Parâmetros de gerenciamento de cliente preteridos</span><span class="sxs-lookup"><span data-stu-id="0a7ce-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a7ce-154">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="0a7ce-154">Parameter</span></span></th>
<th><span data-ttu-id="0a7ce-155">Cmdlet do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="0a7ce-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="0a7ce-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a7ce-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="0a7ce-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-159">Esse parâmetro foi preterido para uso com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="0a7ce-160">Quando usado em conjunto com EnableEnterpriseCustomizedHelp, esse parâmetro habilitou uma organização para especificar uma URL de modo que, quando os usuários clicarem no menu ajuda no Lync, a ajuda personalizada seria exibida.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="0a7ce-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-163">Esse parâmetro foi preterido para uso com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="0a7ce-164">Quando usado em conjunto com CustomizedHelpUrl, este parâmetro habilitou organizações para exibir a ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="0a7ce-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-167">O parâmetro EnableSQMData do cmdlet Set-CSClientPolicy foi removido no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="0a7ce-168">Em vez disso, você pode usar a configuração de política de grupo compartilhado para dados de gerenciamento de qualidade de software (SQM) para determinar a interface do usuário para a opção de aperfeiçoamento da experiência do usuário na página Opções gerais do cliente do Lync:</span><span class="sxs-lookup"><span data-stu-id="0a7ce-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="0a7ce-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="0a7ce-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="0a7ce-170">Valores</span><span class="sxs-lookup"><span data-stu-id="0a7ce-170">Values:</span></span></p>
<p><span data-ttu-id="0a7ce-171">1 = exibir e marcar a caixa de seleção (o usuário pode desmarcar a caixa de seleção)</span><span class="sxs-lookup"><span data-stu-id="0a7ce-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="0a7ce-172">0 = desativar e desativar a caixa de seleção (o usuário não pode substituir)</span><span class="sxs-lookup"><span data-stu-id="0a7ce-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="0a7ce-173">NULL = o valor é determinado pela instalação do Office e a caixa de seleção é exibida para os usuários definirem como escolher</span><span class="sxs-lookup"><span data-stu-id="0a7ce-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="0a7ce-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-176">Esse parâmetro foi removido.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-176">This parameter has been removed.</span></span> <span data-ttu-id="0a7ce-177">Em vez disso, quando você implanta o Lync Server 2013 e publica a topologia, o repositório de contatos unificado é habilitado para todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="0a7ce-178">Isso significa que todos os contatos de um usuário são mantidos no Exchange e estão disponíveis no Lync, no Outlook e no Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="0a7ce-179">Você pode usar o cmdlet Set-CsUserServicesPolicy para personalizar quais usuários têm o repositório de contatos unificado disponível.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="0a7ce-180">Você pode habilitar usuários globalmente, por site, por locatário ou por indivíduos ou grupos de indivíduos.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="0a7ce-181">Para obter detalhes, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">habilitar usuários para o repositório de contatos unificado no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a7ce-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="0a7ce-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-184">Esse parâmetro não é usado pelo Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="0a7ce-185">Em versões anteriores, esse parâmetro especificou com que frequência o cliente recuperou dados MAPI de pastas públicas do Exchange</span><span class="sxs-lookup"><span data-stu-id="0a7ce-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a7ce-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="0a7ce-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0a7ce-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="0a7ce-188">Este parâmetro foi preterido no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0a7ce-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

