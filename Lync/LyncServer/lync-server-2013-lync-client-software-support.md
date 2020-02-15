---
title: 'Lync Server 2013: suporte ao software cliente do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client software support
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412781(v=OCS.15)
ms:contentKeyID: 48184994
ms.date: 02/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 913a484262d9e1b3a899aeda42c5f23049d8c73c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-software-support-in-lync-server-2013"></a>Suporte a software de cliente do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-02-25_

Esta seção resume o suporte de software para Lync 2013 e o suplemento de reunião online para Lync 2013.

<div>


> [!NOTE]  
> O suplemento de reunião online do Lync 2013, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Lync 2013.



</div>

### <a name="software-requirements-for-lync-2013-and-the-online-meeting-add-in-for-lync-2013"></a>Requisitos de software para o Lync 2013 e o suplemento de reunião online para Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente do sistema</th>
<th>Requisito mínimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sistema operacional Windows</p></td>
<td><p>Windows 10</p>
<p>Windows 8.1</p>
<p>Windows 8</p>
<p>Sistema operacional Windows 7</p>
<p>Windows Server 2008 R2 com o Service Pack mais recente</p>
<div>

> [!NOTE]  
> O Lync 2013 e o suplemento online Meeting para Lync 2013 não têm suporte no Windows Vista ou Windows XP (qualquer versão).


</div></td>
</tr>
<tr class="even">
<td><p>Instalação e atualizações</p></td>
<td><p>Direitos e permissões de administrador</p></td>
</tr>
<tr class="odd">
<td><p>Navegador</p></td>
<td><p>Navegador Internet Explorer 11</p>
<p>Navegador Internet Explorer 10</p>
<p>Navegador Internet Explorer 9</p>
<p>Navegador Internet Explorer 8</p>
<p>Navegador Internet Explorer 7</p>
<p>Navegador da Web Mozilla Firefox</p>
<div>

> [!NOTE]  
> Se você estiver usando o Lync com o Microsoft Exchange Online e sua organização tiver implantado um proxy HTTP de autenticação, o Internet Explorer 9 ou o Internet Explorer 8 serão necessários.


</div></td>
</tr>
<tr class="even">
<td><p>Integração com o Microsoft Office</p></td>
<td><p>Para o conjunto completo de recursos de integração:</p>
<ul>
<li><p>Cliente de mensagens e colaboração do Outlook 2013</p></li>
<li><p>Cliente de mensagens e colaboração do Outlook 2010</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Integração com o Microsoft Exchange</p></td>
<td><p>Para o conjunto completo de recursos de integração:</p>
<ul>
<li><p>Microsoft Exchange Server 2013</p></li>
<li><p>Microsoft Exchange Server 2010</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>

## <a name="macintosh-operating-systems"></a>Sistemas operacionais Macintosh

O Lync 2013 está disponível somente para Windows. No entanto, o Lync Server 2013 oferece suporte aos seguintes clientes em computadores que executam o Mac OS 10.5.8 ou o Service Pack ou versão mais recente (baseado em Intel) sistemas operacionais (o sistema operacional Mac OS 10,9 não tem suporte no momento). Para obter detalhes sobre os recursos suportados, consulte [Client Comparison Tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync para Mac 2011 (consulte "Lync for Mac 2011 Deployment Guide" em [http://go.microsoft.com/fwlink/p/?LinkId=268786](http://go.microsoft.com/fwlink/p/?linkid=268786))

  - Microsoft Communicator para Mac 2011 (consulte "guia de implantação do Communicator for Mac 2011 [http://go.microsoft.com/fwlink/p/?LinkId=268787](http://go.microsoft.com/fwlink/p/?linkid=268787)" em)

</div>

<div>

## <a name="lync-web-app-browsers"></a>Navegadores do Lync Web App

O Lync Web App oferece suporte a combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, consulte [Lync Web App supported platforms for Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) na documentação de planejamento.

</div>

<div>

## <a name="microsoft-office-supportability"></a>Ajuste de Suporte do Microsoft Office

Os clientes do Lync Server 2013 oferecem suporte à integração com várias versões do Microsoft Office, conforme resumido nesta seção.

  - Os recursos de integração do Lync 2013 têm suporte no Outlook 2013 e no Microsoft Outlook 2010.

  - Os recursos de integração do Lync 2013 têm suporte no Microsoft Exchange Server 2013 e no Microsoft Exchange Server 2010.

  - O suplemento de reunião online para o Lync 2013 é compatível com o Office 2013 e o Microsoft Office 2010.

</div>

<div>

## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se os usuários planejam usar os recursos de conferência do Lync 2013, eles não devem usar os perfis obrigatórios dos serviços de domínio do Active Directory para entrar no cliente do Lync 2013. Como os perfis obrigatórios são perfis de usuário somente leitura, as chaves PKI (infraestrutura de chave pública) necessárias para a conferência do Lync 2013 não podem ser salvas no perfil. Para obter detalhes, consulte o artigo 2552221 da base de dados de conhecimento da Microsoft, "o recurso de conferência do Lync 2010 falha quando o usuário está [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2552221](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2552221)conectado usando um perfil de usuário obrigatório" em.

</div>

<div>

## <a name="see-also"></a>Confira também


[Suporte a hardware de cliente do Lync no Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Requisitos de vídeo do cliente Lync para Lync Server 2013](lync-server-2013-lync-client-video-requirements.md)  
[Clientes com suporte de implantações anteriores no Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

