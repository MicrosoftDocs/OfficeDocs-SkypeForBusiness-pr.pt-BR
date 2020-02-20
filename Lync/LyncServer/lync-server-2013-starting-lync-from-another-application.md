---
title: 'Lync Server 2013: Iniciando o Lync de outro aplicativo'
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
ms.openlocfilehash: 75e7a48645301b6c822eed52ea31e6d4b46019bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Iniciando o Lync de outro aplicativo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Você pode usar os parâmetros de linha de comando para iniciar rapidamente o Lync 2013. Por exemplo, se um usuário clica em um número de telefone em outro aplicativo, o aplicativo pode iniciar uma instância do Lync 2013 e iniciar uma chamada para esse número.

O Lync 2013 também pode reconhecer uma lista delimitada por ponto-e-vírgula de nomes de contato para conferência de vários participantes.

Se o Lync 2013 estiver configurado para entrar automaticamente quando iniciado, a inicialização do Lync 2013 com os parâmetros de linha de comando abrirá a janela principal do Lync. Se o Lync não estiver configurado para entrar automaticamente quando for iniciado, a janela será aberta.

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
<th>Extensão</th>
<th>Formato de dados</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>tel URI</p></td>
<td><p>Abre a janela de conversação para uma chamada de áudio mas não disca o número especificado.</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>tel:, sip:, ou tel URI digitável</p></td>
<td><p>Abre a janela de conversação para uma chamada de áudio mas não disca o número especificado.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>URI do SIP</p></td>
<td><p>Abre a janela de conversação com o URI (Uniform Resource Identifier) do SIP na lista de participantes.</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>URI do SIP</p></td>
<td><p>Se o Lync 2013 estiver configurado para usar o protocolo TLS (Transport Layer Security), funcionará exatamente como SIP:. Se o TLS não estiver sendo usado, uma caixa de diálogo será exibida informando ao usuário que um nível maior de segurança é necessário.</p></td>
</tr>
<tr class="odd">
<td><p>fere</p></td>
<td><p>URI do SIP da conferência para ingresso</p></td>
<td><p>Quando o URI é self, ele cria uma instância do foco e exibe somente a lista de participantes. Caso contrário, ele exibe a lista de participantes, mas não envia INVITE.</p></td>
</tr>
<tr class="even">
<td><p>respectiva</p></td>
<td><p>URI do SIP</p></td>
<td><p>Exibe uma janela de conversação de somente mensagens instantâneas com o URI do SIP. Aceita vários URIs SIP especificados dentro de colchetes angulares (&lt;&gt;) sem nenhum separador.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


A tabela a seguir fornece exemplos destes parâmetros de linha de comando.

### <a name="command-line-parameter-examples"></a>Exemplos de parâmetros de linha de comando

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
<td><p>Abre uma exibição somente de telefone com +14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>Abre uma exibição somente de telefone com +14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Abre uma exibição somente de telefone com kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Abre uma janela de conversação com kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Abre uma janela de conversa e exibe opções de ingresso no áudio da reunião.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

