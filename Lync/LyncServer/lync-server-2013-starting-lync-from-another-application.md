---
title: 'Lync Server 2013: Iniciando o Lync a partir de outro aplicativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Iniciando o Lync a partir de outro aplicativo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Você pode usar parâmetros de linha de comando para iniciar rapidamente o Lync 2013. Por exemplo, se um usuário clicar em um número de telefone em outro aplicativo, o aplicativo poderá iniciar uma instância do Lync 2013 e iniciar uma chamada para esse número.

O Lync 2013 também pode reconhecer uma lista delimitada por ponto-e-vírgula de nomes de contatos para conferência multiparte.

Se o Lync 2013 estiver configurado para entrar automaticamente quando iniciado, iniciar o Lync 2013 com parâmetros de linha de comando abrirá a janela principal do Lync. Se o Lync não estiver configurado para entrar automaticamente quando iniciado, a janela de entrada será aberta.

A tabela a seguir mostra os parâmetros disponíveis.

### <a name="lync-2013-command-line-parameters"></a>Parâmetros de linha de comando do Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Prorroga</th>
<th>Formato dos dados</th>
<th>Ação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>telefone</p></td>
<td><p>URI do Tel</p></td>
<td><p>Abre a janela de conversa para uma chamada de áudio, mas não disca o número especificado.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>Tel:, SIP: ou URI de Tel digitado</p></td>
<td><p>Abre a janela de conversa para uma chamada de áudio, mas não disca o número especificado.</p></td>
</tr>
<tr class="odd">
<td><p>SPI</p></td>
<td><p>URI do SIP</p></td>
<td><p>Abre a janela de conversa com o URI (Uniform Resource Identifier) SIP especificado na lista de participantes.</p></td>
</tr>
<tr class="even">
<td><p>SIPS</p></td>
<td><p>URI do SIP</p></td>
<td><p>Se o Lync 2013 estiver configurado para usar o protocolo TLS (Transport Layer Security), funciona exatamente como SIP:. Se o TLS não estiver sendo usado, exibe uma caixa de diálogo informando ao usuário que um nível mais alto de segurança é necessário.</p></td>
</tr>
<tr class="odd">
<td><p>Conferência</p></td>
<td><p>URI SIP da conferência para ingressar</p></td>
<td><p>Se URI for Self, instancia o foco e mostra o modo de exibição somente de lista. Caso contrário, exibe o modo de exibição de lista, mas não envia convite.</p></td>
</tr>
<tr class="even">
<td><p>comunicar</p></td>
<td><p>URI do SIP</p></td>
<td><p>Exibe uma janela de conversa somente de mensagens instantâneas (IM) com o URI SIP. Aceita vários URIs SIP especificados dentro dos colchetes angulares (&lt;&gt;) sem qualquer separador.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


A tabela a seguir fornece exemplos desses parâmetros de linha de comando.

### <a name="command-line-parameter-examples"></a>Exemplos de parâmetro de linha de comando

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instância</th>
<th>Resultados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Abre um modo de exibição somente telefone com + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto: Tel: + 14255550101</p></td>
<td><p>Abre um modo de exibição somente telefone com + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Abre uma exibição somente de telefone com o kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Abre uma janela de conversa com o kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Abre uma janela de conversa e exibe as opções de ingresso no áudio da reunião.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

