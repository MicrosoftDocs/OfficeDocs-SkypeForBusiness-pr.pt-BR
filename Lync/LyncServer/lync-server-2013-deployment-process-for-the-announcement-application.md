---
title: 'Lync Server 2013: processo de implantação para o aplicativo de comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d38db71daed7a7946b62593a29f7f685c96c647
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526848"
---
# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Processo de implantação para o aplicativo de anúncio no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-12_

Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de comunicado. Você deve implantar o Enterprise Voice antes de configurar os comunicados. Os componentes exigidos pelo aplicativo de comunicado são instalados e habilitados quando você implanta o Enterprise Voice.

### <a name="announcement-deployment-process"></a>Processo de implantação do comunicado

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
<th>Funções</th>
<th>Documentação de Implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Definir configurações do comunicado</p></td>
<td><ul>
<li><p>Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS).</p></li>
<li><p>Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Criar um comunicado no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurar a tabela de números não atribuídos no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Verifique a implantação do comunicado</p></td>
<td><p>Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Opcion Verificar a implantação do comunicado no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

