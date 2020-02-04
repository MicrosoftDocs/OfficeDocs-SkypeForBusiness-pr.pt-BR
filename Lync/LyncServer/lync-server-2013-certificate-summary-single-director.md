---
title: 'Lync Server 2013: Resumo do certificado - Diretor único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Resumo do certificado - Diretor único no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Os requisitos de certificado para um único diretor consistem em um certificado padrão que tem um nome de assunto e nomes alternativos de assunto para serviços que o diretor pode receber. Além disso, há um certificado de token OAuth para fins de autenticação do servidor para servidor.

### <a name="certificates-for-director"></a>Certificados para o diretor

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome da entidade (SN)</th>
<th>Nomes alternativos de entidades (SAN)</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcionalmente) *. contoso.com</p></td>
<td><p>Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma CA pública.</p>
<p>O diretor responde a solicitações do proxy reverso no perímetro ou do servidor de borda. Os clientes internos não usarão o diretor.</p>
<p>Ou uma entrada curinga para as URLs simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Sem entrada</p></td>
<td><div>

> [!IMPORTANT]  
> Observe que o tamanho mínimo da chave é 1024, mas você pode receber um aviso de que o tamanho mínimo recomendado da chave é 2048 bits.


</div>
<p>O certificado OAuthTokenIssuer é um certificado de finalidade única para a finalidade de autenticar servidores em um ambiente em larga escala e pode ser solicitado de uma CA interna ou de uma CA pública. O certificado é necessário.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

