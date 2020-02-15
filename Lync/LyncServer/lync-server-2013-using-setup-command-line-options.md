---
title: 'Lync Server 2013: usando opções de linha de comando da instalação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aacaa402b325fbefe13d70dea4f3e74af1d896cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Usando opções de linha de comando da instalação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

A linha de comando Setup. exe é usada para muito poucas operações na instalação do Office. Em vez de usar as opções de linha de comando da instalação, você geralmente usará a ferramenta de personalização do Office e o arquivo config. xml para a configuração do produto e a personalização de recursos.

A linha de comando Setup. exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.

### <a name="office-setup-command-line-options"></a>Opções de linha de comando da instalação do Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção de linha de comando de instalação</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Executa a Ferramenta de Personalização do Office para criar um arquivo de personalização da Instalação (arquivo .msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>Aplica o arquivo de personalização da Instalação específico para a instalação. É possível especificar um caminho de um arquivo de personalização específico (arquivo .msp) ou para a pasta na qual você armazena os arquivos de personalização.</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>Especifica o arquivo Config.xml que a Instalação usa durante a instalação. Use a opção/config para especificar o arquivo config. XML que você personalizou para instalações do Lync 2013, por exemplo:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/Modify Lync</p></td>
<td><p>Usado com um arquivo Config.xml modificado para executar a instalação no modo de manutenção e fazer alterações em uma instalação existente do Office. Por exemplo, você pode usar a opção/Modify para adicionar ou remover recursos do Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/Repair Lync</p></td>
<td><p>Executa a instalação do computador do usuário para reparar o Lync.</p></td>
</tr>
<tr class="even">
<td><p>/Uninstall Lync</p></td>
<td><p>Executa a instalação para remover o Lync do computador do usuário.</p></td>
</tr>
</tbody>
</table>


Para obter detalhes sobre como usar as opções de linha de comando <http://go.microsoft.com/fwlink/p/?linkid=267515>da instalação, consulte.

</div>

<span> </span>

</div>

</div>

</div>

