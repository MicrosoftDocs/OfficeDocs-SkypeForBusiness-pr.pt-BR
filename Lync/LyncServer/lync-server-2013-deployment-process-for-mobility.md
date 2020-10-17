---
title: 'Lync Server 2013: processo de implantação para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7d0e78cd4a8705178b3704a716846755d5c46f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514478"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Processo de implantação para mobilidade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

Esta seção descreve a sequência de etapas necessárias para implantar o recurso de mobilidade do Lync Server 2013.

### <a name="mobility-deployment-process"></a>Processo de implantação de mobilidade

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Permissões</th>
<th>Documentação de implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criar registros do DNS (Sistema de Nomes de Domínio)</p></td>
<td><ul>
<li><p>Crie um registro DNS interno CNAME ou um registro (host, se IPv6, AAAA) para resolver a URL interna do serviço de descoberta automática.</p></li>
<li><p>Criar um registro DNS externo CNAME ou um registro (host, se IPv6, AAAA) para resolver a URL externa do serviço de descoberta automática.</p></li>
</ul></td>
<td><p>Admins. do Domínio</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Criar registros DNS para o serviço de descoberta automática no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modificar certificados</p></td>
<td><p>Adicione entradas de nome alternativo de entidade aos seguintes certificados para oferecer suporte a conexões seguras para usuários móveis:</p>
<ul>
<li><p>Certificado de diretor</p></li>
<li><p>Certificado de pool de front-ends</p></li>
<li><p>Certificado de proxy reverso</p></li>
</ul></td>
<td><p>Administrador local</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modificando certificados para mobilidade no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar o proxy inverso</p></td>
<td><ul>
<li><p>Atribua certificados atualizados com nomes alternativos de entidade ao Ouvinte SSL.</p></li>
<li><p>Reconfigure a regra de publicação na Web para a URL externa do serviço de descoberta automática.</p></li>
<li><p>Verifique se existe uma regra de publicação na Web para a URL dos serviços Web externos do Lync Server 2013 em seu pool de front-ends.</p></li>
</ul>
<p>Ou</p>
<ul>
<li><p>Se você optar por usar HTTP para a solicitação de descoberta automática inicial e não atualizar listas de nomes alternativos de entidades nos certificados, configure uma nova regra de publicação na Web ou RECONFIGURE uma regra de publicação existente para HTTP da porta 80.</p></li>
</ul></td>
<td><p>Administrador local</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurando o proxy reverso para mobilidade no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Testar sua implantação de mobilidade para o Lync 2010 Mobile usando o serviço de mobilidade do MCX</p></td>
<td><p>Execute o <strong>Test-CsMcxP2PIM</strong> para enviar uma mensagem instantânea de uma pessoa para outra.</p>
<p>Consulte a documentação do cmdlet do Shell de gerenciamento do Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> para obter uma lista completa das opções.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verificando sua implantação de mobilidade no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Testar sua implantação de mobilidade para clientes móveis do Lync 2013 usando os componentes Web do UCWA</p></td>
<td><p>Use o cmdlet <strong>Test-CsUcwaConference</strong> para testar e verificar se os usuários de teste predefinidos ou um par de usuários reais podem usar o UCWA para criar e participar de uma conferência.</p>
<p>Consulte a documentação do cmdlet do Shell de gerenciamento do Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> para obter uma lista completa das opções.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verificando sua implantação de mobilidade no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar para notificações por push</p></td>
<td><ul>
<li><p>Para servidores de borda do Lync Server 2013, adicione um provedor de hospedagem do Lync Server Online e configure a Federação do provedor de hospedagem.</p></li>
<li><p>Para servidores de borda do Lync Server 2010, adicione um provedor de hospedagem do Lync Server Online e configure a Federação do provedor de hospedagem.</p></li>
<li><p>Para servidores de borda do Office Communications Server 2007 R2, adicione um parceiro federado.</p></li>
<li><p>Se você desejar oferecer suporte a notificações de envio por push em uma rede Wi-Fi, configure uma regra de firewall de saída para a porta TCP 5223.</p></li>
<li><p>Use o cmdlet <strong>Set-CsPushNotificationConfiguration</strong> para habilitar as notificações de envio por push para o APNS (Apple Push Notification Service) e o MPNS (Microsoft Push Notification Service). Esse recurso é habilitado por padrão.</p></li>
<li><p>Use o cmdlet <strong>Test-CsFederatedPartner</strong> para testar a configuração da federação e o cmdlet <strong>Test-CsMCXPushNotification</strong> para testar as notificações de envio por push.</p>
<div>

> [!NOTE]  
> As notificações por push são usadas para clientes móveis do Lync 2010 em dispositivos Apple e Windows Phone<BR>A notificação por push é necessária para clientes móveis do Lync 2013 somente no Windows Phone


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configurando notificações por push no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar a política de mobilidade</p></td>
<td><p>Use o cmdlet <strong>set-CsMobilityPolicy</strong> para permitir ou impedir:</p>
<ul>
<li><p>Ligar via trabalho</p></li>
<li><p>Habilitar áudio IP e vídeo IP</p></li>
<li><p>Exigir WiFi para áudio IP e/ou vídeo IP</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configurando a política de mobilidade no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

