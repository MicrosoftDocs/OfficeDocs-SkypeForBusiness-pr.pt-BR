---
title: 'Lync Server 2013: configurações de negociação para parceiros federados XMPP'
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Configurações de negociação para parceiros federados XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

As configurações dos tipos de negociação na configuração de um parceiro do XMPP têm uma ampla variedade de combinações possíveis. Nem todas essas combinações são válidas. A tabela detalhada neste tópico definirá as configurações válidas e inválidas. As configurações comuns são apresentadas na primeira tabela, a segunda tabela detalhando todas as combinações possíveis. Observe que você não pode ter a *autenticação simples e a camada de segurança* (SASL) **, a menos** que *Transport Layer Security* (TLS) também esteja disponível. O SASL é enviado em um formato não criptografado (legível) e nunca deve ser transmitido, a menos que seja protegido por outro meio, como o TLS.

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
<th>TLS (Transport Layer Security)</th>
<th>Autenticação simples e camada de segurança (SASL)</th>
<th>Autenticação Dialback</th>
<th>Método (s) de autenticação esperado</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obrigatório</p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><p>O TLS e o SASL necessários ajudam a garantir que o fluxo de mensagens SASL seja seguro. Dialback não está disponível e não pode ser usado para um método fallback se o parceiro federado do XMPP não definiu o TLS como obrigatório ou opcional.</p></td>
</tr>
<tr class="even">
<td><p>Obrigatório</p></td>
<td><p>Opcional</p></td>
<td><p>True</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Ao exigir TLS, se o parceiro federado XMPP tiver definido SASL como opcional ou obrigatório, o SASL será usado. Se SASL não estiver disponível, o Dialback sobre TLS será usado.</p></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Opcional</p></td>
<td><p>True</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Embora muito flexível nos métodos de negociação oferecidos, essas configurações dependem das configurações do parceiro de Federação do XMPP. Se o parceiro tiver o TLS opcional ou necessário, mas o SASL não for suportado, o TLS Dialback estará disponível. Se o parceiro tiver TLS e SASL definido como Optional ou Required, a seleção ideal de TLS sobre o SASL será usada.</p></td>
</tr>
<tr class="even">
<td><p>Não Suportado</p></td>
<td><p>Não Suportado</p></td>
<td><p>True</p></td>
<td><p>TCP Dialback</p></td>
<td><p>Em muitos casos, o TCP Dialback é a única solução possível. Menos desejável que outras opções, ele fornece algum nível de confiança.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matriz de métodos de negociação de Federação XMPP-Complete

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
<th>TLS (Transport Layer Security)</th>
<th>Autenticação simples e camada de segurança (SASL)</th>
<th>Autenticação Dialback</th>
<th>Método de autenticação esperado</th>
<th>Observações, avisos ou erros de configuração não válida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obrigatório</p></td>
<td><p>Obrigatório</p></td>
<td><p>True</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> O Dialback não funcionará se ambos SASL e TLS forem necessários.


</div></td>
</tr>
<tr class="even">
<td><p>Obrigatório</p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Obrigatório</p></td>
<td><p>True</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="odd">
<td><p>Não suportado</p></td>
<td><p>Obrigatório</p></td>
<td><p>True</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Não suportado</p></td>
<td><p>Obrigatório</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> Não é uma configuração válida


</div></td>
<td><div>

> [!WARNING]  
> Como o SASL requer o TLS, e o TLS não está disponível, o SASL/TLS não pode ser bem-sucedido. TCP Dialback está definido como false e não pode ser usado.


</div></td>
</tr>
<tr class="odd">
<td><p>Obrigatório</p></td>
<td><p>Opcional</p></td>
<td><p>True</p></td>
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
<td><p>Opcional</p></td>
<td><p>Opcional</p></td>
<td><p>True</p></td>
<td><p>SASL sobre TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><p>SASL sobre TLS</p></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="odd">
<td><p>Não suportado</p></td>
<td><p>Opcional</p></td>
<td><p>True</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="even">
<td><p>Não suportado</p></td>
<td><p>Opcional</p></td>
<td><p>Falso</p></td>
<td><div>

> [!WARNING]  
> Não é uma configuração válida


</div></td>
<td><div>

> [!WARNING]  
> SASL exige o protocolo TLS. Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.


</div></td>
</tr>
<tr class="odd">
<td><p>Obrigatório</p></td>
<td><p>Não suportado</p></td>
<td><p>True</p></td>
<td><p>TLS Dialback</p></td>
<td><p>A configuração permite o TLS Dialback.</p></td>
</tr>
<tr class="even">
<td><p>Obrigatório</p></td>
<td><p>Não suportado</p></td>
<td><p>Falso</p></td>
<td><p>Não é uma configuração válida</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback deve estar habilitado.


</div></td>
</tr>
<tr class="odd">
<td><p>Opcional</p></td>
<td><p>Não suportado</p></td>
<td><p>True</p></td>
<td><p>TLS Dialback, TCP Dialback</p></td>
<td><p>Com base nas opções de negociação do outro ponto de extremidade, os Dialback TCP ou TLS serão aceitos.</p></td>
</tr>
<tr class="even">
<td><p>Opcional</p></td>
<td><p>Não suportado</p></td>
<td><p>Falso</p></td>
<td><p>Não é uma configuração válida</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback deve estar habilitado.


</div></td>
</tr>
<tr class="odd">
<td><p>Não Suportado</p></td>
<td><p>Não Suportado</p></td>
<td><p>True</p></td>
<td><p>TCP Dialback</p></td>
<td><p>O TCP Dialback é o único método de negociação disponível</p></td>
</tr>
<tr class="even">
<td><p>Não Suportado</p></td>
<td><p>Não Suportado</p></td>
<td><p>Falso</p></td>
<td><p>Não é uma configuração válida</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback deve estar habilitado.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

