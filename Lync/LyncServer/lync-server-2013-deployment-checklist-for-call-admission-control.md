---
title: 'Lync Server 2013: lista de verificação de implantação para controle de admissão de chamadas'
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
ms.openlocfilehash: 13d9591ad8dfed90373fedc8adfb3a3c3c44eb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529138"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lista de verificação de implantação para controle de admissão de chamada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-08_

Para planejar efetivamente o controle de admissão de chamadas (CAC), você deve levar em consideração o seguinte:

  - Pré-requisitos para implantação do CAC.

  - Informações necessárias para decisões de CAC e de configuração que você deve tomar antes de começar a implantação

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Pré-requisitos de implantação do controle de admissão de chamada

Antes de implantar o controle de admissão de chamadas, você já deve ter implantado seus servidores internos do Lync Server 2013, incluindo um pool de front-ends ou um servidor Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Requisitos de informações para o controle de admissão de chamada

A tabela a seguir resume as informações exigidas para implantar o controle de admissão de chamada.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Requisitos de informações para a implantação do controle de admissão de chamada

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
<li><p>Recursos a ser suportados pela organização</p></li>
<li><p>Recursos a ser ativados para os usuários individuais</p></li>
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
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Determinando os requisitos do sistema para o Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Requisitos de infra-estrutura</p></td>
<td><ul>
<li><p>Nenhum requisito de infraestrutura específica é necessário para CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestrutura para controle de admissão de chamadas no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos de interface de rede</p></td>
<td><ul>
<li><p>Informações sobre as interfaces interna e externa</p></li>
<li><p>Informações de roteamento (incluindo informações sobre o blog do NextHop em <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> , canal de resposta do cliente da equipe do Microsoft Lync Server)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Implantando o acesso de usuário externo no Lync Server 2013</a></p></td>
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
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Práticas recomendadas para controle de admissão de chamadas no Lync Server 2013</a></p></td>
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

