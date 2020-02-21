---
title: 'Lync Server 2013: requisitos de certificado para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bd350a4b552d63b635f8ec5a25ed7803de4b55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Requisitos de certificado para servidores internos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-02-17_

Servidores internos que estão executando o Lync Server e que exigem certificados incluem servidor Standard Edition, servidor front-end Enterprise Edition, servidor de mediação e diretor. A tabela abaixo mostra os requisitos de certificado desses servidores. Você pode usar o assistente de certificado do Lync Server para solicitar esses certificados.

<div>


> [!TIP]  
> Os certificados curinga são compatíveis com os nomes alternativos de entidade associados às URLs simples no pool de front-ends, servidor front-end ou diretor. Para obter detalhes sobre o suporte a certificados curinga, consulte <A href="lync-server-2013-wildcard-certificate-support.md">suporte a certificados curinga no Lync Server 2013</A>.



</div>

Embora uma autoridade de certificação empresarial interna seja recomendada para servidores internos, você também pode usar uma autoridade de certificação pública. Para obter uma lista de autoridades de certificação públicas que oferecem certificados compatíveis com requisitos específicos para certificados de comunicações unificadas (UC) e que tenham parceria com a Microsoft para garantir que eles funcionem com o assistente de certificado do Lync Server, consulte o artigo Microsoft Knowledge Base 929395, "parceiros de certificado de [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)comunicações unificadas para o Exchange Server e o Communications Server" em.

A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos. Para a versão 2013, Lync Server 2013 e outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o SharePoint Server, dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor. Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou a documentação de operações.

Para conexões de clientes que executam o sistema operacional Windows 7, o sistema operacional Windows Server 2008, o sistema operacional Windows Server 2008 R2, o sistema operacional Windows Vista e o Microsoft Lync Phone Edition, Lync Server 2013 inclui suporte para (mas não require) certificados assinados usando a função de hash criptográfico SHA-256. Para suportar acesso externo usando SHA-256, o certificado externo é emitido por um AC público usando SHA-256.

As tabelas a seguir mostram os requisitos de certificado por função de servidor para pools de Front-Ends e servidores Standard Edition. Todos são certificados padrão de servidores da web com chave privada e não exportáveis.

Observe que o Uso Avançado de Chave (EKU) é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.

<div>


> [!NOTE]  
> Cada nome amigável do certificado deve ser exclusivo no repositório do computador.



</div>

<div>


> [!NOTE]  
> Se você tiver configurado o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, será necessário adicioná-los ao nome alternativo da entidade do certificado.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificados para o servidor Standard Edition

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
<th>Certificado</th>
<th>Nome da entidade/nome comum</th>
<th>Nome da entidade alternativo</th>
<th>Exemplo</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>Nome de domínio totalmente qualificado (FQDN) do pool</p></td>
<td><p>FQDN do pool e o FQDN do servidor</p>
<p>Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</p>
<p>Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</p></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com</p>
<p>Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>No servidor Standard Edition, o servidor FQDN é o mesmo que o pool FQDN.</p>
<p>O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</p>
<p>Você também pode usar esse certificado para autenticação de servidor para servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web interna</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN de web interna (que é o mesmo que o FQDN do servidor)</p></li>
<li><p>Atender a URLs simples</p></li>
<li><p>Discar URL simples</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou, uma entrada coringa para os URLs simples</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</p>
<p>Como usar um certificado curinga:</p>
<p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Não é possível substituir o FQDN interno da Web no construtor de topologias.</p>
<p>Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externa</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da web externa</p></li>
<li><p>Discar URL simples</p></li>
<li><p>Atender URLs simples por domínio SIP</p></li>
<li><p>Ou uma entrada curinga para os URLs simples</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</p>
<p>Como usar um certificado coringa:</p>
<p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificados de servidor Front-End eu um pool de Front-Ends

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
<th>Certificado</th>
<th>Nome da entidade/nome comum</th>
<th>Nome da entidade alternativo</th>
<th>Exemplo</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do pool</p></td>
<td><p>FQDN do pool e FQDN do servidor.</p>
<p>Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</p>
<p>Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do DNS é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</p></td>
<td><p>SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</p>
<p>Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</p>
<p>Você também pode usar esse certificado para autenticação de servidor para servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web interna</p></td>
<td><p>FQDN do pool</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da Web interna (que não é o mesmo que o FQDN do servidor)</p></li>
<li><p>FQDN do servidor</p></li>
<li><p>FQDN do pool do Lync</p></li>
<li><p>Atender a URLs simples</p></li>
<li><p>Discar URL simples</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou, uma entrada curinga para os URLs simples</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</p>
<p>Como usar um certificado curinga:</p>
<p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externa</p></td>
<td><p>FQDN do pool</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da web externa</p></li>
<li><p>Discar URL simples</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou, uma entrada curinga para os URLs simples</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</p>
<p>Como usar um certificado curinga:</p>
<p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificados do diretor

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nome da entidade/nome comum</th>
<th>Nome da entidade alternativo</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do pool de Diretores</p></td>
<td><p>FQDN do Diretor, FQDN do pool de Diretores</p>
<p>Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do DNS é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</p>
<p>Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
<tr class="even">
<td><p>Web interna</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN de web interna (que é o mesmo que o FQDN do servidor)</p></li>
<li><p>FQDN do servidor</p></li>
<li><p>FQDN do pool do Lync</p></li>
<li><p>Atender a URLs simples</p></li>
<li><p>Discar URL simples</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou, uma entrada curinga para os URLs simples</p></li>
</ul></td>
<td><p>SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = *. contoso. com</p></td>
</tr>
<tr class="odd">
<td><p>Web externa</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da web externa</p></li>
<li><p>Discar URL simples</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou, uma entrada curinga para os URLs simples</p></li>
</ul></td>
<td><p>O FQDN da Web externa do diretor deve ser diferente do pool de front-ends ou servidor front-end.</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = encontro. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = *. contoso. com</p></td>
</tr>
</tbody>
</table>


Se possuir um pool do Servidor de Mediação autônomo, os servidores presentes em cada um precisam dos certificados listados na tabela a seguir. Se um Servidor de Mediação for colocado junto aos Servidores Front-End, são suficientes os certificados listados na tabela “Certificados para Servidor Front-End no Pool do Front-End”, já apresentada neste tópico.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificados para um Servidor de Mediação Autônomo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nome da entidade/nome comum</th>
<th>Nome da entidade alternativo</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do pool</p></td>
<td><p>FQDN do pool</p>
<p>FQDN do servidor membro do pool</p></td>
<td><p>SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificados para Aparelho de Filial Persistente

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nome da entidade/nome comum</th>
<th>Nome da entidade alternativo</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do aplicativo</p></td>
<td><p>SIP. &lt;sipdomain&gt; (precisa de uma entrada por domínio SIP)</p></td>
<td><p>SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira também


[Suporte a certificados curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

