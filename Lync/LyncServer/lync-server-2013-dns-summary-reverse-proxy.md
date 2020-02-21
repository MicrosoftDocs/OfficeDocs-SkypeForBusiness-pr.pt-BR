---
title: 'Lync Server 2013: Resumo de DNS-proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5f79437c5253365e4333e7cd064883bba968a54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Resumo de DNS-proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-22_

Você configura dois adaptadores de rede em seu proxy reverso como a seguir:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Requisitos do Adaptador de Rede do Proxy Reverso

  - Exemplo do **Adaptador de rede 1 (interface interna)**
    
    Interface interna com 172.25.33.40 atribuído.
    
    Nenhum gateway padrão é definido.
    
    Verifique se há uma rota da rede que contém a interface interna do proxy reverso para qualquer rede que contenha servidores de pool Front-end do Lync Server (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - Exemplo do **Adaptador de rede 2 (interface externa)**
    
    Um mínimo de um endereço IP público é atribuído a este adaptador de rede.
    
    O gateway é definido para o ponto do roteador ou firewall integrado em seu perímetro externo. (10.45.16.1 nos exemplos de cenário)

### <a name="dns-records-required-for-reverse-proxy"></a>Registros DNS necessários para proxy inverso

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
<th>Mapear para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A Externo</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Ouvidor atribuído para recursos publicados externamente</p></td>
<td><p>Serviços da Web externos da implantação interna. Registros adicionais podem ser definidos e criados para todos os pools e servidores únicos para qualquer domínio SIP que usará este proxy reverso e tenha os serviços da Web externos definidos.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Ouvidor atribuído para recursos publicados externamente</p></td>
<td><p>Serviços Web externos para os diretores ou pools de diretor em sua implantação. Você pode definir quantos directors forem diferentes de diretores, dos quais podem ser associados a outros domínios SIP.</p>
<div>

> [!IMPORTANT]  
> A definição dos registros DNS para e publicação dos diretores não é um pool de front-ends ou a decisão diretor. Você deve definir e publicar os serviços Web externos do diretor e do pool de front-end, se estiver usando diretores. Os tipos específicos de tráfego (para autenticação e outros usos) serão enviados para o diretor primeiro, se for definido na topologia.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Ouvidor atribuído para recursos publicados externamente</p></td>
<td><p>Conferência discada publicada externamente</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Ouvidor atribuído para recursos publicados externamente</p></td>
<td><p>Conferências publicadas externamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Ouvinte atribuído para o servidor do Office Web Apps</p></td>
<td><p>Servidor do Office Web Apps implantado internamente ou no perímetro e publicado para acesso de cliente externo</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Ouvidor atribuído para recursos publicados externamente</p></td>
<td><p>Registro externo de descoberta do Lync para descoberta automática publicada externamente e inclui mobilidade, Microsoft Lync Web App e Agendador Web App</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

