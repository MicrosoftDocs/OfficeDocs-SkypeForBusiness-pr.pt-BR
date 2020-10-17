---
title: 'Lync Server 2013: processo de implantação para recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522608"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Processo de implantação do recebimento de chamadas em grupo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

Esta seção fornece uma visão geral das etapas envolvidas na implantação do recebimento de chamadas em grupo. Você deve implantar o Enterprise Edition ou Standard Edition com o Enterprise Voice antes de configurar o recebimento de chamadas em grupo. Os componentes necessários para o recebimento de chamadas em grupo são instalados e habilitados quando você implanta o Enterprise Voice.

### <a name="group-call-pickup-deployment-process"></a>Processo de implantação de recebimento de chamadas de grupo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Grupos e funções exigidos</th>
<th>Documentação da implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Habilitar a ferramenta SEFAUtil Resource Kit na topologia</p></td>
<td><ol>
<li><p>Use o cmdlet <strong>New-CsTrustedApplicationPool</strong> para criar um novo pool de aplicativos confiáveis.</p></li>
<li><p>Use o cmdlet <strong>New-CsTrustedApplication</strong> para especificar a ferramenta SEFAUtil como aplicativo confiável.</p></li>
<li><p>Execute o cmdlet <strong>Enable-CsTopology</strong> para habilitar a topologia.</p></li>
<li><p>Instale as ferramentas do kit de recursos em um servidor front-end que esteja no pool de aplicativos confiáveis criado na etapa 1.</p></li>
<li><p>Verifique se o SEFAUtil está funcionando corretamente executando-o para exibir as configurações de encaminhamento de chamadas de um usuário na implantação.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Implantar a ferramenta SEFAUtil no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar intervalos de números de recebimento de chamada na tabela de órbita de estacionamento de chamada</p></td>
<td><p>Use o cmdlet <strong>New-CSCallParkOrbit</strong> para criar intervalos de números de recebimento de chamadas na tabela de órbitas do estacionamento de chamadas e atribua ao tipo de chamada os intervalos de GroupPickup.</p>
<div>

> [!NOTE]  
> Você deve usar o Shell de gerenciamento do Lync Server para criar, modificar, remover e exibir intervalos de números de recebimento de chamadas em grupo na tabela de órbita de estacionamento de chamada. Os intervalos de números de recebimento de chamadas de grupo não estão disponíveis no painel de controle do Lync Server.


</div>
<div>

> [!NOTE]  
> Para uma integração perfeita com planos de discagem existentes, os intervalos de números geralmente são configurados como um bloco de extensões virtuais. A atribuição de números DID (discagem direta interna) como números de intervalo na tabela de órbita de estacionamento de chamada não é suportada.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar números de grupos de recebimento de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Atribuir um número de recebimento de chamada aos usuários e habilitar o recebimento de chamadas em grupo para os usuários</p></td>
<td><p>Use o parâmetro/enablegrouppickup na ferramenta do kit de recursos do SEFAUtil para habilitar o recebimento de chamadas em grupo e atribuir um número de recebimento de chamada para os usuários.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013 e atribuir um número de grupo</a></p></td>
</tr>
<tr class="even">
<td><p>Notificar os usuários sobre o número de recebimento de chamadas atribuído e qualquer outro número de interesse</p></td>
<td><p>Como qualquer usuário pode recuperar uma chamada feita para um usuário de recebimento de chamada em grupo, os usuários podem querer monitorar mais de um grupo.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar as atribuições de recebimento de chamadas de grupo aos usuários no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificar a implantação do recebimento de chamadas em grupo</p></td>
<td><p>Teste a colocação e recuperação de chamadas para garantir que a configuração funcione conforme o esperado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opcion Verificar a implantação do recebimento de chamadas em grupo no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

