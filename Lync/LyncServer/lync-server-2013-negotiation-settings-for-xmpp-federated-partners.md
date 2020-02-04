---
title: 'Lync Server 2013: Configurações de negociação para parceiros de XMPP federados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Configurações de negociação para parceiros de XMPP federados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

As configurações dos tipos de negociação na configuração de um parceiro do XMPP têm uma ampla variedade de combinações possíveis. Nem todas essas combinações são válidas. A tabela detalhada neste tópico definirá as configurações válidas e inválidas. As configurações comuns são apresentadas na primeira tabela, a segunda tabela que detalha todas as combinações possíveis. Observe que você não pode ter a *autenticação simples e a camada de segurança* (SASL) **, a menos** que o TLS ( *Transport Layer Security* ) também esteja disponível. SASL é enviada em um formato não criptografado (legível) e nunca deve ser transmitida, a menos que seja protegida por outro meio, como TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Métodos comuns de negociação de Federação XMPP

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport Layer Security (TLS)</th>
<th>Camada de segurança e autenticação simples (SASL)</th>
<th>Autenticação Dialback</th>
<th>Método (s) de autenticação esperado (s)</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obrigatório </p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><p>O TLS e o SASL são necessários ajuda a garantir que o fluxo de mensagens SASL seja seguro. Dialback não está disponível e não pode ser usado para um método de fallback se o parceiro federado do XMPP não definiu o TLS como obrigatório ou opcional.</p></td>
</tr>
<tr class="even">
<td><p>Obrigatório</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadeiro</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Ao exigir TLS, se o parceiro federado do XMPP tiver sido definido SASL para opcional ou obrigatório, o SASL será usado. Se SASL não estiver disponível, o Dialback em TLS será usado.</p></td>
</tr>
<tr class="odd">
<td><p>Opcional </p></td>
<td><p>Opcional</p></td>
<td><p>Verdadeiro</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Embora seja bastante flexível nos métodos de negociação oferecidos, essas configurações dependem das configurações do parceiro de Federação do XMPP. Se o parceiro tiver o TLS opcional ou obrigatório, mas o SASL não for compatível, o TLS Dialback estará disponível. Se o parceiro tiver TLS e SASL definido como opcional ou obrigatório, a seleção ideal de TLS sobre o SASL será usada.</p></td>
</tr>
<tr class="even">
<td><p>Sem suporte</p></td>
<td><p>Sem suporte</p></td>
<td><p>Verdadeiro</p></td>
<td><p>TCP Dialback</p></td>
<td><p>Em muitos casos, o TCP Dialback é a única solução possível. Menos desejável do que outras opções, ele fornece um certo nível de confiança.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matriz de métodos de negociação de Federação XMPP-concluída

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport Layer Security (TLS)</th>
<th>Camada de segurança e autenticação simples (SASL)</th>
<th>Autenticação Dialback</th>
<th>Método de autenticação esperado</th>
<th>Observações, aviso ou erro para uma configuração inválida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obrigatório </p></td>
<td><p>Obrigatório</p></td>
<td><p>Verdadeiro</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> O Dialback não funcionará se o SASL e o TLS forem obrigatórios.


</div></td>
</tr>
<tr class="even">
<td><p>Obrigatório </p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Obrigatório</p></td>
<td><p>Verdadeiro</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="odd">
<td><p>Sem suporte</p></td>
<td><p>Obrigatório</p></td>
<td><p>Verdadeiro</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Sem suporte</p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> Configuração inválida


</div></td>
<td><div>

> [!WARNING]  
> Como a SASL requer TLS, e o TLS não está disponível, o SASL/TLS não pode ser bem-sucedido. TCP Dialback é definido como false e não pode ser usado.


</div></td>
</tr>
<tr class="odd">
<td><p>Obrigatório</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadeiro</p></td>
<td><p>SASL sobre TLS, TLS Dialback</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Obrigatório</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Opcional </p></td>
<td><p>Opcional</p></td>
<td><p>Verdadeiro</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional </p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="odd">
<td><p>Sem suporte</p></td>
<td><p>Opcional</p></td>
<td><p>Verdadeiro</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Sem suporte</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> Configuração inválida


</div></td>
<td><div>

> [!WARNING]  
> SASL requer TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="odd">
<td><p>Obrigatório</p></td>
<td><p>Sem suporte</p></td>
<td><p>Verdadeiro</p></td>
<td><p>TLS Dialback</p></td>
<td><p>A configuração permite o TLS Dialback.</p></td>
</tr>
<tr class="even">
<td><p>Obrigatório</p></td>
<td><p>Sem suporte</p></td>
<td><p>Falso</p></td>
<td><p>Configuração inválida</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback devem ser habilitados.


</div></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Sem suporte</p></td>
<td><p>Verdadeiro</p></td>
<td><p>TLS Dialback, TCP Dialback</p></td>
<td><p>Com base nas opções de negociação do outro ponto de extremidade, o TCP ou o TLS Dialback será aceito.</p></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Sem suporte</p></td>
<td><p>Falso</p></td>
<td><p>Configuração inválida</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback devem ser habilitados.


</div></td>
</tr>
<tr class="odd">
<td><p>Sem suporte</p></td>
<td><p>Sem suporte</p></td>
<td><p>Verdadeiro</p></td>
<td><p>TCP Dialback</p></td>
<td><p>O TCP Dialback é o único método de negociação disponível</p></td>
</tr>
<tr class="even">
<td><p>Sem suporte</p></td>
<td><p>Sem suporte</p></td>
<td><p>Falso</p></td>
<td><p>Configuração inválida</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback devem ser habilitados.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

