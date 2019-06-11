---
title: 'Lync Server 2013: configurações novas e alteradas do Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Configurações novas e alteradas para o Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-05_

Este tópico discute alterações nos cmdlets do Shell de gerenciamento do Lync Server relacionadas diretamente ao gerenciamento de cliente. O Lync Server 2013 introduz vários parâmetros novos e reprova parâmetros para recursos que podem ser configurados por meio de outros meios.

<div>

## <a name="new-client-management-parameters"></a>Novos parâmetros de gerenciamento de cliente


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Novo</th>
<th>Cmdlet do Shell de gerenciamento do Lync Server</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Quando definido como true, o rastreamento de software será habilitado no Lync; Quando definida como false, o rastreamento de software será desabilitado. O rastreamento de software envolve manter um registro detalhado de tudo o que um programa faz (incluindo o rastreamento de chamadas de API). O rastreamento é principalmente útil para desenvolvedores e para a equipe de suporte do aplicativo. Essa configuração é equivalente à configuração &quot;de política de grupo do Communications Server 2007 R2 ative o rastreamento para o Communicator. &quot; As configurações são as seguintes:</p>
<ul>
<li><p>Off = o rastreamento está desabilitado e o usuário não pode alterar essa configuração.</p></li>
<li><p>Light = o rastreamento mínimo é executado e o usuário não pode alterar essa configuração.</p></li>
<li><p>On = o rastreamento detalhado é executado e o usuário não pode alterar essa configuração.</p></li>
</ul>
<p>Por padrão, TracingLevel é definido como um valor nulo. Isso significa que o rastreamento mínimo é executado, mas o usuário pode habilitar ou desabilitar esse rastreamento mínimo.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Quando definida como true ($True) permite que os fluxos de áudio e vídeo sejam separados de outros tráfegos de rede, por sua vez, isso permite que os dispositivos cliente façam a codificação e decodifique de áudio e vídeo localmente. O redirecionamento de mídia normalmente resulta em uso de largura de banda menor, maior escalabilidade de servidor e uma experiência ideal para o usuário em comparação com técnicas semelhantes, como a compactação de dispositivo ou de compactação de codec.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando definido como verdadeiro, todas as reuniões do Lync são &quot;tratadas como reuniões grandes. &quot; Com uma reunião grande, as restrições são colocadas no número de notificações enviadas aos participantes, além do tamanho da lista de reuniões transmitidas por padrão.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando definido como verdadeiro ($True) os usuários não poderão adicionar anotações aos slides do PowerPoint usados em uma conferência. No entanto, dependendo do valor da propriedade AllowAnnotations, os usuários ainda terão acesso a outros recursos do whiteboard. O valor padrão é false, o que significa que as anotações do PowerPoint são permitidas.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando definido como verdadeiro (o valor padrão), todos os blocos de anotações abertos do OneNote vinculados à conferência serão automaticamente atualizados com informações como participantes da conferência e detalhes sobre o conteúdo compartilhado durante a conferência.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Usado juntamente com outros parâmetros novos CsMeetingConfiguration para personalizar os convites de reunião gerados pelo suplemento de reunião online do Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona o logotipo da sua organização a todos os convites gerados pelo suplemento de reunião online do Lync 2013. Você especifica a URL de uma imagem GIF ou JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona a ajuda ou a URL de suporte da sua organização a todos os convites gerados pelo suplemento de reunião online do Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona texto legal ou texto de aviso de isenção a todos os convites gerados pelo suplemento de reunião online do Lync 2013. Você especifica a URL para o local do texto.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona um rodapé personalizado a todos os convites gerados pelo suplemento de reunião online do Lync 2013. Você especifica a URL para o local do texto do rodapé personalizado.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>Parâmetros de gerenciamento de cliente preteridos


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parâmetro</th>
<th>Cmdlet do Shell de gerenciamento do Lync Server</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Esse parâmetro foi preterido para uso com o Lync Server 2013. Quando usado em conjunto com EnableEnterpriseCustomizedHelp, esse parâmetro habilitou uma organização para especificar uma URL de modo que, quando os usuários clicarem no menu ajuda no Lync, a ajuda personalizada seria exibida.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Esse parâmetro foi preterido para uso com o Lync Server 2013. Quando usado em conjunto com CustomizedHelpUrl, este parâmetro habilitou organizações para exibir a ajuda personalizada.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>O parâmetro EnableSQMData do cmdlet Set-CSClientPolicy foi removido no Lync Server 2013. Em vez disso, você pode usar a configuração de política de grupo compartilhado para dados de gerenciamento de qualidade de software (SQM) para determinar a interface do usuário para a opção de aperfeiçoamento da experiência do usuário na página Opções gerais do cliente do Lync:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valores</p>
<p>1 = exibir e marcar a caixa de seleção (o usuário pode desmarcar a caixa de seleção)</p>
<p>0 = desativar e desativar a caixa de seleção (o usuário não pode substituir)</p>
<p>NULL = o valor é determinado pela instalação do Office e a caixa de seleção é exibida para os usuários definirem como escolher</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Esse parâmetro foi removido. Em vez disso, quando você implanta o Lync Server 2013 e publica a topologia, o repositório de contatos unificado é habilitado para todos os usuários por padrão. Isso significa que todos os contatos de um usuário são mantidos no Exchange e estão disponíveis no Lync, no Outlook e no Outlook Web Access. Você pode usar o cmdlet Set-CsUserServicesPolicy para personalizar quais usuários têm o repositório de contatos unificado disponível. Você pode habilitar usuários globalmente, por site, por locatário ou por indivíduos ou grupos de indivíduos. Para obter detalhes, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">habilitar usuários para o repositório de contatos unificado no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Esse parâmetro não é usado pelo Lync 2013. Em versões anteriores, esse parâmetro especificou com que frequência o cliente recuperou dados MAPI de pastas públicas do Exchange</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parâmetro foi preterido no Lync 2013.</p></td>
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

