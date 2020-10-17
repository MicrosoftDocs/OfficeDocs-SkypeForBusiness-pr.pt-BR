---
title: 'Lync Server 2013: definindo seus requisitos de mobilidade'
description: 'Lync Server 2013: definindo seus requisitos de mobilidade.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545537"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="916b9-103">Definindo seus requisitos de mobilidade para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="916b9-103">Defining your mobility requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="916b9-104">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="916b9-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="916b9-105">Durante a fase de planejamento para o recurso de mobilidade do Lync Server 2013, quando você usa os clientes móveis do Lync 2010 Mobile e Lync 2013, toma decisões que determinam suas etapas de implantação.</span><span class="sxs-lookup"><span data-stu-id="916b9-105">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="916b9-106">Estas são as decisões que você deve considerar:</span><span class="sxs-lookup"><span data-stu-id="916b9-106">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="916b9-107">**Você deseja usar a descoberta automática para clientes móveis do Lync?**</span><span class="sxs-lookup"><span data-stu-id="916b9-107">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="916b9-108">Se você quiser oferecer suporte à descoberta automática, precisará criar novos registros de DNS (sistema de nomes de domínio) internos e externos, adicionar nomes alternativos de entidade aos certificados nos servidores front-end, diretores e proxy reverso e modificar as regras de publicação existentes no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="916b9-108">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="916b9-109">Para obter detalhes, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="916b9-109">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="916b9-110">Com a descoberta automática, os usuários podem localizar automaticamente os serviços Web do Lync Server 2013 de qualquer lugar dentro ou fora da rede corporativa, sem inserir URLs em suas configurações de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="916b9-110">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="916b9-111">Se você usar as configurações manuais em vez da descoberta automática, os usuários móveis precisarão inserir manualmente as seguintes URLs em seus dispositivos móveis:</span><span class="sxs-lookup"><span data-stu-id="916b9-111">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="916b9-112">https:// \<ExtPoolFQDN\> /autodiscover/autodiscoverservice.svc/root para acesso externo</span><span class="sxs-lookup"><span data-stu-id="916b9-112">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="916b9-113">https:// \<IntPoolFQDN\> /autodiscover/autodiscoverservice. svc/root para acesso interno</span><span class="sxs-lookup"><span data-stu-id="916b9-113">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="916b9-p102">Recomendamos o uso da descoberta automática. O uso principal das configurações manuais é para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="916b9-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="916b9-116">**Se você decidir oferecer suporte à descoberta automática, estará disposto a atualizar os certificados no proxy reverso com nomes de entidade alternativos para cada domínio SIP?**</span><span class="sxs-lookup"><span data-stu-id="916b9-116">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="916b9-117">Se você tiver muitos domínios SIP, a atualização de certificados públicos no proxy reverso pode se tornar muito cara.</span><span class="sxs-lookup"><span data-stu-id="916b9-117">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="916b9-118">Se esse for o caso, você pode optar por implementar a descoberta automática para que a solicitação inicial de serviço de descoberta automática use HTTP na porta 80, em vez de usar HTTPS na porta 443.</span><span class="sxs-lookup"><span data-stu-id="916b9-118">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="916b9-119">No entanto, essa não é a abordagem recomendada.</span><span class="sxs-lookup"><span data-stu-id="916b9-119">However, this is not the recommended approach.</span></span> <span data-ttu-id="916b9-120">Se você decidir escolher essa alternativa, não precisará atualizar os certificados no proxy reverso, mas precisará criar uma regra de publicação na Web para HTTP na porta 80.</span><span class="sxs-lookup"><span data-stu-id="916b9-120">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="916b9-121">Para obter mais detalhes, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="916b9-121">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="916b9-122">**Você deseja oferecer suporte aos clientes móveis do Lync de dentro e fora da rede corporativa, ou deseja oferecer suporte somente dentro da rede corporativa?**</span><span class="sxs-lookup"><span data-stu-id="916b9-122">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="916b9-p104">Se você quiser oferecer suporte aos clientes móveis de dentro e fora de sua rede, os dispositivos móveis poderão acessar os recursos de mobilidade a partir de qualquer local. A configuração padrão é oferecer suporte aos clientes de dentro e fora da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="916b9-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="916b9-125">Embora a configuração padrão permita que o tráfego do cliente móvel passe pelo site externo, é possível restringir o tráfego do cliente móvel à rede corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="916b9-125">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="916b9-126">Quando você restringe o tráfego para a rede interna, os usuários podem usar os aplicativos móveis do Lync em seus dispositivos móveis somente quando estão dentro da rede.</span><span class="sxs-lookup"><span data-stu-id="916b9-126">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="916b9-127">Para implantações que oferecem suporte à mobilidade usando o serviço de mobilidade do MCX e o Lync 2010 Mobile, execute o cmdlet **set-CsMcxConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="916b9-127">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="916b9-128">Para configurar a mobilidade somente para uso interno, você usaria um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="916b9-128">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="916b9-129">Não há configurações adicionais necessárias para o UCWA.</span><span class="sxs-lookup"><span data-stu-id="916b9-129">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="916b9-130">UCWA não tem uma configuração somente de interno equivalente.</span><span class="sxs-lookup"><span data-stu-id="916b9-130">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="916b9-131">Se você estiver usando um servidor front-end do Lync Server 2013 &nbsp; ou pools de front-ends e <STRONG>não tiver</STRONG> servidores front-end do Lync Server 2010 &nbsp; ou pools de front-ends, não <STRONG>haverá necessidade de persistência baseada em cookie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="916b9-131">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="916b9-132">Se você precisar manter qualquer servidor &nbsp; front-end do Lync Server 2010 ou pools de front-ends, as mesmas regras ainda serão aplicadas como no Lync server 2010 para persistência baseada em cookie.</span><span class="sxs-lookup"><span data-stu-id="916b9-132">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="916b9-133">**Você deseja oferecer suporte às notificações por push para dispositivos Apple iOS e Windows Phones?**</span><span class="sxs-lookup"><span data-stu-id="916b9-133">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="916b9-134">Se você oferecer suporte às notificações por push, os dispositivos Apple iOS suportados e os Windows Phones receberão uma notificação sobre os eventos que ocorrem quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="916b9-134">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="916b9-135">Você deve configurar seu servidor de borda para ter uma relação de Federação com o serviço de notificação por push do Lync Server baseado na nuvem, que está localizado no datacenter do Lync Online e executar um cmdlet para habilitar as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="916b9-135">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="916b9-136">Se você quiser dar suporte a notificações por push sobre sua rede do Wi-Fi, além de dar suporte a notificações por push sobre as redes 3G ou de dados de provedores de dispositivos móveis, você deve abrir a porta 5223 de saída em sua empresa Wi-Fi rede.</span><span class="sxs-lookup"><span data-stu-id="916b9-136">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="916b9-137">O suporte às notificações por push sobre a rede Wi-Fi oferece suporte aos dispositivos móveis que usam apenas Wi-Fi e dispositivos móveis que possuem uma recepção interna ruim.</span><span class="sxs-lookup"><span data-stu-id="916b9-137">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="916b9-138">A porta TCP 5223 só é necessária ao suporte a dispositivos Apple que executam o cliente móvel do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="916b9-138">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="916b9-139">Se você não oferecer suporte a notificações por push, os usuários de dispositivos móveis Apple e Windows phones não descobrirá sobre eventos, como convites de mensagens instantâneas ou mensagens perdidas, que ocorrem quando o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="916b9-139">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="916b9-140">Os clientes móveis do Lync 2013 em dispositivos Apple não exigem notificações por push.</span><span class="sxs-lookup"><span data-stu-id="916b9-140">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="916b9-141">Os clientes móveis do Lync 2013 no Windows Phone usam notificação por push.</span><span class="sxs-lookup"><span data-stu-id="916b9-141">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="916b9-142">O planejamento da notificação por push e a impressão de notificação por push permanecem os mesmos para Lync Mobile no Windows Phone e dispositivos Apple que não podem executar o cliente móvel do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="916b9-142">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="916b9-143">**Deseja que todos os usuários tenham acesso aos recursos de mobilidade ou você deseja poder especificar quais usuários têm acesso a esses recursos?**</span><span class="sxs-lookup"><span data-stu-id="916b9-143">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="916b9-144">A tabela descreve os recursos disponíveis para os usuários no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="916b9-144">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="916b9-145">Os padrões permitem chamar via trabalho, permitir voz sobre IP (VoIP) e habilitar mobilidade.</span><span class="sxs-lookup"><span data-stu-id="916b9-145">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="916b9-146">Este é o conjunto completo de opções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="916b9-146">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="916b9-147">Nome/escopo do recurso/parâmetro (os nomes de parâmetro de política podem não ser iguais)</span><span class="sxs-lookup"><span data-stu-id="916b9-147">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="916b9-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="916b9-148">Description</span></span></th>
    <th><span data-ttu-id="916b9-149">Introduzido</span><span class="sxs-lookup"><span data-stu-id="916b9-149">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="916b9-150">Habilitar mobilidade</span><span class="sxs-lookup"><span data-stu-id="916b9-150">Enable Mobility</span></span></p>
    <p><span data-ttu-id="916b9-151">Nome do parâmetro: <code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="916b9-151">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="916b9-152">Escopo: global/site/usuário</span><span class="sxs-lookup"><span data-stu-id="916b9-152">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="916b9-153">Configuração administrativa para controlar os usuários em um determinado escopo com o Lync Mobile instalado, se a política estiver definida como false, o usuário não poderá entrar no cliente.</span><span class="sxs-lookup"><span data-stu-id="916b9-153">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="916b9-154">A configuração padrão é true.</span><span class="sxs-lookup"><span data-stu-id="916b9-154">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="916b9-155">Atualização cumulativa para o Lync Server 2010: novembro de 2011</span><span class="sxs-lookup"><span data-stu-id="916b9-155">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="916b9-156">Habilitar voz externa</span><span class="sxs-lookup"><span data-stu-id="916b9-156">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="916b9-157">Nome do parâmetro: <code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="916b9-157">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="916b9-158">Escopo: global/site/usuário</span><span class="sxs-lookup"><span data-stu-id="916b9-158">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="916b9-159">Controla a capacidade de um usuário de usar Call via Work, um recurso que permite que os usuários façam e recebam chamadas usando seus números de trabalho, em vez de seus números de celular.</span><span class="sxs-lookup"><span data-stu-id="916b9-159">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="916b9-160">Se for definido como false, o usuário não poderá fazer ou receber chamadas usando seu número comercial do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="916b9-160">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="916b9-161">A configuração padrão é true</span><span class="sxs-lookup"><span data-stu-id="916b9-161">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="916b9-162">Atualização cumulativa para o Lync Server 2010: novembro de 2011</span><span class="sxs-lookup"><span data-stu-id="916b9-162">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="916b9-163">Habilitar áudio e vídeo IP</span><span class="sxs-lookup"><span data-stu-id="916b9-163">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="916b9-164">Nome do parâmetro: <code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="916b9-164">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="916b9-165">Escopo: global/site/usuário</span><span class="sxs-lookup"><span data-stu-id="916b9-165">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="916b9-166">Controla se um usuário pode usar VoIP para fazer ou receber chamadas de voz ou vídeo em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="916b9-166">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="916b9-167">Se for definido como false, o usuário não poderá fazer ou receber chamadas VoIP ou de vídeo em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="916b9-167">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="916b9-168">A configuração padrão é true.</span><span class="sxs-lookup"><span data-stu-id="916b9-168">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="916b9-169">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="916b9-169">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="916b9-170">Exigir WiFi para áudio IP</span><span class="sxs-lookup"><span data-stu-id="916b9-170">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="916b9-171">Nome do parâmetro: <code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="916b9-171">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="916b9-172">Escopo: global/site/usuário</span><span class="sxs-lookup"><span data-stu-id="916b9-172">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="916b9-173">Essa configuração define se o cliente será solicitado a fazer e receber chamadas por VoIP em vez da rede de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="916b9-173">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="916b9-174">Se for definido como true, o usuário poderá fazer e receber chamadas de VoIP somente quando estiver conectado a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="916b9-174">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="916b9-175">A configuração padrão é false.</span><span class="sxs-lookup"><span data-stu-id="916b9-175">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="916b9-176">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="916b9-176">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="916b9-177">Exigir WiFi para vídeo IP</span><span class="sxs-lookup"><span data-stu-id="916b9-177">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="916b9-178">Nome do parâmetro: <code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="916b9-178">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="916b9-179">Escopo: global/site/usuário</span><span class="sxs-lookup"><span data-stu-id="916b9-179">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="916b9-180">Essa configuração define se o cliente será solicitado a fazer e receber chamadas de vídeo em Wi-Fi, em vez de na rede de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="916b9-180">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="916b9-181">Se for definido como true, o usuário poderá fazer e receber chamadas de vídeo somente quando estiver conectado a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="916b9-181">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="916b9-182">A configuração padrão é false.</span><span class="sxs-lookup"><span data-stu-id="916b9-182">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="916b9-183">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="916b9-183">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="916b9-184">Para obter uma descrição das configurações de política que você pode configurar e como gerenciar as políticas, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), Grant- [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="916b9-184">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="916b9-185">**Você deseja que os usuários não habilitados para Enterprise Voice possam usar o recurso Clique para ingressar a fim de entrar em conferências?**</span><span class="sxs-lookup"><span data-stu-id="916b9-185">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="916b9-186">Para que os usuários tenham acesso aos recursos de mobilidade e Telefonar via Trabalho, eles precisam ser habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="916b9-186">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="916b9-187">No entanto, os usuários que não estão habilitados para o Enterprise Voice podem participar de conferências clicando no link em seu dispositivo móvel, caso tenham uma política de voz apropriada atribuída.</span><span class="sxs-lookup"><span data-stu-id="916b9-187">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="916b9-188">Você pode atribuir uma política de voz específica a esses usuários ou certificar-se de que exista uma política global ou uma política de nível de site que se aplique a elas.</span><span class="sxs-lookup"><span data-stu-id="916b9-188">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="916b9-189">A política de voz atribuída deve ter registros de uso de rede telefônica pública comutada (PSTN) e rotas que definem as áreas às quais os usuários podem discar para ingressar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="916b9-189">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="916b9-190">Para obter detalhes sobre como configurar política de voz, registros de uso de PSTN e rotas, consulte [Configuring Voice Policies, PSTN Usage Records, and Voice Routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="916b9-190">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="916b9-191">Os usuários móveis que desejam usar o clique para ingressar exigem uma política de voz, junto com os registros de uso PSTN e rotas de voz relacionados, porque clicar no link no dispositivo móvel resulta em uma chamada de saída do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="916b9-191">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="916b9-192">Confira também</span><span class="sxs-lookup"><span data-stu-id="916b9-192">See Also</span></span>


[<span data-ttu-id="916b9-193">Requisitos técnicos para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="916b9-193">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="916b9-194">Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="916b9-194">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

