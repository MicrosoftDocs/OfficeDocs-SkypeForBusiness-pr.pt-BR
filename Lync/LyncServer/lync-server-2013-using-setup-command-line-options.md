---
title: 'Lync Server 2013: usando as opções de linha de comando de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Usando as opções de linha de comando de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

A linha de comando Setup.exe é usada em poucas operações na instalação do Office. Em vez de usar as opções da linha de comando Setup, você geralmente usa a Ferramenta de personalização do Office e o arquivo Config.xml file para instalação do produto e personalização de recursos.

A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.

### <a name="office-setup-command-line-options"></a>Opções de linha de comando Setup do Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção de linha de comando Setup</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [caminho]</p></td>
<td><p>Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.</p></td>
</tr>
<tr class="odd">
<td><p>/config [caminho]</p></td>
<td><p>Especifica o arquivo Config.xml que o Setup usa durante a instalação. Use a opção/config para especificar o arquivo config. xml personalizado para instalações do Lync 2013, por exemplo:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/Modify Lync</p></td>
<td><p>Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office. Por exemplo, você pode usar a opção/Modify para adicionar ou remover recursos do Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/Repair Lync</p></td>
<td><p>Executa a instalação a partir do computador do usuário para reparar o Lync.</p></td>
</tr>
<tr class="even">
<td><p>/Uninstall Lync</p></td>
<td><p>Executa a instalação para remover o Lync do computador do usuário.</p></td>
</tr>
</tbody>
</table>


Para obter detalhes sobre como usar as opções de linha de comando <http://go.microsoft.com/fwlink/p/?linkid=267515>de configuração, consulte.

</div>

<span> </span>

</div>

</div>

</div>

