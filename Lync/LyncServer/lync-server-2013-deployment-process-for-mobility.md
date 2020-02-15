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
ms.openlocfilehash: 337e85520cb2a285f4e4743837aafa4136c89f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="e50a4-102">Processo de implantação para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50a4-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e50a4-103">_**Última modificação do tópico:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e50a4-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="e50a4-104">Esta seção descreve a sequência de etapas necessárias para implantar o recurso de mobilidade do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e50a4-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="e50a4-105">Processo de implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="e50a4-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e50a4-106">Fase</span><span class="sxs-lookup"><span data-stu-id="e50a4-106">Phase</span></span></th>
<th><span data-ttu-id="e50a4-107">Etapas</span><span class="sxs-lookup"><span data-stu-id="e50a4-107">Steps</span></span></th>
<th><span data-ttu-id="e50a4-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="e50a4-108">Permissions</span></span></th>
<th><span data-ttu-id="e50a4-109">Documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="e50a4-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e50a4-110">Criar registros do DNS (Sistema de Nomes de Domínio)</span><span class="sxs-lookup"><span data-stu-id="e50a4-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e50a4-111">Crie um registro DNS interno CNAME ou um registro (host, se IPv6, AAAA) para resolver a URL interna do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e50a4-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-112">Criar um registro DNS externo CNAME ou um registro (host, se IPv6, AAAA) para resolver a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e50a4-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e50a4-113">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="e50a4-113">Domain Admins</span></span></p>
<p><span data-ttu-id="e50a4-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="e50a4-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="e50a4-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Criar registros DNS para o serviço de descoberta automática no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e50a4-116">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="e50a4-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="e50a4-117">Adicione entradas de nome alternativo de entidade aos seguintes certificados para oferecer suporte a conexões seguras para usuários móveis:</span><span class="sxs-lookup"><span data-stu-id="e50a4-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="e50a4-118">Certificado de diretor</span><span class="sxs-lookup"><span data-stu-id="e50a4-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="e50a4-119">Certificado de pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="e50a4-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="e50a4-120">Certificado de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="e50a4-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e50a4-121">Administrador local</span><span class="sxs-lookup"><span data-stu-id="e50a4-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="e50a4-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modificando certificados para mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e50a4-123">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="e50a4-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e50a4-124">Atribua certificados atualizados com nomes alternativos de entidade ao Ouvinte SSL.</span><span class="sxs-lookup"><span data-stu-id="e50a4-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-125">Reconfigure a regra de publicação na Web para a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e50a4-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-126">Verifique se existe uma regra de publicação na Web para a URL dos serviços Web externos do Lync Server 2013 em seu pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e50a4-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="e50a4-127">Ou</span><span class="sxs-lookup"><span data-stu-id="e50a4-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="e50a4-128">Se você optar por usar HTTP para a solicitação de descoberta automática inicial e não atualizar listas de nomes alternativos de entidades nos certificados, configure uma nova regra de publicação na Web ou RECONFIGURE uma regra de publicação existente para HTTP da porta 80.</span><span class="sxs-lookup"><span data-stu-id="e50a4-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e50a4-129">Administrador local</span><span class="sxs-lookup"><span data-stu-id="e50a4-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="e50a4-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurando o proxy reverso para mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e50a4-131">Testar sua implantação de mobilidade para o Lync 2010 Mobile usando o serviço de mobilidade do MCX</span><span class="sxs-lookup"><span data-stu-id="e50a4-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="e50a4-132">Execute o <strong>Test-CsMcxP2PIM</strong> para enviar uma mensagem instantânea de uma pessoa para outra.</span><span class="sxs-lookup"><span data-stu-id="e50a4-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="e50a4-133">Consulte a documentação do cmdlet do Shell de gerenciamento do Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> para obter uma lista completa das opções.</span><span class="sxs-lookup"><span data-stu-id="e50a4-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="e50a4-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e50a4-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e50a4-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verificando sua implantação de mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e50a4-136">Testar sua implantação de mobilidade para clientes móveis do Lync 2013 usando os componentes Web do UCWA</span><span class="sxs-lookup"><span data-stu-id="e50a4-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="e50a4-137">Use o cmdlet <strong>Test-CsUcwaConference</strong> para testar e verificar se os usuários de teste predefinidos ou um par de usuários reais podem usar o UCWA para criar e participar de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="e50a4-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="e50a4-138">Consulte a documentação do cmdlet do Shell de gerenciamento do Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> para obter uma lista completa das opções.</span><span class="sxs-lookup"><span data-stu-id="e50a4-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="e50a4-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e50a4-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e50a4-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verificando sua implantação de mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e50a4-141">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="e50a4-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e50a4-142">Para servidores de borda do Lync Server 2013, adicione um provedor de hospedagem do Lync Server Online e configure a Federação do provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="e50a4-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-143">Para servidores de borda do Lync Server 2010, adicione um provedor de hospedagem do Lync Server Online e configure a Federação do provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="e50a4-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-144">Para servidores de borda do Office Communications Server 2007 R2, adicione um parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="e50a4-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-145">Se você desejar oferecer suporte a notificações de envio por push em uma rede Wi-Fi, configure uma regra de firewall de saída para a porta TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="e50a4-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-146">Use o cmdlet <strong>Set-CsPushNotificationConfiguration</strong> para habilitar as notificações de envio por push para o APNS (Apple Push Notification Service) e o MPNS (Microsoft Push Notification Service).</span><span class="sxs-lookup"><span data-stu-id="e50a4-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="e50a4-147">Esse recurso é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="e50a4-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="e50a4-148">Use o cmdlet <strong>Test-CsFederatedPartner</strong> para testar a configuração da federação e o cmdlet <strong>Test-CsMCXPushNotification</strong> para testar as notificações de envio por push.</span><span class="sxs-lookup"><span data-stu-id="e50a4-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e50a4-149">As notificações por push são usadas para clientes móveis do Lync 2010 em dispositivos Apple e Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e50a4-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="e50a4-150">A notificação por push é necessária para clientes móveis do Lync 2013 somente no Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e50a4-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="e50a4-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e50a4-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="e50a4-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configurando notificações por push no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e50a4-153">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="e50a4-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="e50a4-154">Use o cmdlet <strong>set-CsMobilityPolicy</strong> para permitir ou impedir:</span><span class="sxs-lookup"><span data-stu-id="e50a4-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="e50a4-155">Ligar via trabalho</span><span class="sxs-lookup"><span data-stu-id="e50a4-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="e50a4-156">Habilitar áudio IP e vídeo IP</span><span class="sxs-lookup"><span data-stu-id="e50a4-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="e50a4-157">Exigir WiFi para áudio IP e/ou vídeo IP</span><span class="sxs-lookup"><span data-stu-id="e50a4-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e50a4-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e50a4-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e50a4-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configurando a política de mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e50a4-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

