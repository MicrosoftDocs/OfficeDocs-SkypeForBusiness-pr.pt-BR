---
title: 'Lync Server 2013: processo de implantação para integração do UM do Exchange hospedado'
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
ms.openlocfilehash: f55e8f573b4000d56a002adb9bd40d03b2021cba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Processo de implantação para integração do UM do Exchange hospedado com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-25_

O planejamento eficaz da integração do Lync Server 2013 com a Unificação de mensagens (UM) do Exchange hospedado exige que você leve em consideração o seguinte:

  - Pré-requisitos para a integração do Lync Server 2013 com o UM do Exchange hospedado

  - Etapas necessárias durante o processo de integração

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Pré-requisitos de implantação para a integração com UM do Exchange hospedada

Antes de começar o processo de integração, você já deve ter implantado o Lync Server 2013 (no mínimo, um pool de front-end ou um servidor Standard Edition), um servidor de borda e os clientes do Lync 2013 ou Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Processo de integração

A tabela a seguir fornece uma visão geral do processo de integração da UM do Exchange hospedada. Para obter detalhes sobre etapas de implantação, consulte [fornecer mensagens de voz do Lync Server 2013 Users no Hosted Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) na documentação de implantação.


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
<th>Documentação de implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuração do Servidor de Borda.</p></td>
<td><ol>
<li><p>Configure o Servidor de Borda para federação.</p></li>
<li><p>Replique manualmente os dados para o Servidor de Borda.</p></li>
<li><p>Configure um provedor de hospedagem no Servidor de Borda.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar o servidor de borda para integração com o UM do Exchange hospedado</a></p></td>
</tr>
<tr class="even">
<td><p>Configure a política de caixa postal hospedada.</p></td>
<td><ol>
<li><p>Modifique a política global de caixa postal hospedada ou crie uma nova política de caixa postal hospedada com escopo de Site ou Por usuário.</p></li>
<li><p>Para políticas com o escopo Por usuário, atribua a política aos usuários ou grupos.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gerenciar políticas de caixa postal hospedada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilite os usuários para caixa postal hospedada</p></td>
<td><ul>
<li><p>Configure contas de usuário para usuário cujas caixas postais estão em um serviço do Exchange hospedado.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar usuários para caixa postal hospedada no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure objetos de contato hospedados.</p></td>
<td><ol>
<li><p>Crie objetos de contato Atendedor Automático para UM do Exchange hospedada.</p></li>
<li><p>Crie objetos de contato Acesso do Assinante para UM do Exchange hospedada.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Para criar, modificar ou remover objetos de contato, o usuário que executa o cmdlet New-CsExUmContact, Set-CsExUmContact ou Remove-CsExUmContact precisa ter a permissão correta para a unidade organizacional Active Directory na qual os novos objetos de contato são armazenados. Essa permissão pode ser atribuída por meio da execução do cmdlet Grant-CsOUPermission. Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Criar objetos de contato para a UM do Exchange hospedado no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

