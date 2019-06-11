---
title: 'Lync Server 2013: Resumo do certificado-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c3777f9b13dc18e3e52e80120009f93c20db3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Resumo do certificado-descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-14_

O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-end e, quando publicados no DNS, pode ser usado pelos clientes do Lync para localizar serviços de servidor e usuário. Se você estiver atualizando do Lync Server 2010 e não implantou a mobilidade, antes que os clientes possam usar a descoberta automática, você deve modificar listas de nomes alternativos de entidades de certificado em qualquer director e servidor front-end executando o serviço descoberta automática. Além disso, pode ser necessário modificar as listas de nomes alternativos de entidades nos certificados usados para regras de publicação de serviço Web externo em proxies reverso.

A decisão sobre se deve usar listas de nomes alternativos de entidades em proxies invertidos se baseia se você publica o serviço de descoberta automática na porta 80 ou na porta 443:

  - **Publicado na porta 80**   nenhuma alteração de certificado será necessária se a consulta inicial para o serviço descoberta automática ocorrer na porta 80. Isso ocorre porque os dispositivos móveis que executam o Lync acessam o proxy reverso na porta 80 externamente e, em seguida, ligados a um diretor ou servidor front-end na porta 8080 internamente. Para obter detalhes, consulte a seção requisitos técnicos da seção "processo de descoberta automática inicial usando a porta 80" [para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publicado na porta 443**   a lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos deve conter um *lyncdiscover.\< entrada\> sipdomain* para cada domínio SIP em sua organização.
    
    <div>
    

    > [!IMPORTANT]  
    > É altamente recomendável usar HTTPS sobre HTTP. HTTPS usa certificados para criptografar o tráfego. O HTTP não fornece criptografia, e todos os dados enviados serão texto sem formatação.

    
    </div>

A emissão de certificados por meio de uma autoridade de certificação interna geralmente é um processo simples. Mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nomes alternativos de entidades pode ficar caro. Para contornar esse problema, oferecemos suporte para a conexão de descoberta automática inicial na porta 80, que é redirecionada para a porta 8080 do diretor ou servidor front-end.

<div>


> [!NOTE]  
> Se a sua infraestrutura do Lync Server 2013 usa certificados internos que são emitidos de uma CA (autoridade de certificação) interna e você planeja dar suporte a dispositivos móveis que se conectam sem fio, a cadeia de certificados raiz da autoridade de certificação interna deve ser instalada nos dispositivos móveis ou você deve mudar para um certificado público na sua infraestrutura do Lync Server 2013.



</div>

Este tópico descreve os nomes alternativos de entidades adicionados necessários para o diretor, servidor front-end e proxy reverso. Somente os nomes alternativos de entidades (SAN) adicionados são referenciados. Consulte as seções de planejamento para obter diretrizes sobre as outras entradas em certificados. Para obter detalhes, consulte [cenários do diretor do Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [cenários para o proxy inverso no Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

As tabelas a seguir definem as entradas de SAN de descoberta automática para o pool de diretor, o pool de front-ends e o proxy reverso:

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificado do pool do director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome alternativo do assunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de descoberta automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;nome de domínio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui o certificado recém atualizado com a nova entrada de SAN ao certificado padrão. Você também pode usar SAN = *. &lt;sipdomain&gt;.



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos de certificado de pool de front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome alternativo do assunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de descoberta automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;nome de domínio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui o certificado recém atualizado com a nova entrada de SAN ao certificado padrão. Você também pode usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisitos de certificado de proxy reverso (CA pública)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome alternativo do assunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui o certificado recém atualizado à nova entrada de SAN ao ouvinte SSL no proxy reverso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

