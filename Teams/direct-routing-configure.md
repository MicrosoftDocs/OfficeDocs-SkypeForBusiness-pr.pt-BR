---
title: Configurar o Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba como configurar o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 40439fd31db458f8cb306c0e3dbd456aa59a7a21
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111725"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="cc130-103">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="cc130-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="cc130-104">Assista à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="cc130-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="cc130-105">Se você ainda não tiver feito isso, leia [planejar o roteamento direto](direct-routing-plan.md) para pré-requisitos e revise outras etapas necessárias antes de configurar a rede do Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="cc130-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="cc130-106">Este artigo descreve como configurar o roteamento direto do sistema de telefonia da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc130-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="cc130-107">Ele detalha como emparelhar um SBC (controlador de borda de sessão) com suporte para roteamento direto e como configurar os usuários do Microsoft Teams para usar o roteamento direto para se conectar à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="cc130-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="cc130-108">Para concluir as etapas explicadas neste artigo, os administradores precisam estar familiarizados com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc130-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="cc130-109">Para obter mais informações sobre como usar o PowerShell, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc130-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="cc130-110">Recomendamos que você confirme que o seu SBC já foi configurado como recomendado pelo fornecedor do SBC:</span><span class="sxs-lookup"><span data-stu-id="cc130-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="cc130-111">Documentação de implantação do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="cc130-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="cc130-112">Documentação de implantação do Oracle</span><span class="sxs-lookup"><span data-stu-id="cc130-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="cc130-113">Documentação da implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="cc130-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="cc130-114">Documentação de implantação do anynode (File-Systems)</span><span class="sxs-lookup"><span data-stu-id="cc130-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="cc130-115">Você pode configurar seu sistema telefônico da Microsoft e permitir que os usuários usem o roteamento direto e, em seguida, configurar o Microsoft Teams como o cliente de chamada preferencial, completando os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cc130-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="cc130-116">Emparelhar o SBC com um sistema telefônico da Microsoft e validar o emparelhamento</span><span class="sxs-lookup"><span data-stu-id="cc130-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="cc130-117">Habilitar usuários para o serviço de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="cc130-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="cc130-118">Garantir que o Microsoft Teams seja o cliente de chamadas preferencial para os usuários</span><span class="sxs-lookup"><span data-stu-id="cc130-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="cc130-119">Emparelhar o SBC com o serviço de roteamento direto do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="cc130-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="cc130-120">Veja a seguir as três etapas de alto nível para permitir que você conecte ou Emparelhe o SBC à interface de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="cc130-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="cc130-121">Conectar-se ao centro **de administração do Skype for Business online** usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc130-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="cc130-122">Emparelhar o SBC</span><span class="sxs-lookup"><span data-stu-id="cc130-122">Pair the SBC</span></span> 
- <span data-ttu-id="cc130-123">Validar o emparelhamento</span><span class="sxs-lookup"><span data-stu-id="cc130-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="cc130-124">Conectar-se ao Skype for Business online usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc130-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="cc130-125">Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC com a interface de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="cc130-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="cc130-126">Para abrir uma sessão do PowerShell, siga as etapas descritas em [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc130-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="cc130-127">Depois de estabelecer uma sessão remota do PowerShell, valide se você pode ver os comandos para gerenciar o SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="cc130-128">Para validar os comandos, digite ou copie/cole o seguinte na sessão do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="cc130-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="cc130-129">Seu comando retornará as quatro funções mostradas aqui que permitirão que você gerencie o SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="cc130-130">Emparelhar o SBC ao locatário</span><span class="sxs-lookup"><span data-stu-id="cc130-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="cc130-131">Para emparelhar o SBC com o locatário, na sessão do PowerShell, digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="cc130-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="cc130-132">É altamente recomendável definir um limite máximo de chamadas no SBC, usando as informações que podem ser encontradas na documentação do SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="cc130-133">O limite acionará uma notificação se o SBC estiver no nível de capacidade.</span><span class="sxs-lookup"><span data-stu-id="cc130-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="cc130-134">Você só pode emparelhar o SBC se a parte do domínio de seu FQDN corresponder a um dos domínios registrados em seu locatário \*, exceto. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cc130-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="cc130-135">Não \*há suporte para o uso de nomes de domínio. onmicrosoft.com para o nome FQDN do SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="cc130-136">Por exemplo, se você tiver dois nomes de domínio:</span><span class="sxs-lookup"><span data-stu-id="cc130-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="cc130-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="cc130-137">**contoso**.com</span></span><br/><span data-ttu-id="cc130-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cc130-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="cc130-139">Para o nome do SBC, você pode usar o nome sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cc130-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="cc130-140">Se você tentar emparelhar o SBC com um nome SBC. contoso. ABC, o sistema não permitirá que o domínio não seja pertencente a esse locatário.</span><span class="sxs-lookup"><span data-stu-id="cc130-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="cc130-141">Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída.</span><span class="sxs-lookup"><span data-stu-id="cc130-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="cc130-142">Se não for, você receberá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="cc130-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="cc130-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="cc130-143"></span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="cc130-144">Devolver</span><span class="sxs-lookup"><span data-stu-id="cc130-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="cc130-145">Há opções adicionais que podem ser definidas durante o processo de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="cc130-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="cc130-146">No exemplo anterior, no entanto, somente os parâmetros mínimos necessários são exibidos.</span><span class="sxs-lookup"><span data-stu-id="cc130-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="cc130-147">A tabela a seguir lista os parâmetros adicionais que você pode usar em definir parâmetros ```New-CsOnlinePstnGateway```para.</span><span class="sxs-lookup"><span data-stu-id="cc130-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="cc130-148">Necessário?</span><span class="sxs-lookup"><span data-stu-id="cc130-148">Required?</span></span>|<span data-ttu-id="cc130-149">Nome</span><span class="sxs-lookup"><span data-stu-id="cc130-149">Name</span></span>|<span data-ttu-id="cc130-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc130-150">Description</span></span>|<span data-ttu-id="cc130-151">Padrão</span><span class="sxs-lookup"><span data-stu-id="cc130-151">Default</span></span>|<span data-ttu-id="cc130-152">Valores possíveis</span><span class="sxs-lookup"><span data-stu-id="cc130-152">Possible values</span></span>|<span data-ttu-id="cc130-153">Tipo e restrições</span><span class="sxs-lookup"><span data-stu-id="cc130-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc130-154">Sim</span><span class="sxs-lookup"><span data-stu-id="cc130-154">Yes</span></span>|<span data-ttu-id="cc130-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="cc130-155">FQDN</span></span>|<span data-ttu-id="cc130-156">O nome FQDN do SBC</span><span class="sxs-lookup"><span data-stu-id="cc130-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="cc130-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cc130-157">None</span></span>|<span data-ttu-id="cc130-158">Nome do NoneFQDN, limite de 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="cc130-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="cc130-159">Cadeia de caracteres, lista de caracteres permitidos e não permitidos em [convenções de nomenclatura no Active Directory para computadores, domínios, sites e UOs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="cc130-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="cc130-160">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-160">No</span></span>|<span data-ttu-id="cc130-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="cc130-161">MediaBypass</span></span> |<span data-ttu-id="cc130-162">O parâmetro indicado do SBC dá suporte à bypass de mídia e o administrador deseja usá-la.</span><span class="sxs-lookup"><span data-stu-id="cc130-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="cc130-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cc130-163">None</span></span>|<span data-ttu-id="cc130-164">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cc130-164">True</span></span><br/><span data-ttu-id="cc130-165">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-165">False</span></span>|<span data-ttu-id="cc130-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="cc130-166">Boolean</span></span>|
|<span data-ttu-id="cc130-167">Sim</span><span class="sxs-lookup"><span data-stu-id="cc130-167">Yes</span></span>|<span data-ttu-id="cc130-168">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="cc130-168">SipSignallingPort</span></span> |<span data-ttu-id="cc130-169">Porta de escuta usada para comunicação com serviços de roteamento direto usando o protocolo TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="cc130-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="cc130-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cc130-170">None</span></span>|<span data-ttu-id="cc130-171">Qualquer porta</span><span class="sxs-lookup"><span data-stu-id="cc130-171">Any port</span></span>|<span data-ttu-id="cc130-172">0 a 65535</span><span class="sxs-lookup"><span data-stu-id="cc130-172">0 to 65535</span></span> |
|<span data-ttu-id="cc130-173">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-173">No</span></span>|<span data-ttu-id="cc130-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="cc130-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="cc130-175">Quando definido como 10 (valor padrão), as chamadas de saída que não são respondidas pelo gateway em 10 segundos são roteadas para o próximo tronco disponível; Se não houver troncos adicionais, a chamada será automaticamente cancelada.</span><span class="sxs-lookup"><span data-stu-id="cc130-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="cc130-176">Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="cc130-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="cc130-177">O valor padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="cc130-177">The default value is 10.</span></span>|<span data-ttu-id="cc130-178">254</span><span class="sxs-lookup"><span data-stu-id="cc130-178">10</span></span>|<span data-ttu-id="cc130-179">Número</span><span class="sxs-lookup"><span data-stu-id="cc130-179">Number</span></span>|<span data-ttu-id="cc130-180">Núm</span><span class="sxs-lookup"><span data-stu-id="cc130-180">Int</span></span>|
|<span data-ttu-id="cc130-181">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-181">No</span></span>|<span data-ttu-id="cc130-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="cc130-182">ForwardCallHistory</span></span> |<span data-ttu-id="cc130-183">Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.</span><span class="sxs-lookup"><span data-stu-id="cc130-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="cc130-184">Se habilitado, o proxy PSTN do Office 365 envia dois cabeçalhos: histórico-informações e referenciado por.</span><span class="sxs-lookup"><span data-stu-id="cc130-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="cc130-185">O valor padrão é **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="cc130-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="cc130-186">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-186">False</span></span>|<span data-ttu-id="cc130-187">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cc130-187">True</span></span><br/><span data-ttu-id="cc130-188">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-188">False</span></span>|<span data-ttu-id="cc130-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="cc130-189">Boolean</span></span>|
|<span data-ttu-id="cc130-190">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-190">No</span></span>|<span data-ttu-id="cc130-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="cc130-191">ForwardPAI</span></span>|<span data-ttu-id="cc130-192">Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada.</span><span class="sxs-lookup"><span data-stu-id="cc130-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="cc130-193">O header PAI oferece uma forma de verificar a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="cc130-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="cc130-194">Se habilitado, o cabeçalho de identificação privacidade: também será enviado.</span><span class="sxs-lookup"><span data-stu-id="cc130-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="cc130-195">O valor padrão é **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="cc130-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="cc130-196">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-196">False</span></span>|<span data-ttu-id="cc130-197">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cc130-197">True</span></span><br/><span data-ttu-id="cc130-198">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-198">False</span></span>|<span data-ttu-id="cc130-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="cc130-199">Boolean</span></span>|
|<span data-ttu-id="cc130-200">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-200">No</span></span>|<span data-ttu-id="cc130-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="cc130-201">SendSIPOptions</span></span> |<span data-ttu-id="cc130-202">Define se um SBC irá ou não enviará as opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="cc130-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="cc130-203">Se desabilitado, o SBC será excluído do sistema de monitoramento e alerta.</span><span class="sxs-lookup"><span data-stu-id="cc130-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="cc130-204">É altamente recomendável que você ative as opções do SIP.</span><span class="sxs-lookup"><span data-stu-id="cc130-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="cc130-205">O valor padrão é **true**.</span><span class="sxs-lookup"><span data-stu-id="cc130-205">Default value is **True**.</span></span> |<span data-ttu-id="cc130-206">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cc130-206">True</span></span>|<span data-ttu-id="cc130-207">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cc130-207">True</span></span><br/><span data-ttu-id="cc130-208">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-208">False</span></span>|<span data-ttu-id="cc130-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="cc130-209">Boolean</span></span>|
|<span data-ttu-id="cc130-210">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-210">No</span></span>|<span data-ttu-id="cc130-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="cc130-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="cc130-212">Usado pelo sistema de alerta.</span><span class="sxs-lookup"><span data-stu-id="cc130-212">Used by alerting system.</span></span> <span data-ttu-id="cc130-213">Quando qualquer valor for definido, o sistema de alerta gerará um alerta para o administrador do locatário quando o número da sessão simultânea for 90% ou superior a este valor.</span><span class="sxs-lookup"><span data-stu-id="cc130-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="cc130-214">Se o parâmetro não estiver definido, os alertas não serão gerados.</span><span class="sxs-lookup"><span data-stu-id="cc130-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="cc130-215">No entanto, o sistema de monitoramento reportará o número da sessão simultânea a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="cc130-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="cc130-216">Vazio</span><span class="sxs-lookup"><span data-stu-id="cc130-216">Null</span></span>|<span data-ttu-id="cc130-217">Vazio</span><span class="sxs-lookup"><span data-stu-id="cc130-217">Null</span></span><br/><span data-ttu-id="cc130-218">de 1 a 100.000</span><span class="sxs-lookup"><span data-stu-id="cc130-218">1 to 100,000</span></span> ||
|<span data-ttu-id="cc130-219">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-219">No</span></span>|<span data-ttu-id="cc130-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="cc130-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="cc130-221">Permite a seleção de caminho para mídia manualmente.</span><span class="sxs-lookup"><span data-stu-id="cc130-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="cc130-222">O roteamento direto atribui um datacenter para caminho de mídia com base no IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="cc130-223">Sempre selecionamos mais próximo ao Datacenter do SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="cc130-224">No entanto, em alguns casos, um IP público de, por exemplo, um intervalo dos EUA pode ser atribuído a um SBC localizado na Europa.</span><span class="sxs-lookup"><span data-stu-id="cc130-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="cc130-225">Nesse caso, vamos usar o caminho de mídia ideal.</span><span class="sxs-lookup"><span data-stu-id="cc130-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="cc130-226">Esse parâmetro permite definir manualmente a região preferida para tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="cc130-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="cc130-227">Recomendamos configurar esse parâmetro apenas se os logs de chamada indicar claramente que a atribuição automática do Media Center para o caminho de mídia não atribui o mais próximo possível ao Datacenter do SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="cc130-228">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cc130-228">None</span></span>|<span data-ttu-id="cc130-229">Códigos de país no formato ISO</span><span class="sxs-lookup"><span data-stu-id="cc130-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="cc130-230">Não</span><span class="sxs-lookup"><span data-stu-id="cc130-230">No</span></span>|<span data-ttu-id="cc130-231">Habilitado</span><span class="sxs-lookup"><span data-stu-id="cc130-231">Enabled</span></span>|<span data-ttu-id="cc130-232">Usado para habilitar este SBC para chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="cc130-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="cc130-233">Pode ser usado para remover temporariamente o SBC, enquanto ele está sendo atualizado ou durante a manutenção.</span><span class="sxs-lookup"><span data-stu-id="cc130-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="cc130-234">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-234">False</span></span>|<span data-ttu-id="cc130-235">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cc130-235">True</span></span><br/><span data-ttu-id="cc130-236">Falso</span><span class="sxs-lookup"><span data-stu-id="cc130-236">False</span></span>|<span data-ttu-id="cc130-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="cc130-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="cc130-238">Verificar o emparelhamento de SBC</span><span class="sxs-lookup"><span data-stu-id="cc130-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="cc130-239">Verifique a conexão:</span><span class="sxs-lookup"><span data-stu-id="cc130-239">Verify the connection:</span></span> 
- <span data-ttu-id="cc130-240">Verifique se o SBC está na lista de SBCs emparelhado.</span><span class="sxs-lookup"><span data-stu-id="cc130-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="cc130-241">Validar opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="cc130-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="cc130-242">Validar se o SBC estiver na lista de SBCs emparelhado</span><span class="sxs-lookup"><span data-stu-id="cc130-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="cc130-243">Depois de emparelhar o SBC, valide se o SBC está presente na lista de SBCs emparelhada executando o seguinte comando em uma sessão remota do PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="cc130-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="cc130-244">O gateway emparelhado deve aparecer na lista, conforme mostrado no exemplo abaixo, e verificar se o parâmetro **Enabled** exibe um valor de **true**.</span><span class="sxs-lookup"><span data-stu-id="cc130-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="cc130-245">Dique</span><span class="sxs-lookup"><span data-stu-id="cc130-245">Enter:</span></span>

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="cc130-246">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc130-246">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="cc130-247">Validar o fluxo de opções do SIP</span><span class="sxs-lookup"><span data-stu-id="cc130-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="cc130-248">Para validar o emparelhamento usando as opções de SIP de saída, use a interface de gerenciamento do SBC e confirme se o SBC recebe as respostas de OK do 200 para suas mensagens de opções de saída.</span><span class="sxs-lookup"><span data-stu-id="cc130-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="cc130-249">Quando o roteamento direto vê as opções de entrada, ele começará a enviar mensagens de opções de SIP de saída para o FQDN do SBC configurado no campo de cabeçalho de contato na mensagem de opções de entrada.</span><span class="sxs-lookup"><span data-stu-id="cc130-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="cc130-250">Para validar o emparelhamento usando as opções do SIP de entrada, use a interface de gerenciamento do SBC e veja se o SBC envia uma resposta às mensagens de opções que chegam do roteamento direto e que o código de resposta que ele envia é 200 OK.</span><span class="sxs-lookup"><span data-stu-id="cc130-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="cc130-251">Habilitar usuários para o serviço de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="cc130-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="cc130-252">Quando estiver pronto para habilitar os usuários para o serviço de roteamento direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cc130-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="cc130-253">Criar um usuário no Office 365 e atribuir uma licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="cc130-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="cc130-254">Certifique-se de que o usuário esteja hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="cc130-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="cc130-255">Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz.</span><span class="sxs-lookup"><span data-stu-id="cc130-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="cc130-256">Configurar o roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="cc130-256">Configure voice routing.</span></span> <span data-ttu-id="cc130-257">A rota é validada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cc130-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="cc130-258">Criar um usuário no Office 365 e atribuir a licença</span><span class="sxs-lookup"><span data-stu-id="cc130-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="cc130-259">Há duas opções para criar um novo usuário no Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc130-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="cc130-260">No entanto, recomendamos que sua organização selecione e use uma opção para evitar problemas de roteamento:</span><span class="sxs-lookup"><span data-stu-id="cc130-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="cc130-261">Crie o usuário no Active Directory local e sincronize o usuário com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="cc130-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="cc130-262">Confira [integrar seus diretórios locais com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="cc130-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="cc130-263">Crie o usuário diretamente no portal do administrador do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc130-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="cc130-264">Consulte [Adicionar usuários individualmente ou em massa ao Office 365-ajuda para administradores](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="cc130-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="cc130-265">Se sua implantação do Skype for Business Online for coexistente com o Skype for Business 2015 ou o Lync 2010/2013 local, a única opção compatível é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (opção 1).</span><span class="sxs-lookup"><span data-stu-id="cc130-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="cc130-266">Para obter informações sobre os requisitos de licença, consulte [Licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements) no [Roteamento direto do plano](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="cc130-266">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="cc130-267">Certifique-se de que o usuário esteja hospedado no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cc130-267">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="cc130-268">O roteamento direto exige que o usuário seja hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="cc130-268">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="cc130-269">Você pode verificar isso examinando o parâmetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="cc130-269">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="cc130-270">Ele precisa ter um valor no domínio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cc130-270">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="cc130-271">Conecte-se ao PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="cc130-271">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="cc130-272">Execute o comando:</span><span class="sxs-lookup"><span data-stu-id="cc130-272">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="cc130-273">Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz</span><span class="sxs-lookup"><span data-stu-id="cc130-273">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="cc130-274">Depois de criar o usuário e atribuir uma licença, a próxima etapa é configurar o número de telefone e o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="cc130-274">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="cc130-275">Isso pode ser feito em uma etapa.</span><span class="sxs-lookup"><span data-stu-id="cc130-275">This can be done in one step.</span></span> 

<span data-ttu-id="cc130-276">Para adicionar o número de telefone e habilitar o correio de voz:</span><span class="sxs-lookup"><span data-stu-id="cc130-276">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="cc130-277">Conectar-se a uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc130-277">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="cc130-278">Digite o comando:</span><span class="sxs-lookup"><span data-stu-id="cc130-278">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

<span data-ttu-id="cc130-279">Por exemplo, para adicionar um número de telefone para o usuário "Spencer baixo", você deve digitar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc130-279">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```PowerShell
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="cc130-280">O número de telefone usado deve ser configurado como um número de telefone completo E. 164 com código de país.</span><span class="sxs-lookup"><span data-stu-id="cc130-280">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="cc130-281">Se o número de telefone do usuário for gerenciado localmente, use o Shell de gerenciamento do Skype for Business local ou o painel de controle para configurar o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="cc130-281">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="cc130-282">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="cc130-282">Configure Voice Routing</span></span> 

<span data-ttu-id="cc130-283">O sistema telefônico da Microsoft tem um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC específico com base em:</span><span class="sxs-lookup"><span data-stu-id="cc130-283">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="cc130-284">Padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="cc130-284">Called number pattern</span></span> 
- <span data-ttu-id="cc130-285">Chamado de padrão de número + usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="cc130-285">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="cc130-286">A SBCs pode ser designada como ativa e de backup.</span><span class="sxs-lookup"><span data-stu-id="cc130-286">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="cc130-287">Isso significa que, quando o SBC que é configurado como ativo para este padrão de número ou de número + usuário específico não está disponível, as chamadas são roteadas para um SBC de backup.</span><span class="sxs-lookup"><span data-stu-id="cc130-287">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="cc130-288">O encaminhamento de chamadas é composto pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="cc130-288">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="cc130-289">Política de roteamento de voz – contêiner para usos de PSTN; pode ser atribuído a um usuário ou a vários usuários</span><span class="sxs-lookup"><span data-stu-id="cc130-289">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="cc130-290">Usos de PSTN – contêiner para roteiros de voz e usos de PSTN; pode ser compartilhado em diferentes políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="cc130-290">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="cc130-291">Rotas de voz – o padrão de número e o conjunto de gateways PSTN online a serem usados para chamadas em que o número de chamada corresponde ao padrão</span><span class="sxs-lookup"><span data-stu-id="cc130-291">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="cc130-292">Gateway PSTN online-o ponteiro para um SBC também armazena a configuração aplicada quando a chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (PAI) ou codecs preferenciais; pode ser adicionado a roteiros de voz</span><span class="sxs-lookup"><span data-stu-id="cc130-292">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="cc130-293">Criando uma política de roteamento de voz com um uso PSTN</span><span class="sxs-lookup"><span data-stu-id="cc130-293">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="cc130-294">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz no fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cc130-294">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="cc130-295">**Fluxo de chamadas 1 (à esquerda):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc130-295">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cc130-296">Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="cc130-296">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="cc130-297">**Fluxo de chamadas 2 (à direita):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc130-297">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cc130-298">Se nenhum SBC estiver disponível, a rota com prioridade menor será tentada (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="cc130-298">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="cc130-299">Se nenhum dos SBCs estiver disponível, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="cc130-299">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="cc130-301">Nos dois exemplos, enquanto a rota de voz é atribuída às prioridades, o SBCs nos roteiros é tentado em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="cc130-301">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc130-302">A menos que o usuário também tenha uma licença do plano de chamadas da Microsoft, as chamadas para qualquer número, exceto números que correspondam aos padrões + 1 425 XXX XX XX ou + 1 206 XXX XX XX no exemplo de configuração são descartados.</span><span class="sxs-lookup"><span data-stu-id="cc130-302">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="cc130-303">Se o usuário tiver uma licença de plano de chamada, a chamada será roteada automaticamente de acordo com as políticas do plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc130-303">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="cc130-304">O plano de chamadas da Microsoft aplica-se automaticamente como a última rota para todos os usuários com a licença do plano de chamadas da Microsoft e não requer configuração de roteamento de chamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="cc130-304">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="cc130-305">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números canadenses e números (chamadas que vão para o padrão de número chamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="cc130-305">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="cc130-307">Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="cc130-307">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="cc130-308">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, encaminhe pelo plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc130-308">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="cc130-309">Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="cc130-309">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc130-310">O valor de prioridade para a rota "Other + 1" não importa nesse caso, pois há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="cc130-310">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="cc130-311">Se um usuário fizer uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiverem indisponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="cc130-311">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="cc130-312">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="cc130-312">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="cc130-313">Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="cc130-313">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="cc130-314">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="cc130-314">**PSTN usage**</span></span>|<span data-ttu-id="cc130-315">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="cc130-315">**Voice route**</span></span>|<span data-ttu-id="cc130-316">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="cc130-316">**Number pattern**</span></span>|<span data-ttu-id="cc130-317">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="cc130-317">**Priority**</span></span>|<span data-ttu-id="cc130-318">**SBC**</span><span class="sxs-lookup"><span data-stu-id="cc130-318">**SBC**</span></span>|<span data-ttu-id="cc130-319">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cc130-319">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc130-320">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="cc130-320">US only</span></span>|<span data-ttu-id="cc130-321">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="cc130-321">"Redmond 1"</span></span>|<span data-ttu-id="cc130-322">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-322">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc130-323">1</span><span class="sxs-lookup"><span data-stu-id="cc130-323">1</span></span>|<span data-ttu-id="cc130-324">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-324">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cc130-325">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-325">sbc2.contoso.biz</span></span>|<span data-ttu-id="cc130-326">Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc130-326">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc130-327">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="cc130-327">US only</span></span>|<span data-ttu-id="cc130-328">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="cc130-328">"Redmond 2"</span></span>|<span data-ttu-id="cc130-329">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-329">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc130-330">2</span><span class="sxs-lookup"><span data-stu-id="cc130-330">2</span></span>|<span data-ttu-id="cc130-331">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-331">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cc130-332">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-332">sbc4.contoso.biz</span></span>|<span data-ttu-id="cc130-333">Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc130-333">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc130-334">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="cc130-334">US only</span></span>|<span data-ttu-id="cc130-335">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="cc130-335">"Other +1"</span></span>|<span data-ttu-id="cc130-336">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-336">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cc130-337">3</span><span class="sxs-lookup"><span data-stu-id="cc130-337">3</span></span>|<span data-ttu-id="cc130-338">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-338">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cc130-339">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-339">sbc6.contoso.biz</span></span>|<span data-ttu-id="cc130-340">Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="cc130-340">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="cc130-341">Todas as rotas são associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado apenas à política de roteamento de voz "apenas para os EUA".</span><span class="sxs-lookup"><span data-stu-id="cc130-341">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="cc130-342">Neste exemplo, a política de roteamento de voz é atribuída ao usuário Spencer baixo.</span><span class="sxs-lookup"><span data-stu-id="cc130-342">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="cc130-343">Exemplos de roteiros de chamada</span><span class="sxs-lookup"><span data-stu-id="cc130-343">Examples of call routes</span></span>

<span data-ttu-id="cc130-344">No exemplo a seguir, demonstramos como configurar rotas, usos de PSTN e políticas de roteamento, e atribuímos a política ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc130-344">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="cc130-345">**Etapa 1:** Crie o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="cc130-345">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="cc130-346">Em uma sessão do PowerShell remoto do Skype for Business, digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-346">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="cc130-347">Valide se o uso foi criado inserindo:</span><span class="sxs-lookup"><span data-stu-id="cc130-347">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="cc130-348">Que retorna uma lista de nomes que podem estar truncados:</span><span class="sxs-lookup"><span data-stu-id="cc130-348">Which returns a list of names that may be truncated:</span></span>
```output
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="cc130-349">No exemplo abaixo, você pode ver o resultado do comando `(Get-CSOnlinePSTNUsage).usage` running the PowerShell para exibir nomes completos (não truncados).</span><span class="sxs-lookup"><span data-stu-id="cc130-349">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="cc130-350">**Etapa 2:** Em uma sessão do PowerShell no Skype for Business Online, crie três roteiros: 1, Redmond 2 e outros + 1, conforme detalhado na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="cc130-350">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="cc130-351">Para criar a rota "Redmond 1", digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-351">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cc130-352">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc130-352">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="cc130-353">Para criar a rota Redmond 2, digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-353">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cc130-354">Para criar a outra rota + 1, digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-354">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="cc130-355">Certifique-se de que sua expressão regular no atributo NumberPattern é uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="cc130-355">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="cc130-356">Você pode testá-lo usando este site:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="cc130-356">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="cc130-357">Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="cc130-357">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="cc130-358">Rotear todas as chamadas para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-358">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="cc130-359">Valide se você configurou corretamente a rota executando o comando `Get-CSOnlineVoiceRoute` do PowerShell usando as opções, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="cc130-359">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="cc130-360">Que deve retornar:</span><span class="sxs-lookup"><span data-stu-id="cc130-360">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="cc130-361">No exemplo, a rota "Other + 1" foi automaticamente atribuída à prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="cc130-361">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="cc130-362">**Etapa 3:** Crie uma política de roteamento de voz "apenas EUA" e adicione à política o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="cc130-362">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="cc130-363">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-363">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cc130-364">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="cc130-364">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="cc130-365">**Etapa 4:** Conceder ao usuário Spencer uma política de roteamento de voz baixa usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc130-365">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="cc130-366">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-366">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="cc130-367">Valide a atribuição de política inserindo este comando:</span><span class="sxs-lookup"><span data-stu-id="cc130-367">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="cc130-368">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc130-368">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="cc130-369">Criando uma política de roteamento de voz com vários usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="cc130-369">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="cc130-370">A política de roteamento de voz criada anteriormente só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do plano de chamadas da Microsoft também seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc130-370">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="cc130-371">No exemplo a seguir, você pode criar a política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="cc130-371">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="cc130-372">A política reutiliza o uso de PSTN "EUA e Canadá" criado no exemplo anterior, bem como o novo uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="cc130-372">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="cc130-373">Isso roteia todas as outras chamadas para a SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc130-373">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="cc130-374">Os exemplos mostrados atribuir apenas a política US para o usuário "Spencer baixo" e sem restrições ao usuário "John Woods".</span><span class="sxs-lookup"><span data-stu-id="cc130-374">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="cc130-375">Spencer baixo – chamadas permitidas somente para números canadenses e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="cc130-375">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="cc130-376">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBC deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="cc130-376">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="cc130-377">Os números que não são dos EUA não serão roteados, a menos que a licença do plano de chamada seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc130-377">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="cc130-378">John Woods – chamadas permitidas para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="cc130-378">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="cc130-379">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBC deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="cc130-379">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="cc130-380">Os números que não são dos EUA serão roteados via sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc130-380">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário Spencer baixo](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="cc130-382">Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="cc130-382">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="cc130-383">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, encaminhe pelo plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc130-383">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="cc130-384">Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="cc130-384">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="cc130-386">A tabela a seguir resume as designações de uso de política de roteamento "sem restrições" e rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="cc130-386">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="cc130-387">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="cc130-387">**PSTN usage**</span></span>|<span data-ttu-id="cc130-388">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="cc130-388">**Voice route**</span></span>|<span data-ttu-id="cc130-389">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="cc130-389">**Number pattern**</span></span>|<span data-ttu-id="cc130-390">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="cc130-390">**Priority**</span></span>|<span data-ttu-id="cc130-391">**SBC**</span><span class="sxs-lookup"><span data-stu-id="cc130-391">**SBC**</span></span>|<span data-ttu-id="cc130-392">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cc130-392">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc130-393">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="cc130-393">US Only</span></span>|<span data-ttu-id="cc130-394">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="cc130-394">"Redmond 1"</span></span>|<span data-ttu-id="cc130-395">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-395">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc130-396">1</span><span class="sxs-lookup"><span data-stu-id="cc130-396">1</span></span>|<span data-ttu-id="cc130-397">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-397">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cc130-398">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-398">sbc2.contoso.biz</span></span>|<span data-ttu-id="cc130-399">Roteiro ativo para números de chamada + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc130-399">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc130-400">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="cc130-400">US Only</span></span>|<span data-ttu-id="cc130-401">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="cc130-401">"Redmond 2"</span></span>|<span data-ttu-id="cc130-402">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-402">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc130-403">2</span><span class="sxs-lookup"><span data-stu-id="cc130-403">2</span></span>|<span data-ttu-id="cc130-404">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-404">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cc130-405">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-405">sbc4.contoso.biz</span></span>|<span data-ttu-id="cc130-406">Rota de backup para números do chamado + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc130-406">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc130-407">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="cc130-407">US Only</span></span>|<span data-ttu-id="cc130-408">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="cc130-408">"Other +1"</span></span>|<span data-ttu-id="cc130-409">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-409">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cc130-410">3</span><span class="sxs-lookup"><span data-stu-id="cc130-410">3</span></span>|<span data-ttu-id="cc130-411">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-411">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cc130-412">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-412">sbc6>.contoso.biz</span></span>|<span data-ttu-id="cc130-413">Rota para números de chamada + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="cc130-413">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="cc130-414">International</span><span class="sxs-lookup"><span data-stu-id="cc130-414">International</span></span>|<span data-ttu-id="cc130-415">International</span><span class="sxs-lookup"><span data-stu-id="cc130-415">International</span></span>|<span data-ttu-id="cc130-416">\d +</span><span class="sxs-lookup"><span data-stu-id="cc130-416">\d+</span></span>|<span data-ttu-id="cc130-417">4</span><span class="sxs-lookup"><span data-stu-id="cc130-417">4</span></span>|<span data-ttu-id="cc130-418">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-418">sbc2.contoso.biz</span></span><br/><span data-ttu-id="cc130-419">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc130-419">sbc5.contoso.biz</span></span>|<span data-ttu-id="cc130-420">Rota para qualquer padrão de número</span><span class="sxs-lookup"><span data-stu-id="cc130-420">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="cc130-421">A ordem dos usos de PSTN nas políticas de roteamento de voz é crítica.</span><span class="sxs-lookup"><span data-stu-id="cc130-421">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="cc130-422">Os usos são aplicados em ordem e, se for encontrada uma coincidência no primeiro uso, outros usos nunca serão avaliados.</span><span class="sxs-lookup"><span data-stu-id="cc130-422">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="cc130-423">O uso de PSTN "internacional" deve ser colocado após o uso de PSTN "somente EUA".</span><span class="sxs-lookup"><span data-stu-id="cc130-423">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="cc130-424">Para alterar a ordem dos usos de PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="cc130-424">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="cc130-425">Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "internacional" segundo a execução da ordem inversa:</span><span class="sxs-lookup"><span data-stu-id="cc130-425">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="cc130-426">A prioridade para as rotas de voz "Other + 1" e "International" são atribuídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cc130-426">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="cc130-427">Não importa tão tempo que tenham prioridades menores do que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="cc130-427">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="cc130-428">Exemplo de política de roteamento de voz para usuário John Woods</span><span class="sxs-lookup"><span data-stu-id="cc130-428">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="cc130-429">As etapas para criar o uso de PSTN "internacional", a rota de voz "internacional", a política de roteamento de voz "sem restrições" e, em seguida, atribuí-lo ao usuário "John Woods" são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="cc130-429">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>   


<span data-ttu-id="cc130-430">**Etapa 1**: criar o uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="cc130-430">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="cc130-431">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="cc130-431">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="cc130-432">**Etapa 2**: criar a nova rota de voz "internacional".</span><span class="sxs-lookup"><span data-stu-id="cc130-432">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="cc130-433">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc130-433">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="cc130-434">**Etapa 3**: criar uma política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="cc130-434">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="cc130-435">O uso de PSTN "Redmond 1" e "Redmond" é reutilizado nesta política de roteamento de voz para preservar a manipulação especial de chamadas para número "+ 1 425 XXX XX XX XX" e "+ 1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="cc130-435">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

   ```PowerShell
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

<span data-ttu-id="cc130-436">Tome nota da ordem dos usos de PSTN:</span><span class="sxs-lookup"><span data-stu-id="cc130-436">Take note of the order of PSTN Usages:</span></span>

<span data-ttu-id="cc130-437">a.</span><span class="sxs-lookup"><span data-stu-id="cc130-437">a.</span></span> <span data-ttu-id="cc130-438">Se uma chamada feita ao número "+ 1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial for aplicada.</span><span class="sxs-lookup"><span data-stu-id="cc130-438">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="cc130-439">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como as rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="cc130-439">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

<span data-ttu-id="cc130-440">b.</span><span class="sxs-lookup"><span data-stu-id="cc130-440">b.</span></span> <span data-ttu-id="cc130-441">Se o uso de PSTN "internacional" for anterior aos "EUA e Canadá", as chamadas para + 1 425 XXX XX XX são roteadas para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cc130-441">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="cc130-442">Digite o comando:</span><span class="sxs-lookup"><span data-stu-id="cc130-442">Enter the command:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

<span data-ttu-id="cc130-443">Que retorna</span><span class="sxs-lookup"><span data-stu-id="cc130-443">Which returns</span></span>

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

<span data-ttu-id="cc130-444">**Etapa 4**: atribua a política de roteamento de voz ao usuário "John Woods" usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="cc130-444">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="cc130-445">Em seguida, verifique a tarefa usando o comando:</span><span class="sxs-lookup"><span data-stu-id="cc130-445">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="cc130-446">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc130-446">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="cc130-447">O resultado é que a política de voz aplicada a chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para chamadas para os EUA, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="cc130-447">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="cc130-448">Atribuir o modo apenas Teams aos usuários para garantir chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc130-448">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="cc130-449">O roteamento direto requer que os usuários estejam no modo somente Teams para garantir que as chamadas de entrada sejam feitas no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="cc130-449">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="cc130-450">Para colocar usuários no modo somente Teams, atribua a eles a instância "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="cc130-450">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="cc130-451">Se a sua organização usa o Skype for Business Server ou o Skype for Business Online, consulte o artigo a seguir para interoperabilidade de informações entre o Skype e o Teams: [orientação de migração e interoperabilidade para organizações que usam o Skype for Business em equipe](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="cc130-451">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="cc130-452">Configurar o envio de chamadas diretamente para o correio de voz</span><span class="sxs-lookup"><span data-stu-id="cc130-452">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="cc130-453">O roteamento direto permite encerrar a chamada para um usuário e enviá-la diretamente para a caixa postal dos usuários.</span><span class="sxs-lookup"><span data-stu-id="cc130-453">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="cc130-454">Se você quiser enviar a chamada diretamente para o correio de voz, anexe o aplicativo opaco = App: correio de voz ao cabeçalho URI da solicitação.</span><span class="sxs-lookup"><span data-stu-id="cc130-454">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="cc130-455">Por exemplo, "SIP: user@yourdomain. com; opaco = App: correio de voz".</span><span class="sxs-lookup"><span data-stu-id="cc130-455">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="cc130-456">Nesse caso, o usuário do Teams não receberá a notificação de chamada, a chamada será conectada diretamente ao correio de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="cc130-456">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="cc130-457">Traduza números de chamadas e de chamadas para chamadas de entrada e saída para um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="cc130-457">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="cc130-458">Às vezes, os administradores de locatários podem querer alterar o chamador ou o número de chamada para chamadas de entrada e/ou de entrada com base nos padrões que criaram para garantir a interoperabilidade com SBCs.</span><span class="sxs-lookup"><span data-stu-id="cc130-458">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="cc130-459">Você pode definir uma política de regras de tradução de números para traduzir chamadas para chamadas ou números de chamadas para um formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="cc130-459">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="cc130-460">Você pode usar a política para traduzir números para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc130-460">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="cc130-461">Chamadas recebidas: chamadas de um ponto de extremidade PSTN (chamador) para um cliente do Teams (chamado).</span><span class="sxs-lookup"><span data-stu-id="cc130-461">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="cc130-462">Chamadas de saída: chamadas de um cliente do Teams (chamador) para um ponto de extremidade PSTN (chamado).</span><span class="sxs-lookup"><span data-stu-id="cc130-462">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="cc130-463">A política é aplicada no nível de SBC.</span><span class="sxs-lookup"><span data-stu-id="cc130-463">The policy is applied at the SBC level.</span></span> <span data-ttu-id="cc130-464">Você pode atribuir várias regras de tradução a um SBC, que são aplicadas na ordem em que aparecem quando você as lista no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc130-464">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="cc130-465">Você também pode alterar a ordem das regras na política.</span><span class="sxs-lookup"><span data-stu-id="cc130-465">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="cc130-466">Para criar, modificar, exibir e excluir regras de manipulação de números, use os cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .</span><span class="sxs-lookup"><span data-stu-id="cc130-466">To create, modify, view, and delete number manipulation rules, use the [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule), and [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) cmdlets.</span></span>

<span data-ttu-id="cc130-467">Para atribuir, configurar e listar as regras de manipulação de números no SBCS, use os cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) juntos ```InboundPSTNNumberTranslationRules```com ```OutboundTeamsNumberTranslationRules```os ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRules```parâmetros ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList```,,, ```OutboundPSTNNumberTranslationRulesList``` , e.</span><span class="sxs-lookup"><span data-stu-id="cc130-467">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="cc130-468">Exemplos</span><span class="sxs-lookup"><span data-stu-id="cc130-468">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="cc130-469">Exemplo de configuração do SBC</span><span class="sxs-lookup"><span data-stu-id="cc130-469">Example SBC configuration</span></span>

<span data-ttu-id="cc130-470">Para os cenários de exemplo, executamos ```New-CsOnlinePSTNGateway``` o cmdlet para criar a configuração do SBC a seguir.</span><span class="sxs-lookup"><span data-stu-id="cc130-470">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="cc130-471">As regras de tradução atribuídas ao SBC são resumidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cc130-471">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="cc130-472">Nome</span><span class="sxs-lookup"><span data-stu-id="cc130-472">Name</span></span>  |<span data-ttu-id="cc130-473">Padrão</span><span class="sxs-lookup"><span data-stu-id="cc130-473">Pattern</span></span> |<span data-ttu-id="cc130-474">Conversão</span><span class="sxs-lookup"><span data-stu-id="cc130-474">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cc130-475">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="cc130-475">AddPlus1</span></span>     |<span data-ttu-id="cc130-476">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-476">^(\d{10})$</span></span>          |<span data-ttu-id="cc130-477">+1$1</span><span class="sxs-lookup"><span data-stu-id="cc130-477">+1$1</span></span>          |
|<span data-ttu-id="cc130-478">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="cc130-478">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="cc130-479">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-479">^(\d{4})$</span></span>          | <span data-ttu-id="cc130-480">+ 1206555 $1</span><span class="sxs-lookup"><span data-stu-id="cc130-480">+1206555$1</span></span>         |
|<span data-ttu-id="cc130-481">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="cc130-481">AddSeattleAreaCode</span></span>    |<span data-ttu-id="cc130-482">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-482">^(\d{4})$</span></span>          | <span data-ttu-id="cc130-483">425555 $1</span><span class="sxs-lookup"><span data-stu-id="cc130-483">425555$1</span></span>         |
|<span data-ttu-id="cc130-484">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="cc130-484">StripPlus1</span></span>    |<span data-ttu-id="cc130-485">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="cc130-485">^+1(\d{10})$</span></span>          | <span data-ttu-id="cc130-486">$1</span><span class="sxs-lookup"><span data-stu-id="cc130-486">$1</span></span>         |

<span data-ttu-id="cc130-487">Nestes cenários de exemplo, temos dois usuários, Alice e Bob.</span><span class="sxs-lookup"><span data-stu-id="cc130-487">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="cc130-488">Alice é um usuário do Teams e seu número é + 1 206 555 0100.</span><span class="sxs-lookup"><span data-stu-id="cc130-488">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="cc130-489">Bob é um usuário PSTN e seu número é + 1 425 555 0100.</span><span class="sxs-lookup"><span data-stu-id="cc130-489">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="cc130-490">Exemplo 1: chamada de entrada para um número de 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="cc130-490">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="cc130-491">Bob chama Alice usando um número que não seja E. 164 de dez dígitos.</span><span class="sxs-lookup"><span data-stu-id="cc130-491">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="cc130-492">Bob disca 2065550100 para falar com Alice.</span><span class="sxs-lookup"><span data-stu-id="cc130-492">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="cc130-493">O SBC usa 2065550100 no RequestURI e em cabeçalhos e 4255550100 no cabeçalho de.</span><span class="sxs-lookup"><span data-stu-id="cc130-493">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="cc130-494">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="cc130-494">Header</span></span>  |<span data-ttu-id="cc130-495">Original</span><span class="sxs-lookup"><span data-stu-id="cc130-495">Original</span></span> |<span data-ttu-id="cc130-496">Cabeçalho traduzido</span><span class="sxs-lookup"><span data-stu-id="cc130-496">Translated header</span></span> |<span data-ttu-id="cc130-497">Parâmetro e regra aplicados</span><span class="sxs-lookup"><span data-stu-id="cc130-497">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="cc130-498">RequestURI</span><span class="sxs-lookup"><span data-stu-id="cc130-498">RequestURI</span></span>  |<span data-ttu-id="cc130-499">CONVIDAR sip:2065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-499">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="cc130-500">CONVIDAR sip:+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-500">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="cc130-501">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-501">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="cc130-502">Para</span><span class="sxs-lookup"><span data-stu-id="cc130-502">TO</span></span>    |<span data-ttu-id="cc130-503">PARA: \<SIP:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-503">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-504">PARA: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-504">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-505">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-505">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="cc130-506">De</span><span class="sxs-lookup"><span data-stu-id="cc130-506">FROM</span></span>   |<span data-ttu-id="cc130-507">DE: \<SIP:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-507">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-508">DE: \<SIP:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-508">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-509">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-509">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="cc130-510">Exemplo 2: chamada de entrada para um número de quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="cc130-510">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="cc130-511">Bob chama Alice usando um número de quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="cc130-511">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="cc130-512">Bob disca 0100 para falar com Alice.</span><span class="sxs-lookup"><span data-stu-id="cc130-512">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="cc130-513">O SBC usa 0100 no RequestURI e em cabeçalhos e 4255550100 no cabeçalho de.</span><span class="sxs-lookup"><span data-stu-id="cc130-513">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="cc130-514">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="cc130-514">Header</span></span>  |<span data-ttu-id="cc130-515">Original</span><span class="sxs-lookup"><span data-stu-id="cc130-515">Original</span></span> |<span data-ttu-id="cc130-516">Cabeçalho traduzido</span><span class="sxs-lookup"><span data-stu-id="cc130-516">Translated header</span></span> |<span data-ttu-id="cc130-517">Parâmetro e regra aplicados</span><span class="sxs-lookup"><span data-stu-id="cc130-517">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="cc130-518">RequestURI</span><span class="sxs-lookup"><span data-stu-id="cc130-518">RequestURI</span></span>  |<span data-ttu-id="cc130-519">CONVIDAR sip:0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-519">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="cc130-520">CONVIDAR sip:+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-520">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="cc130-521">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="cc130-521">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="cc130-522">Para</span><span class="sxs-lookup"><span data-stu-id="cc130-522">TO</span></span>    |<span data-ttu-id="cc130-523">PARA: \<SIP:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-523">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-524">PARA: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-524">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-525">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="cc130-525">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="cc130-526">De</span><span class="sxs-lookup"><span data-stu-id="cc130-526">FROM</span></span>   |<span data-ttu-id="cc130-527">DE: \<SIP:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-527">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-528">DE: \<SIP:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-528">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-529">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-529">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="cc130-530">Exemplo 3: chamada de saída usando um número não-E de dez dígitos. 164</span><span class="sxs-lookup"><span data-stu-id="cc130-530">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="cc130-531">Alice chama Bob usando um número de dez dígitos.</span><span class="sxs-lookup"><span data-stu-id="cc130-531">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="cc130-532">Ana discagem 425 555 0100 para falar com o Bob.</span><span class="sxs-lookup"><span data-stu-id="cc130-532">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="cc130-533">O SBC está configurado para usar números de dez dígitos que não são E. 164 para equipes e usuários de PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc130-533">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="cc130-534">Nesse cenário, um plano de discagem converte o número antes de enviá-lo para a interface de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="cc130-534">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="cc130-535">Quando Ana entra em 425 555 0100 no cliente do Teams, o número é convertido em + 14255550100 pelo plano de discagem do país.</span><span class="sxs-lookup"><span data-stu-id="cc130-535">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="cc130-536">Os números resultantes são uma normalização cumulativa das regras do plano de discagem e das regras de tradução do teams.</span><span class="sxs-lookup"><span data-stu-id="cc130-536">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="cc130-537">As regras de tradução do teams removem o "+ 1" que foi adicionado pelo plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="cc130-537">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="cc130-538">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="cc130-538">Header</span></span>  |<span data-ttu-id="cc130-539">Original</span><span class="sxs-lookup"><span data-stu-id="cc130-539">Original</span></span> |<span data-ttu-id="cc130-540">Cabeçalho traduzido</span><span class="sxs-lookup"><span data-stu-id="cc130-540">Translated header</span></span> |<span data-ttu-id="cc130-541">Parâmetro e regra aplicados</span><span class="sxs-lookup"><span data-stu-id="cc130-541">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="cc130-542">RequestURI</span><span class="sxs-lookup"><span data-stu-id="cc130-542">RequestURI</span></span>  |<span data-ttu-id="cc130-543">CONVIDAR sip:+14255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-543">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="cc130-544">CONVIDAR sip:4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-544">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="cc130-545">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-545">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="cc130-546">Para</span><span class="sxs-lookup"><span data-stu-id="cc130-546">TO</span></span>    |<span data-ttu-id="cc130-547">PARA: \<SIP:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-547">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-548">PARA: \<SIP:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-548">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-549">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-549">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="cc130-550">De</span><span class="sxs-lookup"><span data-stu-id="cc130-550">FROM</span></span>   |<span data-ttu-id="cc130-551">DE: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-551">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-552">DE: \<SIP:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-552">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-553">OutboundTeamsNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-553">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="cc130-554">Exemplo 4: chamada de saída usando um número de quatro dígitos que não é E. 164</span><span class="sxs-lookup"><span data-stu-id="cc130-554">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="cc130-555">Alice chama Bob usando um número de quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="cc130-555">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="cc130-556">Alice usa 0100 para se comunicar com Bob em chamadas ou usando um contato.</span><span class="sxs-lookup"><span data-stu-id="cc130-556">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="cc130-557">O SBC está configurado para usar números de quatro dígitos que não são E. 164 para usuários do Teams e números de dez dígitos para usuários de PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc130-557">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="cc130-558">O plano de discagem não é aplicado nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="cc130-558">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="cc130-559">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="cc130-559">Header</span></span>  |<span data-ttu-id="cc130-560">Original</span><span class="sxs-lookup"><span data-stu-id="cc130-560">Original</span></span> |<span data-ttu-id="cc130-561">Cabeçalho traduzido</span><span class="sxs-lookup"><span data-stu-id="cc130-561">Translated header</span></span> |<span data-ttu-id="cc130-562">Parâmetro e regra aplicados</span><span class="sxs-lookup"><span data-stu-id="cc130-562">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="cc130-563">RequestURI</span><span class="sxs-lookup"><span data-stu-id="cc130-563">RequestURI</span></span>  |<span data-ttu-id="cc130-564">CONVIDAR sip:0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-564">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="cc130-565">CONVIDAR sip:4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc130-565">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="cc130-566">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="cc130-566">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="cc130-567">Para</span><span class="sxs-lookup"><span data-stu-id="cc130-567">TO</span></span>    |<span data-ttu-id="cc130-568">PARA: \<SIP:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-568">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-569">PARA: \<SIP:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-569">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-570">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="cc130-570">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="cc130-571">De</span><span class="sxs-lookup"><span data-stu-id="cc130-571">FROM</span></span>   |<span data-ttu-id="cc130-572">DE: \<SIP:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-572">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="cc130-573">DE: \<SIP:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="cc130-573">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="cc130-574">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="cc130-574">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="cc130-575">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc130-575">See also</span></span>

[<span data-ttu-id="cc130-576">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="cc130-576">Plan Direct Routing</span></span>](direct-routing-plan.md)
