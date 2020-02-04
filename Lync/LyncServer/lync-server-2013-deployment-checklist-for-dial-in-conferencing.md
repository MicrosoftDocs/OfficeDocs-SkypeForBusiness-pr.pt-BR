---
title: 'Lync Server 2013: Lista de verificação de implantação para conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf496dcb24c021246bfbb6e7a5ef7b3a3a5acc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lista de verificação de implantação para conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-10-03_

Os componentes necessários para a conferência discada são implantados quando você implanta a carga de trabalho de conferência. Antes de poder configurar a conferência discada, você precisa implantar o Enterprise Voice ou um servidor de mediação (PSTN) e um gateway de rede telefônica pública comutada (PSTN).

Todas as etapas na tabela a seguir devem ser realizadas antes que os usuários possam discar da PSTN para ingressar em uma conferência de áudio/vídeo.

<div>


> [!NOTE]  
> Se estiver migrando do Office Communications Server 2007 R2, você deve aplicar as atualizações mais recentes ao seu ambiente do Office Communications Server 2007 R2 antes de implantar a conferência discada.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Processo de implantação de conferência discada

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
<th>Permissões</th>
<th>Documentação de Implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Crie uma topologia que inclua a carga de trabalho de conferência, incluindo um servidor de mediação e um gateway PSTN, e implante o pool de front-end ou o servidor Standard Edition</strong></p></td>
<td><ol>
<li><p>Executar o construtor de topologias para configurar sua topologia. Enquanto a configuração da topologia é executada, selecione a opção de conferência discada.</p></li>
<li><p>Publique a topologia e implante o pool de front-end ou o servidor Standard Edition.</p></li>
<li><p>Se necessário, crie um servidor de mediação autônomo e associe-o a um gateway PSTN.</p>
<div>

> [!NOTE]  
> Esta etapa é necessária apenas se você não implantar o Enterprise Voice e não colocar o servidor de mediação com o servidor do Enterprise EditionFront end Server ou Standard Edition. Se você implantar o Enterprise Voice, instale e configure os servidores de mediação e os gateways PSTN como parte da implantação do Enterprise Voice. Se você colocar o servidor de mediação, instale e configure o servidor de mediação como parte do pool de front-end ou da implantação do servidor Standard Edition.


</div></li>
</ol></td>
<td><p>Admins. do Domínio</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrador</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Implantando o Lync Server 2013</a></p></li>
<li><p>Para criar um pool autônomo do servidor de mediação: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">implantação de servidores de mediação e definição de pares no Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial plans</strong></p></td>
<td><p>Um plano de discagem é um conjunto de regras de normalização de número de telefone que traduzem números discados de um local específico para um padrão de formato único (E.164), para fins de autorização do telefone e roteamento de chamadas. O mesmo número de telefone discado a partir de locais diferentes pode, com base nos respectivos planos de discagem, resolver para diferentes números E.164, conforme o que for mais adequado para cada local. Se você implantar o Enterprise Voice, configure planos de discagem como parte dessa implantação, e você precisará certificar-se de que os planos de discagem também acomodem a conferência discada. Se você não implantar o Enterprise Voice, será necessário configurar planos de discagem para conferência discada.</p>
<p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para configurar planos de discagem da seguinte maneira:</p>
<ol>
<li><p>Crie um ou mais planos de discagem para rotear números de telefone de acesso de discagem.</p></li>
<li><p>Atribua um plano de discagem padrão para cada pool. Defina a <strong>Região da conferência discada</strong> à localização geográfica à qual o plano de discagem se aplica. A região associa o plano de discagem aos números de acesso discado.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurar planos de discagem para conferência discada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Verifique se os planos de discagem possuem regiões atribuídas</strong></p></td>
<td><p>Execute os cmdlets <strong>Get-CsDialPlan</strong> e <strong>Set-CsDialPlan</strong> para verificar se todos os planos de discagem possuem uma região atribuída.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Verifique se os planos de discagem do Lync Server 2013 atribuiram regiões</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Verifique ou modifique os requisitos do número de identificação pessoal (PIN) do usuário.</strong></p></td>
<td><p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para exibir ou modificar a <strong>política de PIN</strong>de conferência. Você pode especificar o comprimento mínimo do PIN, o número máximo de tentativas de logon, a expiração do PIN e se padrões comuns são permissíveis.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Opcional) Verificar configurações de política de PIN no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configure a política de conferência para suportar conferências discadas.</strong></p></td>
<td><p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de <strong>política de conferência</strong> . Especifique se:</p>
<ul>
<li><p>A discagem de conferência PSTN está habilitada.</p></li>
<li><p>Usuários podem convidar participantes anônimos.</p></li>
<li><p>Usuários não autenticados podem participar de uma conferência usando discagem de saída. Com a discagem de saída, o servidor de conferência faz uma chamada para o usuário e o usuário atende o telefone para entrar na conferência.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurar política de conferência para discagem no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial-in access numbers</strong></p></td>
<td><p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para configurar números de acesso discada que os usuários chamam para discar para uma conferência e especifique as regiões que associam o número de acesso com os planos de discagem apropriados. Os três primeiros números de acesso para a região especificada pelo plano de discagem do organizador são incluídos no convite da conferência. Todos os números de acesso estão disponíveis na página Configurações de conferência discada.</p>
<div>

> [!NOTE]  
> Depois de criar números de acesso discado, você pode usar o cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar o nome de exibição dos objetos de contato do Active Directory para que os usuários possam identificar mais facilmente o número de acesso correto.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurar número de acesso da conferência discada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Opcional) Verifique as configurações da conferência discada</strong></p></td>
<td><p>Use o cmdlet  <strong>Get-CsDialinConferencingAccessNumber</strong> para pesquisar planos de discagem que tenham uma região de conferência discada que não seja usada por qualquer número de acesso e números de acesso que não possuam região atribuída.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Opcional) Verificar configurações de conferência discada no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Modifique o mapeamento de teclas dos comandos DTMF</strong></p></td>
<td><p>Use o cmdlet <strong>set-CsDialinConferencingDtmfConfiguration</strong> para modificar as chaves usadas para comandos de multifrequência (DTMF) de Tom duplo, quais participantes podem usar para controlar as configurações de conferência (como ativar e desativar mudo ou bloquear e desbloquear).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Opcional) Modificar mapeamento principal de comandos DTMF no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Opcional) Modifique o comportamento do anúncio de entrada e saída da conferência</strong></p></td>
<td><p>Use o cmdlet  <strong>Set-CsDialinConferencingConfiguration</strong> para alterar como os anúncios funcionam quando participantes entram e saem das conferências.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Opcional) Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Verifique a conferência discada</strong></p></td>
<td><p>Use o cmdlet  <strong>Test-CsDialInConferencing</strong> para testar se os números de acesso para o pool especificado estão funcionando corretamente.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Opcional) Verificar conferência discada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Implantar suplemento Online Meeting para Lync 2013</strong></p></td>
<td><p>Implante o suplemento de reunião online do Lync 2013 para que os usuários possam agendar conferências que dão suporte à conferência discada. O suplemento de reunião online do Lync 2013 é instalado automaticamente quando você instala o Lync 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Implantar suplemento Online Meeting para Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Definir configurações de conta do usuário</strong></p></td>
<td><p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para configurar o <strong>URI da linha</strong> de telefonia como um número de telefone normalizado exclusivo (por exemplo, Tel: + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Definir configurações de conta do usuário no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Recomendado) Configurar diretórios de conferência</p></td>
<td><p>Use o cmdlet <strong>New-CsConferenceDirectory</strong> para criar um diretório de conferência para cada 999 usuários no pool.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Requisitos de conferência discada no Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(recomendado) criar diretórios de conferência</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Receba os usuários em conferências discadas e defina o PIN inicial</strong></p></td>
<td><p>Use o script <strong>set-CsPinSendCAWelcomeMail</strong> para definir os Pins iniciais dos usuários e enviar um email de boas-vindas que contenha o PIN inicial e um link para a página Configurações de conferência discada.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Opcional) Dar as boas-vindas aos usuários na conferência discada no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

