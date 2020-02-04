---
title: 'Lync Server 2013: Requisitos de certificado para servidores internos'
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
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Requisitos de certificado para servidores internos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-02-17_

Os servidores internos que executam o Lync Server e que exigem certificados incluem o servidor Standard Edition, o servidor front-end do Enterprise Edition, o servidor de mediação e o diretor. A tabela a seguir mostra os requisitos de certificado para esses servidores. Você pode usar o assistente de certificado do Lync Server para solicitar esses certificados.

<div>


> [!TIP]  
> Os certificados curinga são compatíveis com os nomes alternativos de assunto associados às URLs simples no pool de front-end, servidor front-end ou diretor. Para obter detalhes sobre o suporte a certificados curinga, consulte <A href="lync-server-2013-wildcard-certificate-support.md">suporte a certificados curinga no Lync Server 2013</A>.



</div>

Embora uma CA (autoridade de certificação) corporativa interna seja recomendada para servidores internos, você também pode usar uma CA pública. Para obter uma lista de CAs públicas que fornecem certificados compatíveis com requisitos específicos para certificados de comunicação unificada (UC) e que se associaram à Microsoft para garantir que elas funcionem com o assistente de certificado do Lync Server, consulte o artigo Microsoft Knowledge Base 929395, "parceiros de certificado de comunicação unificada para Exchange Server e para comunicações Server" em [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).

A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos. Para o lançamento do 2013, Lync Server 2013 e outros produtos do Microsoft Server, incluindo Exchange 2013 e SharePoint Server, suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização do servidor para servidor. Para obter detalhes, consulte [Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou na documentação de operações.

Para conexões de clientes que executam o sistema operacional Windows 7, sistema operacional Windows Server 2008, sistema operacional Windows Server 2008 R2, sistema operacional Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 inclui suporte para (mas não Requires) certificados assinados usando a função hash criptográfico SHA-256. Para dar suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma autoridade de certificação pública que usa SHA-256.

As tabelas a seguir mostram os requisitos de certificado por função de servidor para os pools front-end e os servidores Standard Edition. Todos esses são certificados de servidor Web padrão, chave privada, não-exportável.

Observe que o uso avançado de chave do servidor (EKU) é automaticamente configurado quando você usa o assistente de certificado para solicitar certificados.

<div>


> [!NOTE]  
> Cada nome amigável do certificado deve ser exclusivo na loja do computador.



</div>

<div>


> [!NOTE]  
> Se você tiver configurado o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, será necessário adicioná-los ao nome alternativo do requerente do certificado.



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
<th>Nome do assunto/nome comum</th>
<th>Nome alternativo de entidade</th>
<th>Exemplo</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN (nome de domínio totalmente qualificado) do pool</p></td>
<td><p>FQDN do pool e do FQDN do servidor</p>
<p>Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</p>
<p>Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>No servidor Standard Edition, o FQDN do servidor é o mesmo que o FQDN do pool.</p>
<p>O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</p>
<p>Você também utiliza este certificado para Autenticação de Servidor para Servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web interna</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN de web interna (que é o mesmo que o FQDN do servidor)</p></li>
<li><p>Atender a URLs simples</p></li>
<li><p>URL simples de discagem</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou uma entrada curinga para as URLs simples</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Como usar um certificado curinga:</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Não é possível substituir o FQDN da Web interna no construtor de topologias.</p>
<p>Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externa</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da web externa</p></li>
<li><p>URL simples de discagem</p></li>
<li><p>Encontre URLs simples por domínio SIP</p></li>
<li><p>Ou uma entrada curinga para as URLs simples</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Como usar um certificado curinga:</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificados do servidor front-end em um pool de front-ends

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
<th>Nome do assunto/nome comum</th>
<th>Nome alternativo de entidade</th>
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
<p>Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </p>
<p>Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</p>
<p>Você também utiliza este certificado para Autenticação de Servidor para Servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web Internal</p></td>
<td><p>FQDN do pool</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da Web interna (que NÃO é igual ao FQDN do servidor)</p></li>
<li><p>FQDN do servidor</p></li>
<li><p>FQDN do pool do Lync</p></li>
<li><p>Atender a URLs simples</p></li>
<li><p>URL simples de discagem</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou uma entrada curinga para as URLs simples</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Como usar um certificado curinga:</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externa</p></td>
<td><p>FQDN do pool</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da web externa</p></li>
<li><p>URL simples de discagem</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou uma entrada curinga para as URLs simples</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Como usar um certificado curinga:</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</p>
<p>As entradas curinga são suportadas pelas entradas de URL simples.</p></td>
</tr>
</tbody>
</table>


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
<th>Certificado</th>
<th>Nome do assunto/nome comum</th>
<th>Nome alternativo de entidade</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do pool de diretor</p></td>
<td><p>FQDN do diretor, FQDN do pool de diretor</p>
<p>Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</p>
<p>Se esse pool de diretor for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
<tr class="even">
<td><p>Web Internal</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN de web interna (que é o mesmo que o FQDN do servidor)</p></li>
<li><p>FQDN do servidor</p></li>
<li><p>FQDN do pool do Lync</p></li>
<li><p>Atender a URLs simples</p></li>
<li><p>URL simples de discagem</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou uma entrada curinga para as URLs simples</p></li>
</ul></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web externa</p></td>
<td><p>FQDN do servidor</p></td>
<td><p>Cada um dos seguintes:</p>
<ul>
<li><p>FQDN da web externa</p></li>
<li><p>URL simples de discagem</p></li>
<li><p>Administrar URL simples</p></li>
<li><p>Ou uma entrada curinga para as URLs simples</p></li>
</ul></td>
<td><p>O FQDN da Web externa do diretor deve ser diferente do pool de front-end ou do servidor front-end.</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Se você tiver um pool autônomo do servidor de mediação, os servidores de mediação em cada um precisam dos certificados listados na tabela a seguir. Se você colocar o servidor de mediação com os servidores front end, os certificados listados na tabela "certificados para servidor front-end no pool Front-End", anteriormente neste tópico, serão suficientes.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificados para servidor de mediação autônomo

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
<th>Nome do assunto/nome comum</th>
<th>Nome alternativo de entidade</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do pool</p></td>
<td><p>FQDN do pool</p>
<p>FQDN do servidor membro do pool</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificados para aparelho de ramificação sobreviventes

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
<th>Nome do assunto/nome comum</th>
<th>Nome alternativo de entidade</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Padrão</p></td>
<td><p>FQDN do aplicativo</p></td>
<td><p>SPI. &lt;sipdomain&gt; (precisa de uma entrada por domínio SIP)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira também


[Suporte a certificado curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

