---
title: 'Lync Server 2013: processo de implantação para estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Processo de implantação para estacionamento de chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de estacionamento de chamadas. Você deve implantar a edição Enterprise ou Standard Edition com o Enterprise Voice antes de configurar o parque de chamadas. Os componentes exigidos pelo parque de chamadas são instalados e habilitados durante a implantação do Enterprise Voice.

### <a name="call-park-deployment-process"></a>Implantação do Processo de Estacionamento de Chamada

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
<th>Grupos e funções necessários</th>
<th>Documentação de implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configure os intervalos de órbita de estacionamento de chamada na tabela de órbita</p></td>
<td><p>Use o painel de controle do Lync Server ou o cmdlet <strong>New-CSCallParkOrbit</strong> para criar os intervalos de órbita na tabela órbita do estacionamento de chamada e associá-los ao serviço de aplicativo que hospeda o aplicativo parque de chamadas.</p>
<div>

> [!NOTE]  
> Para uma integração perfeita aos planos de discagem existentes, os intervalos de órbitas são normalmente considerados como um bloco de ramais virtuais. Não há suporte para a atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Criar ou modificar uma faixa de opções do parque de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Definir configurações de estacionamento de chamadas</p></td>
<td><p>Use o cmdlet <strong>set-CsCpsConfiguration</strong> para configurar as configurações de estacionamento de chamadas. No mínimo, recomendamos que você configure a opção <strong>OnTimeoutURI</strong> para configurar o destino de fallback a ser usado quando uma chamada estacionada expirar. Você também pode definir as seguintes configurações:</p>
<ul>
<li><p>(Opcional) <strong>EnableMusicOnHold</strong> para habilitar ou desabilitar a música em espera.</p></li>
<li><p>(Opcional)  <strong>MaxCallPickupAttempts</strong> para determinar o número de vezes que uma chamada estacionada toca novamente no telefone de atendimento, antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback.</p></li>
<li><p>(Opcional)  <strong>CallPickupTimeoutThreshold</strong> para determinar o tempo decorrido depois que a chamada foi estacionada, antes que toque novamente no telefone em que foi atendida.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Configurar as definições do estacionamento de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Opcionalmente, personalize a música em espera</p></td>
<td><p>Use o cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> para personalizar e carregar um arquivo de áudio, se você não deseja usar a música em espera padrão.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizar a chamada de música do parque em espera no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar a política de voz para habilitar o estacionamento de chamadas para usuários</p></td>
<td><p>Use o painel de controle do Lync Server ou o cmdlet <strong>set-CSVoicePolicy</strong> com a opção <strong>EnableCallPark</strong> para habilitar o estacionamento de chamadas para usuários na política de voz.</p>
<div>

> [!NOTE]  
> Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.


</div>
<div>

> [!NOTE]  
> Se você tiver diversas políticas de voz, veja se a propriedade EnableCallPark está configurada para cada política, não somente para a padrão.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Habilitar o estacionamento de chamadas para usuários no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificar regras de normalização para Estacionamento de Chamadas</p></td>
<td><p>Órbitas de estacionamento de chamadas não devem ser normalizadas. Verifique se suas regras de normalização não incluem nenhum intervalo de órbita. Se necessário, crie regras adicionais de normalização para evitar órbitas normalizadas.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verificar as regras de normalização para o parque de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Verifique a implantação do estacionamento de chamadas</p></td>
<td><p>Teste estacionar e recuperar chamadas para verificar se a configuração funciona como esperado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Adicionais Verificar a implantação do estacionamento de chamadas no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

