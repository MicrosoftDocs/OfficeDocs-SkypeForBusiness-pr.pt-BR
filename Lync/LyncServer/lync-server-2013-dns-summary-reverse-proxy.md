---
title: 'Lync Server 2013: Resumo de DNS - Proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Resumo de DNS - Proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-22_

Você configura dois adaptadores de rede no seu proxy reverso da seguinte maneira:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Requisitos do adaptador de rede proxy reverso

  - Exemplo **de adaptador de rede 1 (interface interna)**
    
    Interface interna com 172.25.33.40 atribuído.
    
    Não há nenhum gateway padrão definido.
    
    Verifique se há uma rota da rede que contém a interface interna de proxy inverso para qualquer rede que contenha servidores de pool de front-end do Lync Server (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - Exemplo **de adaptador de rede 2 (interface externa)**
    
    Um mínimo de um endereço IP público é atribuído a esse adaptador de rede.
    
    O gateway é definido para apontar para o roteador ou o firewall integrado em seu perímetro externo. (10.45.16.1 nos exemplos de cenário)

### <a name="dns-records-required-for-reverse-proxy"></a>Registros DNS necessários para proxy reverso

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>FQDN</th>
<th>Endereço IP</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Ouvinte atribuído para recursos publicados externamente</p></td>
<td><p>Serviços Web externos da implantação interna. Registros adicionais podem ser definidos e criados para todos os pools e servidores individuais para qualquer domínio SIP que usará esse proxy reverso e definido serviços Web externos.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Ouvinte atribuído para recursos publicados externamente</p></td>
<td><p>Serviços Web externos para os directors ou pools de directors na sua implantação. Você pode definir tantos diretores quantos são diferentes diretores, que podem estar associados a outros domínios SIP.</p>
<div>

> [!IMPORTANT]  
> A definição dos registros de DNS para e a publicação dos directors não é o pool de front-end ou a decisão do diretor. Você deve definir e publicar os serviços Web externos do diretor e do pool de front-end se estiver usando directors. Tipos de tráfego específicos (para autenticação e outros usos) serão enviados ao diretor primeiro, se ele for definido na topologia.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Ouvinte atribuído para recursos publicados externamente</p></td>
<td><p>Conferência discada publicada externamente</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Ouvinte atribuído para recursos publicados externamente</p></td>
<td><p>Conferências publicadas externamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Escuta atribuído para o servidor do Office Web Apps</p></td>
<td><p>Office Web Apps Server implantado internamente ou no perímetro e publicado para acesso de cliente externo</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Ouvinte atribuído para recursos publicados externamente</p></td>
<td><p>O Lync descobriu registro externo para descoberta automática publicada externamente e inclui mobilidade, Microsoft Lync Web App e Agendador Web App</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

