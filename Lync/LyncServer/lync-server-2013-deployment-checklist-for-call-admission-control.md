---
title: 'Lync Server 2013: Lista de verificação de implantação para controle de admissão de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lista de verificação de implantação para controle de admissão de chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-08_

Para planejar efetivamente o controle de admissão de chamadas (CAC), você precisa considerar o seguinte:

  - Pré-requisitos para a implantação do CAC.

  - Informações necessárias para o CAC e decisões de configuração que você deve fazer antes da implantação.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Pré-requisitos de implantação para controle de admissão de chamadas

Antes de implantar o controle de admissão de chamadas, você já deve ter implantado seus servidores internos do Lync Server 2013, incluindo um pool de front-ends ou um servidor Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Requisitos de informações para controle de admissão de chamadas

A tabela a seguir resume as informações necessárias para implantar o controle de admissão de chamadas.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Requisitos de informações para a implantação do controle de admissão de chamadas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informações</th>
<th>Resumo das informações necessárias</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recursos do Lync Server exigidos pela sua organização</p></td>
<td><ul>
<li><p>Recursos a serem suportados pela sua organização</p></li>
<li><p>Recursos a serem habilitados para usuários individuais</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologias e componentes a serem implantados</p></td>
<td><ul>
<li><p>Os componentes relacionados ao CAC são instalados automaticamente como parte do Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos do sistema</p></td>
<td><ul>
<li><p>Requisitos de hardware</p></li>
<li><p>Requisitos de software</p></li>
<li><p>Requisitos de colocação</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Determinando seus requisitos de sistema para Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Requisitos de infraestrutura</p></td>
<td><ul>
<li><p>Nenhuma necessidade de infraestrutura específica é necessária para o CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestrutura para controle de admissão de chamada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos de interface de rede</p></td>
<td><ul>
<li><p>Informações de interface interna e externa</p></li>
<li><p>Informações de roteamento (incluindo informações sobre o blog NextHop <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>em, canal de resposta do cliente da equipe do Microsoft Lync Server)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Implantação de acesso do usuário externo no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Estratégia de implantação</p></td>
<td><ul>
<li><p>Sequência de implantação</p></li>
<li><p>Grupo de trabalho ou domínio</p></li>
<li><p>Segurança</p></li>
<li><p>Monitoramento e auditoria</p></li>
<li><p>Considerações de hardware</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Práticas recomendadas para controle de admissão de chamada no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Processo de implantação</p></td>
<td><ul>
<li><p>Pré-requisitos</p></li>
<li><p>Requisitos de informações</p></li>
<li><p>Processo e procedimentos</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Configurar o controle de admissão de chamadas no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

