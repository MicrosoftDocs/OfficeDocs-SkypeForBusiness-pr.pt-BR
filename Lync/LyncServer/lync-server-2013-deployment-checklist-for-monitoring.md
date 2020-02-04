---
title: 'Lync Server 2013: Lista de verificação de implantação para monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lista de verificação de implantação para monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-05_

Embora o monitoramento já esteja instalado e ativado em cada servidor front-end, ainda há várias etapas que você deve realizar antes de realmente poder coletar dados de monitoramento do Microsoft Lync Server 2013. Essas etapas são descritas na seguinte lista de verificação:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Fase</p></td>
<td><p>Etapas</p></td>
<td><p>Associação de grupo e função</p></td>
<td><p>Documentação</p></td>
</tr>
<tr class="even">
<td><p><strong>Instalar os pré-requisitos de hardware e software</strong></p></td>
<td><p>Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados back-end do monitoramento.</p></td>
<td><p>Usuário do domínio que também é membro do grupo local de administradores.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> no guia de suporte</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> no guia de suporte</p></td>
</tr>
<tr class="odd">
<td><p><strong>Criar a topologia interna apropriada para dar suporte ao monitoramento</strong></p></td>
<td><p>Use o construtor de topologia do Lync Server 2013 para adicionar bancos de dados de monitoramento à topologia e, em seguida, publicar a topologia atualizada.</p></td>
<td><p>Para definir uma topologia, um usuário que seja membro do grupo Usuários local.</p>
<p>Para publicar a topologia, um usuário que seja membro do grupo Administradores de domínio e do grupo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associando um repositório de monitoramento a um pool de front-end no Lync Server 2013</a> no guia de implantação</p></td>
</tr>
<tr class="even">
<td><p><strong>Habilitar a configuração de monitoramento apropriada</strong></p></td>
<td><p>Habilite o monitoramento de registro de detalhes de chamadas (CDR) e/ou Quality of Experience (QoE) nos escopos global e/ou do site.</p></td>
<td><p>Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurando a gravação de detalhes da chamada e as configurações de qualidade de experiência no Lync Server 2013</a> no guia de operações</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

