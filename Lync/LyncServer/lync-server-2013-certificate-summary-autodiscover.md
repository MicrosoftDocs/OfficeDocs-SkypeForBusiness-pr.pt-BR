---
title: 'Lync Server 2013: Resumo de certificado-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196b3dacec792097a4760ef134ead91f267a53d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499308"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Resumo de certificado-descoberta automática no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-14_

O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends e, quando publicado no DNS, pode ser usado por clientes do Lync para localizar serviços de servidor e usuário. Se você estiver atualizando do Lync Server 2010 e não tiver implantado a mobilidade, antes que os clientes possam usar a descoberta automática, você deve modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática. Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.

A decisão sobre a utilização de listas de nomes alternativos de entidades em proxies reversos baseia-se no fato de você publicar o serviço de descoberta automática na porta 80 ou na porta 443:

  - **Publicado na porta 80**     Nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer na porta 80. Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão ligados ao diretor ou servidor front-end na porta 8080 internamente. Para obter detalhes, consulte a seção sobre requisitos técnicos de "processo de descoberta automática inicial usando a porta 80" [para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publicado na porta 443**     A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um *lyncdiscover. \<sipdomain\> * entrada para cada domínio SIP em sua organização.
    
    <div>
    

    > [!IMPORTANT]  
    > É altamente recomendável usar HTTPS sobre HTTP. HTTPS usa certificados para criptografar o tráfego. HTTP não fornece criptografia e todos os dados enviados serão texto sem formatação.

    
    </div>

A reemissão de certificados usando uma autoridade de certificação interna geralmente é um processo simples. Mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nome alternativo de entidade pode se tornar caro. Para contornar esse problema, oferecemos suporte à conexão de descoberta automática inicial na porta 80, que é então redirecionada para a porta 8080 no diretor ou servidor front-end.

<div>


> [!NOTE]  
> Se sua infraestrutura do Lync Server 2013 usa certificados internos emitidos por uma autoridade de certificação interna (CA) e você planeja suportar dispositivos móveis que se conectam sem fio, a cadeia de certificados raiz da autoridade de certificação interna deve ser instalada nos dispositivos móveis ou você deve alterar para um certificado público em sua infraestrutura do Lync Server 2013.



</div>

Este tópico descreve os nomes alternativos de entidade adicionados necessários para o diretor, servidor front-end e proxy reverso. Somente os nomes alternativos da entidade (SAN) adicionados são referenciados. Consulte as seções de planejamento para obter orientação sobre as outras entradas de certificados. Para obter detalhes, consulte [cenários para o diretor no Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [cenários de proxy reverso no Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

As tabelas a seguir definem as entradas de SAN de descoberta automática para o pool de diretores, o pool de front-ends e o proxy reverso:

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificado do Pool de Diretores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome de entidade alternativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt; nome de domínio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL externa do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui o certificado recentemente atualizado à nova entrada de SAN ao certificado padrão. Como alternativa, você pode usar SAN = *. &lt; sipdomain &gt; .



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos de certificado do pool Front-End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome de entidade alternativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt; nome de domínio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL externa do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui o certificado recentemente atualizado à nova entrada de SAN ao certificado padrão. Como alternativa, você pode usar SAN = *. &lt; sipdomain&gt;



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
<th>Entrada de nome de entidade alternativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL externa do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui o certificado recentemente atualizado à nova entrada de SAN ao ouvinte SSL no proxy reverso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

