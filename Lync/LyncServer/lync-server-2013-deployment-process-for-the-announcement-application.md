---
title: 'Lync Server 2013: processo de implantação para o aplicativo de anúncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2b1e9f8dd78b299a8e89e958f5b1c03acdffb7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Processo de implantação do aplicativo de anúncio no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de anúncio. Você deve implantar o Enterprise Voice antes de configurar comunicados. Os componentes exigidos pelo aplicativo de anúncio são instalados e habilitados durante a implantação do Enterprise Voice.

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
<th>Documentação de implantação</th>
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
<td><p><a href="lync-server-2013-create-an-announcement.md">Criar um anúncio no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurar a tabela de número não atribuído no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Verifique a implantação do comunicado</p></td>
<td><p>Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Adicionais Verificar a implantação do lançamento no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

