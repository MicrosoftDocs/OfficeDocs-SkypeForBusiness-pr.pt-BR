---
title: 'Lync Server 2013: lista de verificação de implantação para monitoramento'
description: 'Lync Server 2013: lista de verificação de implantação para monitoramento.'
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
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568317"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lista de verificação de implantação para monitoramento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

Embora o monitoramento já esteja instalado e ativado em cada servidor de front-end, ainda há várias etapas que você deve realizar antes de realmente coletar dados de monitoramento do Microsoft Lync Server 2013. Essas etapas são descritas na seguinte lista de verificação:


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
<td><p><strong>Instale o pré-requisito de hardware e software</strong></p></td>
<td><p>Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados backend do monitoramento.</p></td>
<td><p>Usuário do domínio que também é membro do grupo local de administradores.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> no guia de suporte</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> no guia de suporte</p></td>
</tr>
<tr class="odd">
<td><p><strong>Criar a topologia interna apropriada para dar suporte ao monitoramento</strong></p></td>
<td><p>Use o construtor de topologias do Lync Server 2013 para adicionar bancos de dados de monitoramento à topologia e, em seguida, publique a topologia atualizada.</p></td>
<td><p>Para definir uma topologia, um usuário que seja membro do grupo local de usuários.</p>
<p>Para publicar a topologia, um usuário que seja membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associando um repositório de monitoramento a um pool de front-ends no Lync Server 2013</a> no guia de implantação</p></td>
</tr>
<tr class="even">
<td><p><strong>Habilitar a configuração de monitoramento apropriada</strong></p></td>
<td><p>Habilitar registro de detalhes das chamadas (CDR) e/ou o monitoramento da Qualidade da Experiência (QoE) no escopo global e/ou do site.</p></td>
<td><p>Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration .</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurando a gravação de detalhes da chamada e as configurações de qualidade da experiência no Lync Server 2013</a> no guia de operações</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

