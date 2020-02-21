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

# <a name="new-and-changed-settings-for-lync-2013"></a>Configurações novas e alteradas para o Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-05_

Este tópico discute alterações nos cmdlets do Shell de gerenciamento do Lync Server que se relacionam diretamente com o gerenciamento de cliente. O Lync Server 2013 introduz vários novos parâmetros e substitui parâmetros para recursos que podem ser configurados por outros meios.

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
<td><p>Quando definido como true, o rastreamento de software será habilitado no Lync; Quando definido como false, o rastreamento de software será desabilitado. O rastreamento de software envolve a manutenção de um registro detalhado de tudo que o programa faz (incluindo chamadas de API de rastreamento). O rastreamento é praticamente útil para desenvolvedores e para a equipe de suporte a aplicativos. Essa configuração equivale à configuração &quot;de política de grupo do Communications Server 2007 R2 ative o rastreamento para o Communicator. &quot; As configurações são as seguintes:</p>
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
<td><p>Quando definido como true ($True) permite que os fluxos de áudio e vídeo sejam separados de outro tráfego de rede, por sua vez, isso permite que os dispositivos cliente façam a codificação e decodificação de áudio e vídeo localmente. O redirecionamento de mídia geralmente resulta em um menor uso de largura de banda, maior escalabilidade do servidor e uma experiência do usuário melhor em comparação com técnicas semelhantes como a compactação de codec ou dispositivo remoto.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando definido como true, todas as reuniões do Lync são &quot;tratadas como grandes reuniões. &quot; Com uma grande reunião, as restrições são colocadas no número de notificações enviadas aos participantes, além do tamanho da lista de reunião que é transmitida por padrão.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando definido como true ($True), os usuários não poderão adicionar anotações aos slides do PowerPoint usados em uma conferência. No entanto (dependendo do valor da propriedade AllowAnnotations), os usuários ainda terão acesso a outros recursos de quadro de comunicações. O valor padrão é false, o que significa que as anotações do PowerPoint são permitidas.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando definido como true (o valor padrão), os blocos de anotações abertos do OneNote vinculados à conferência serão automaticamente atualizados com informações como participantes da conferência e detalhes sobre o conteúdo compartilhado durante a conferência.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Usada junto com outros parâmetros novos do CsMeetingConfiguration para personalizar os convites de reunião gerados pelo suplemento de reunião online para Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona o logotipo da sua organização a todos os convites gerados pelo suplemento reunião online para Lync 2013. Você especifica a URL de uma imagem GIF ou JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona a URL de ajuda ou suporte da sua organização a todos os convites gerados pelo suplemento de reunião online para o Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona texto legal ou aviso de isenção a todos os convites gerados pelo suplemento reunião online para Lync 2013. Você especifica a URL para o local do texto.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Adiciona um rodapé personalizado a todos os convites gerados pelo suplemento reunião online para Lync 2013. Você especifica a URL para o local do texto de rodapé personalizado.</p></td>
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
<td><p>Esse parâmetro foi preterido para uso com o Lync Server 2013. Quando usado em conjunto com EnableEnterpriseCustomizedHelp, esse parâmetro permitiu que uma organização especificasse uma URL para que, quando os usuários clicarem no menu ajuda no Lync, a ajuda personalizada seja exibida.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Esse parâmetro foi preterido para uso com o Lync Server 2013. Quando usado em conjunto com o CustomizedHelpUrl, este parâmetro permitiu que as organizações exibam a ajuda personalizada.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>O parâmetro EnableSQMData do cmdlet Set-CSClientPolicy foi removido no Lync Server 2013. Em vez disso, você pode usar a configuração da política de grupo compartilhada para dados de SQM (gerenciamento de qualidade de software) para determinar a interface do usuário para a opção de aperfeiçoamento da experiência do cliente na página Opções gerais do cliente do Lync:</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valores</p>
<p>1 = exibir e marcar a caixa de seleção (o usuário pode desmarcar a caixa de seleção)</p>
<p>0 = desativar e desabilitar a caixa de seleção (o usuário não pode substituir)</p>
<p>NULL = o valor é determinado pela instalação do Office e a caixa de seleção é exibida para que os usuários definam como escolher</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Esse parâmetro foi removido. Em vez disso, ao implantar o Lync Server 2013 e publicar a topologia, o repositório unificado de contatos é habilitado para todos os usuários por padrão. Isso significa que todos os contatos de um usuário são mantidos no Exchange e estão disponíveis no Lync, Outlook e Outlook Web Access. Você pode usar o cmdlet Set-CsUserServicesPolicy para personalizar quais usuários têm o repositório unificado de contatos disponível. Você pode habilitar os usuários globalmente, por site, por locatário ou por indivíduos ou grupos de pessoas. Para obter detalhes, consulte <a href="lync-server-2013-enable-users-for-unified-contact-store.md">habilitar usuários para o repositório unificado de contatos no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Este parâmetro não é usado pelo Lync 2013. Em versões anteriores, esse parâmetro especificou com que frequência o cliente recuperou dados MAPI de pastas públicas do Exchange</p></td>
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

