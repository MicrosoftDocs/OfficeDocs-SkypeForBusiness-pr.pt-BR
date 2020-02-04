---
title: 'Lync Server 2013: Processo de implantação para integrar o Exchange UM hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Processo de implantação para integrar o Exchange UM hospedado ao Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-25_

O planejamento efetivo para a integração do Lync Server 2013 com a Unificação de mensagens do Exchange hospedada requer que você leve em conta o seguinte:

  - Pré-requisitos para a integração do Lync Server 2013 com o Exchange UM hospedado

  - Etapas necessárias durante o processo de integração

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Pré-requisitos de implantação para integração com o Exchange UM hospedado

Antes de começar o processo de integração, você já deve ter implantado o Lync Server 2013 (no mínimo, um pool de front-end ou um servidor Standard Edition), um servidor de borda e clientes Lync 2013 ou Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Processo de integração

A tabela a seguir fornece uma visão geral do processo de integração do Exchange UM hospedado. Para obter detalhes sobre etapas de implantação, consulte [fornecendo aos usuários do Lync Server 2013 a caixa postal no Exchange um hospedado](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) na documentação de implantação.


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
<th>Direitos e permissões</th>
<th>Documentação de Implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar o servidor de borda.</p></td>
<td><ol>
<li><p>Configure o Servidor de Borda para federação.</p></li>
<li><p>Replique manualmente os dados para o servidor de borda.</p></li>
<li><p>Configurar o provedor de hospedagem no servidor de borda.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar Servidor de Borda para integração com o Exchange UM hospedado</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar a política de caixa postal hospedada.</p></td>
<td><ol>
<li><p>Modifique a política de caixa de correio de voz hospedada global ou crie uma nova política de caixa postal hospedada com o site ou o escopo por usuário.</p></li>
<li><p>Para políticas com escopo por usuário, atribua a política a usuários ou grupos.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gerenciar políticas de caixa postal hospedada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilite os usuários para a caixa postal hospedada.</p></td>
<td><ul>
<li><p>Configure contas de usuário para os usuários cujas caixas de correio estão em um serviço hospedado do Exchange.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar usuários para correio de voz hospedado no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar objetos de contato hospedados.</p></td>
<td><ol>
<li><p>Crie objetos de contato do atendente automático para UM Exchange UM hospedado.</p></li>
<li><p>Crie objetos de contato do acesso do assinante para o Exchange UM hospedado.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Para criar, modificar ou remover objetos de contato, o usuário que executa o cmdlet New-CsExUmContact, Set-CsExUmContact ou remove-CsExUmContact deve ter a permissão correta para a unidade organizacional do Active Directory na qual os novos objetos de contato são armazenados. Esta permissão pode ser concedida executando-se o cmdlet Grant-CsOUPermission. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Criar objetos de contato para Exchange UM hospedado no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

