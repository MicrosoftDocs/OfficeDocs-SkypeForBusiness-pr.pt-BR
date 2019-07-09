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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba como configurar o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 154f1b08d01bc9e66d7928d6f136c3c69c48efcc
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588147"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="7a534-103">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="7a534-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="7a534-104">Assista à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="7a534-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="7a534-105">Se você ainda não tiver feito isso, leia [planejar o roteamento direto](direct-routing-plan.md) para pré-requisitos e revise outras etapas necessárias antes de configurar a rede do Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="7a534-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="7a534-106">Este artigo descreve como configurar o roteamento direto do sistema de telefonia da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a534-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="7a534-107">Ele detalha como emparelhar um SBC (controlador de borda de sessão) com suporte para roteamento direto e como configurar os usuários do Microsoft Teams para usar o roteamento direto para se conectar à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="7a534-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7a534-108">Para concluir as etapas explicadas neste artigo, os administradores precisam estar familiarizados com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a534-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="7a534-109">Para obter mais informações sobre como usar o PowerShell, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7a534-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="7a534-110">Recomendamos que você confirme que o seu SBC já foi configurado como recomendado pelo fornecedor do SBC:</span><span class="sxs-lookup"><span data-stu-id="7a534-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="7a534-111">Documentação de implantação do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="7a534-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="7a534-112">Documentação da implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="7a534-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="7a534-113">Você pode configurar seu sistema telefônico da Microsoft e permitir que os usuários usem o roteamento direto e, em seguida, configurar o Microsoft Teams como o cliente de chamada preferencial, completando os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7a534-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="7a534-114">Emparelhar o SBC com um sistema telefônico da Microsoft e validar o emparelhamento</span><span class="sxs-lookup"><span data-stu-id="7a534-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="7a534-115">Habilitar usuários para o serviço de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="7a534-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="7a534-116">Garantir que o Microsoft Teams seja o cliente de chamadas preferencial para os usuários</span><span class="sxs-lookup"><span data-stu-id="7a534-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="7a534-117">Emparelhar o SBC com o serviço de roteamento direto do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="7a534-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="7a534-118">Veja a seguir as três etapas de alto nível para permitir que você conecte ou Emparelhe o SBC à interface de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="7a534-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="7a534-119">Conectar-se ao centro **de administração do Skype for Business online** usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a534-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="7a534-120">Emparelhar o SBC</span><span class="sxs-lookup"><span data-stu-id="7a534-120">Pair the SBC</span></span> 
- <span data-ttu-id="7a534-121">Validar o emparelhamento</span><span class="sxs-lookup"><span data-stu-id="7a534-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="7a534-122">Conectar-se ao Skype for Business online usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a534-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="7a534-123">Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC com a interface de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="7a534-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="7a534-124">Para abrir uma sessão do PowerShell, siga as etapas descritas em [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7a534-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="7a534-125">Depois de estabelecer uma sessão remota do PowerShell, valide se você pode ver os comandos para gerenciar o SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="7a534-126">Para validar os comandos, digite ou copie/cole o seguinte na sessão do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="7a534-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="7a534-127">Seu comando retornará as quatro funções mostradas aqui que permitirão que você gerencie o SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="7a534-128">Emparelhar o SBC ao locatário</span><span class="sxs-lookup"><span data-stu-id="7a534-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="7a534-129">Para emparelhar o SBC com o locatário, na sessão do PowerShell, digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="7a534-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="7a534-130">É altamente recomendável definir um limite máximo de chamadas no SBC, usando as informações que podem ser encontradas na documentação do SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="7a534-131">O limite acionará uma notificação se o SBC estiver no nível de capacidade.</span><span class="sxs-lookup"><span data-stu-id="7a534-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="7a534-132">Você só pode emparelhar o SBC se a parte do domínio de seu FQDN corresponder a um dos domínios registrados em seu locatário \*, exceto. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7a534-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="7a534-133">Não \*há suporte para o uso de nomes de domínio. onmicrosoft.com para o nome FQDN do SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="7a534-134">Por exemplo, se você tiver dois nomes de domínio:</span><span class="sxs-lookup"><span data-stu-id="7a534-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="7a534-135">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="7a534-135">**contoso**.com</span></span><br/><span data-ttu-id="7a534-136">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7a534-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="7a534-137">Para o nome do SBC, você pode usar o nome sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7a534-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="7a534-138">Se você tentar emparelhar o SBC com um nome SBC. contoso. ABC, o sistema não permitirá que o domínio não seja pertencente a esse locatário.</span><span class="sxs-lookup"><span data-stu-id="7a534-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="7a534-139">Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída.</span><span class="sxs-lookup"><span data-stu-id="7a534-139">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="7a534-140">Se não for, você receberá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="7a534-140">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="7a534-141">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="7a534-141"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="7a534-142">Devolver</span><span class="sxs-lookup"><span data-stu-id="7a534-142">Returns:</span></span>
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
<span data-ttu-id="7a534-143">Há opções adicionais que podem ser definidas durante o processo de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="7a534-143">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="7a534-144">No exemplo anterior, no entanto, somente os parâmetros mínimos necessários são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7a534-144">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="7a534-145">A tabela a seguir lista os parâmetros adicionais que você pode usar em definindo parâmetros para`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="7a534-145">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="7a534-146">Necessário?</span><span class="sxs-lookup"><span data-stu-id="7a534-146">Required?</span></span>|<span data-ttu-id="7a534-147">Nome</span><span class="sxs-lookup"><span data-stu-id="7a534-147">Name</span></span>|<span data-ttu-id="7a534-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="7a534-148">Description</span></span>|<span data-ttu-id="7a534-149">Padrão</span><span class="sxs-lookup"><span data-stu-id="7a534-149">Default</span></span>|<span data-ttu-id="7a534-150">Valores possíveis</span><span class="sxs-lookup"><span data-stu-id="7a534-150">Possible values</span></span>|<span data-ttu-id="7a534-151">Tipo e restrições</span><span class="sxs-lookup"><span data-stu-id="7a534-151">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a534-152">Sim</span><span class="sxs-lookup"><span data-stu-id="7a534-152">Yes</span></span>|<span data-ttu-id="7a534-153">FQDN</span><span class="sxs-lookup"><span data-stu-id="7a534-153">FQDN</span></span>|<span data-ttu-id="7a534-154">O nome FQDN do SBC</span><span class="sxs-lookup"><span data-stu-id="7a534-154">The FQDN name of the SBC</span></span> |<span data-ttu-id="7a534-155">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7a534-155">None</span></span>|<span data-ttu-id="7a534-156">Nome do NoneFQDN, limite de 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="7a534-156">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="7a534-157">Cadeia de caracteres, lista de caracteres permitidos e não permitidos em [convenções de nomenclatura no Active Directory para computadores, domínios, sites e UOs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="7a534-157">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="7a534-158">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-158">No</span></span>|<span data-ttu-id="7a534-159">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="7a534-159">MediaBypass</span></span> |<span data-ttu-id="7a534-160">O parâmetro reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="7a534-160">The parameter reserved for future use.</span></span> <span data-ttu-id="7a534-161">O parâmetro indicado do SBC dá suporte à bypass de mídia e o administrador deseja usá-la.</span><span class="sxs-lookup"><span data-stu-id="7a534-161">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="7a534-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7a534-162">None</span></span>|<span data-ttu-id="7a534-163">True</span><span class="sxs-lookup"><span data-stu-id="7a534-163">True</span></span><br/><span data-ttu-id="7a534-164">False</span><span class="sxs-lookup"><span data-stu-id="7a534-164">False</span></span>|<span data-ttu-id="7a534-165">Boolean</span><span class="sxs-lookup"><span data-stu-id="7a534-165">Boolean</span></span>|
|<span data-ttu-id="7a534-166">Sim</span><span class="sxs-lookup"><span data-stu-id="7a534-166">Yes</span></span>|<span data-ttu-id="7a534-167">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="7a534-167">SipSignallingPort</span></span> |<span data-ttu-id="7a534-168">Porta de escuta usada para comunicação com serviços de roteamento direto usando o protocolo TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="7a534-168">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="7a534-169">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7a534-169">None</span></span>|<span data-ttu-id="7a534-170">Qualquer porta</span><span class="sxs-lookup"><span data-stu-id="7a534-170">Any port</span></span>|<span data-ttu-id="7a534-171">0 a 65535</span><span class="sxs-lookup"><span data-stu-id="7a534-171">0 to 65535</span></span> |
|<span data-ttu-id="7a534-172">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-172">No</span></span>|<span data-ttu-id="7a534-173">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="7a534-173">FailoverTimeSeconds</span></span> |<span data-ttu-id="7a534-174">Quando definido como 10 (valor padrão), as chamadas de saída que não são respondidas pelo gateway em 10 segundos são roteadas para o próximo tronco disponível; Se não houver troncos adicionais, a chamada será automaticamente cancelada.</span><span class="sxs-lookup"><span data-stu-id="7a534-174">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="7a534-175">Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="7a534-175">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="7a534-176">O valor padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="7a534-176">The default value is 10.</span></span>|<span data-ttu-id="7a534-177">254</span><span class="sxs-lookup"><span data-stu-id="7a534-177">10</span></span>|<span data-ttu-id="7a534-178">Número</span><span class="sxs-lookup"><span data-stu-id="7a534-178">Number</span></span>|<span data-ttu-id="7a534-179">Núm</span><span class="sxs-lookup"><span data-stu-id="7a534-179">Int</span></span>|
|<span data-ttu-id="7a534-180">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-180">No</span></span>|<span data-ttu-id="7a534-181">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="7a534-181">ForwardCallHistory</span></span> |<span data-ttu-id="7a534-182">Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.</span><span class="sxs-lookup"><span data-stu-id="7a534-182">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="7a534-183">Se habilitado, o proxy PSTN do Office 365 envia dois cabeçalhos: histórico-informações e referenciado por.</span><span class="sxs-lookup"><span data-stu-id="7a534-183">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="7a534-184">O valor padrão é **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="7a534-184">The default value is **False** ($False).</span></span> |<span data-ttu-id="7a534-185">False</span><span class="sxs-lookup"><span data-stu-id="7a534-185">False</span></span>|<span data-ttu-id="7a534-186">True</span><span class="sxs-lookup"><span data-stu-id="7a534-186">True</span></span><br/><span data-ttu-id="7a534-187">False</span><span class="sxs-lookup"><span data-stu-id="7a534-187">False</span></span>|<span data-ttu-id="7a534-188">Boolean</span><span class="sxs-lookup"><span data-stu-id="7a534-188">Boolean</span></span>|
|<span data-ttu-id="7a534-189">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-189">No</span></span>|<span data-ttu-id="7a534-190">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="7a534-190">ForwardPAI</span></span>|<span data-ttu-id="7a534-191">Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada.</span><span class="sxs-lookup"><span data-stu-id="7a534-191">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="7a534-192">O header PAI oferece uma forma de verificar a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="7a534-192">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="7a534-193">Se habilitado, o cabeçalho de identificação privacidade: também será enviado.</span><span class="sxs-lookup"><span data-stu-id="7a534-193">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="7a534-194">O valor padrão é **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="7a534-194">The default value is **False** ($False).</span></span>|<span data-ttu-id="7a534-195">False</span><span class="sxs-lookup"><span data-stu-id="7a534-195">False</span></span>|<span data-ttu-id="7a534-196">True</span><span class="sxs-lookup"><span data-stu-id="7a534-196">True</span></span><br/><span data-ttu-id="7a534-197">False</span><span class="sxs-lookup"><span data-stu-id="7a534-197">False</span></span>|<span data-ttu-id="7a534-198">Boolean</span><span class="sxs-lookup"><span data-stu-id="7a534-198">Boolean</span></span>|
|<span data-ttu-id="7a534-199">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-199">No</span></span>|<span data-ttu-id="7a534-200">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="7a534-200">SendSIPOptions</span></span> |<span data-ttu-id="7a534-201">Define se um SBC irá ou não enviará as opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="7a534-201">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="7a534-202">Se desabilitado, o SBC será excluído do sistema de monitoramento e alerta.</span><span class="sxs-lookup"><span data-stu-id="7a534-202">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="7a534-203">É altamente recomendável que você ative as opções do SIP.</span><span class="sxs-lookup"><span data-stu-id="7a534-203">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="7a534-204">O valor padrão é **true**.</span><span class="sxs-lookup"><span data-stu-id="7a534-204">Default value is **True**.</span></span> |<span data-ttu-id="7a534-205">True</span><span class="sxs-lookup"><span data-stu-id="7a534-205">True</span></span>|<span data-ttu-id="7a534-206">True</span><span class="sxs-lookup"><span data-stu-id="7a534-206">True</span></span><br/><span data-ttu-id="7a534-207">False</span><span class="sxs-lookup"><span data-stu-id="7a534-207">False</span></span>|<span data-ttu-id="7a534-208">Boolean</span><span class="sxs-lookup"><span data-stu-id="7a534-208">Boolean</span></span>|
|<span data-ttu-id="7a534-209">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-209">No</span></span>|<span data-ttu-id="7a534-210">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="7a534-210">MaxConcurrentSessions</span></span> |<span data-ttu-id="7a534-211">Usado pelo sistema de alerta.</span><span class="sxs-lookup"><span data-stu-id="7a534-211">Used by alerting system.</span></span> <span data-ttu-id="7a534-212">Quando qualquer valor for definido, o sistema de alerta gerará um alerta para o administrador do locatário quando o número da sessão simultânea for 90% ou superior a este valor.</span><span class="sxs-lookup"><span data-stu-id="7a534-212">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="7a534-213">Se o parâmetro não estiver definido, os alertas não serão gerados.</span><span class="sxs-lookup"><span data-stu-id="7a534-213">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="7a534-214">No entanto, o sistema de monitoramento reportará o número da sessão simultânea a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="7a534-214">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="7a534-215">Vazio</span><span class="sxs-lookup"><span data-stu-id="7a534-215">Null</span></span>|<span data-ttu-id="7a534-216">Vazio</span><span class="sxs-lookup"><span data-stu-id="7a534-216">Null</span></span><br/><span data-ttu-id="7a534-217">de 1 a 100.000</span><span class="sxs-lookup"><span data-stu-id="7a534-217">1 to 100,000</span></span> ||
|<span data-ttu-id="7a534-218">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-218">No</span></span>|<span data-ttu-id="7a534-219">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="7a534-219">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="7a534-220">Permite a seleção de caminho para mídia manualmente.</span><span class="sxs-lookup"><span data-stu-id="7a534-220">Allows selecting path for media manually.</span></span> <span data-ttu-id="7a534-221">O roteamento direto atribui um datacenter para caminho de mídia com base no IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-221">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="7a534-222">Sempre selecionamos mais próximo ao Datacenter do SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-222">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="7a534-223">No entanto, em alguns casos, um IP público de, por exemplo, um intervalo dos EUA pode ser atribuído a um SBC localizado na Europa.</span><span class="sxs-lookup"><span data-stu-id="7a534-223">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="7a534-224">Nesse caso, vamos usar o caminho de mídia ideal.</span><span class="sxs-lookup"><span data-stu-id="7a534-224">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="7a534-225">Esse parâmetro permite definir manualmente a região preferida para tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="7a534-225">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="7a534-226">Recomendamos configurar esse parâmetro apenas se os logs de chamada indicar claramente que a atribuição automática do Media Center para o caminho de mídia não atribui o mais próximo possível ao Datacenter do SBC.</span><span class="sxs-lookup"><span data-stu-id="7a534-226">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="7a534-227">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7a534-227">None</span></span>|<span data-ttu-id="7a534-228">Códigos de país no formato ISO</span><span class="sxs-lookup"><span data-stu-id="7a534-228">Country codes in ISO format</span></span>||
|<span data-ttu-id="7a534-229">Não</span><span class="sxs-lookup"><span data-stu-id="7a534-229">No</span></span>|<span data-ttu-id="7a534-230">Habilitado</span><span class="sxs-lookup"><span data-stu-id="7a534-230">Enabled</span></span>|<span data-ttu-id="7a534-231">Usado para habilitar este SBC para chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="7a534-231">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="7a534-232">Pode ser usado para remover temporariamente o SBC, enquanto ele está sendo atualizado ou durante a manutenção.</span><span class="sxs-lookup"><span data-stu-id="7a534-232">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="7a534-233">False</span><span class="sxs-lookup"><span data-stu-id="7a534-233">False</span></span>|<span data-ttu-id="7a534-234">True</span><span class="sxs-lookup"><span data-stu-id="7a534-234">True</span></span><br/><span data-ttu-id="7a534-235">False</span><span class="sxs-lookup"><span data-stu-id="7a534-235">False</span></span>|<span data-ttu-id="7a534-236">Boolean</span><span class="sxs-lookup"><span data-stu-id="7a534-236">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="7a534-237">Verificar o emparelhamento de SBC</span><span class="sxs-lookup"><span data-stu-id="7a534-237">Verify the SBC pairing</span></span> 

<span data-ttu-id="7a534-238">Verifique a conexão:</span><span class="sxs-lookup"><span data-stu-id="7a534-238">Verify the connection:</span></span> 
- <span data-ttu-id="7a534-239">Verifique se o SBC está na lista de SBCs emparelhado.</span><span class="sxs-lookup"><span data-stu-id="7a534-239">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="7a534-240">Validar opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="7a534-240">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="7a534-241">Validar se o SBC estiver na lista de SBCs emparelhado</span><span class="sxs-lookup"><span data-stu-id="7a534-241">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="7a534-242">Depois de emparelhar o SBC, valide se o SBC está presente na lista de SBCs emparelhada executando o seguinte comando em uma sessão remota do PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="7a534-242">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="7a534-243">O gateway emparelhado deve aparecer na lista, conforme mostrado no exemplo abaixo, e verificar se o parâmetro *habilitado* exibe o valor **true**.</span><span class="sxs-lookup"><span data-stu-id="7a534-243">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="7a534-244">Dique</span><span class="sxs-lookup"><span data-stu-id="7a534-244">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="7a534-245">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="7a534-245">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="7a534-246">Validar o fluxo de opções do SIP</span><span class="sxs-lookup"><span data-stu-id="7a534-246">Validate SIP Options flow</span></span> 

<span data-ttu-id="7a534-247">Para validar o emparelhamento usando as opções de SIP de saída, use a interface de gerenciamento do SBC e confirme se o SBC recebe as respostas de OK do 200 para suas mensagens de opções de saída.</span><span class="sxs-lookup"><span data-stu-id="7a534-247">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="7a534-248">Quando o roteamento direto vê as opções de entrada, ele começará a enviar mensagens de opções de SIP de saída para o FQDN do SBC configurado no campo de cabeçalho de contato na mensagem de opções de entrada.</span><span class="sxs-lookup"><span data-stu-id="7a534-248">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="7a534-249">Para validar o emparelhamento usando as opções do SIP de entrada, use a interface de gerenciamento do SBC e veja se o SBC envia uma resposta às mensagens de opções que chegam do roteamento direto e que o código de resposta que ele envia é 200 OK.</span><span class="sxs-lookup"><span data-stu-id="7a534-249">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="7a534-250">Habilitar usuários para o serviço de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="7a534-250">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="7a534-251">Quando estiver pronto para habilitar os usuários para o serviço de roteamento direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a534-251">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="7a534-252">Criar um usuário no Office 365 e atribuir uma licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="7a534-252">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="7a534-253">Certifique-se de que o usuário esteja hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="7a534-253">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="7a534-254">Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz.</span><span class="sxs-lookup"><span data-stu-id="7a534-254">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="7a534-255">Configurar o roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="7a534-255">Configure voice routing.</span></span> <span data-ttu-id="7a534-256">A rota é validada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a534-256">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="7a534-257">Criar um usuário no Office 365 e atribuir a licença</span><span class="sxs-lookup"><span data-stu-id="7a534-257">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="7a534-258">Há duas opções para criar um novo usuário no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a534-258">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="7a534-259">No entanto, recomendamos que sua organização selecione e use uma opção para evitar problemas de roteamento:</span><span class="sxs-lookup"><span data-stu-id="7a534-259">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="7a534-260">Crie o usuário no Active Directory local e sincronize o usuário com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="7a534-260">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="7a534-261">Confira [integrar seus diretórios locais com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="7a534-261">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="7a534-262">Crie o usuário diretamente no portal do administrador do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a534-262">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="7a534-263">Consulte [Adicionar usuários individualmente ou em massa ao Office 365-ajuda para administradores](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="7a534-263">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="7a534-264">Se sua implantação do Skype for Business Online for coexistente com o Skype for Business 2015 ou o Lync 2010/2013 local, a única opção compatível é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (opção 1).</span><span class="sxs-lookup"><span data-stu-id="7a534-264">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="7a534-265">Licenças necessárias:</span><span class="sxs-lookup"><span data-stu-id="7a534-265">Required licenses:</span></span> 

- <span data-ttu-id="7a534-266">Office 365 Enterprise E3 (incluindo SfB Plan2, Exchange Plan2 e equipes) + sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="7a534-266">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="7a534-267">Office 365 Enterprise E5 (incluindo SfB Plan2, Exchange Plan2, equipes e sistema telefônico)</span><span class="sxs-lookup"><span data-stu-id="7a534-267">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="7a534-268">Licenças opcionais:</span><span class="sxs-lookup"><span data-stu-id="7a534-268">Optional licenses:</span></span> 

- <span data-ttu-id="7a534-269">Plano de chamada</span><span class="sxs-lookup"><span data-stu-id="7a534-269">Calling Plan</span></span> 
- <span data-ttu-id="7a534-270">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="7a534-270">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="7a534-271">Certifique-se de que o usuário esteja hospedado no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a534-271">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="7a534-272">O roteamento direto exige que o usuário seja hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="7a534-272">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="7a534-273">Você pode verificar isso examinando o parâmetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="7a534-273">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="7a534-274">Ele precisa ter um valor no domínio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7a534-274">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="7a534-275">Conecte-se ao PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="7a534-275">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="7a534-276">Execute o comando:</span><span class="sxs-lookup"><span data-stu-id="7a534-276">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="7a534-277">Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz</span><span class="sxs-lookup"><span data-stu-id="7a534-277">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="7a534-278">Depois de criar o usuário e atribuir uma licença, a próxima etapa é configurar o número de telefone e o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="7a534-278">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="7a534-279">Isso pode ser feito em uma etapa.</span><span class="sxs-lookup"><span data-stu-id="7a534-279">This can be done in one step.</span></span> 

<span data-ttu-id="7a534-280">Para adicionar o número de telefone e habilitar o correio de voz:</span><span class="sxs-lookup"><span data-stu-id="7a534-280">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="7a534-281">Conectar-se a uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a534-281">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="7a534-282">Digite o comando:</span><span class="sxs-lookup"><span data-stu-id="7a534-282">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="7a534-283">Por exemplo, para adicionar um número de telefone para o usuário "Spencer baixo", você deve digitar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7a534-283">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="7a534-284">O número de telefone usado deve ser configurado como um número de telefone completo E. 164 com código de país.</span><span class="sxs-lookup"><span data-stu-id="7a534-284">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="7a534-285">Se o número de telefone do usuário for gerenciado localmente, use o Shell de gerenciamento do Skype for Business local ou o painel de controle para configurar o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="7a534-285">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="7a534-286">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="7a534-286">Configure Voice Routing</span></span> 

<span data-ttu-id="7a534-287">O sistema telefônico da Microsoft tem um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC específico com base em:</span><span class="sxs-lookup"><span data-stu-id="7a534-287">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="7a534-288">Padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="7a534-288">Called number pattern</span></span> 
- <span data-ttu-id="7a534-289">Chamado de padrão de número + usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="7a534-289">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="7a534-290">A SBCs pode ser designada como ativa e de backup.</span><span class="sxs-lookup"><span data-stu-id="7a534-290">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="7a534-291">Isso significa que, quando o SBC que é configurado como ativo para este padrão de número ou de número + usuário específico não está disponível, as chamadas são roteadas para um SBC de backup.</span><span class="sxs-lookup"><span data-stu-id="7a534-291">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="7a534-292">O encaminhamento de chamadas é composto pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="7a534-292">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="7a534-293">Política de roteamento de voz – contêiner para usos de PSTN; pode ser atribuído a um usuário ou a vários usuários</span><span class="sxs-lookup"><span data-stu-id="7a534-293">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="7a534-294">Usos de PSTN – contêiner para roteiros de voz e usos de PSTN; pode ser compartilhado em diferentes políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="7a534-294">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="7a534-295">Rotas de voz – o padrão de número e o conjunto de gateways PSTN online a serem usados para chamadas em que o número de chamada corresponde ao padrão</span><span class="sxs-lookup"><span data-stu-id="7a534-295">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="7a534-296">Gateway PSTN online-o ponteiro para um SBC também armazena a configuração aplicada quando a chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (PAI) ou codecs preferenciais; pode ser adicionado a roteiros de voz</span><span class="sxs-lookup"><span data-stu-id="7a534-296">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="7a534-297">Criando uma política de roteamento de voz com um uso PSTN</span><span class="sxs-lookup"><span data-stu-id="7a534-297">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="7a534-298">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz no fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7a534-298">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="7a534-299">**Fluxo de chamadas 1 (à esquerda):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7a534-299">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="7a534-300">Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="7a534-300">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="7a534-301">**Fluxo de chamadas 2 (à direita):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7a534-301">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="7a534-302">Se nenhum SBC estiver disponível, a rota com prioridade menor será tentada (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="7a534-302">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="7a534-303">Se nenhum dos SBCs estiver disponível, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="7a534-303">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="7a534-305">Nos dois exemplos, enquanto a rota de voz é atribuída às prioridades, o SBCs nos roteiros é tentado em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="7a534-305">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7a534-306">A menos que o usuário também tenha uma licença do plano de chamadas da Microsoft, as chamadas para qualquer número, exceto números que correspondam aos padrões + 1 425 XXX XX XX ou + 1 206 XXX XX XX no exemplo de configuração são descartados.</span><span class="sxs-lookup"><span data-stu-id="7a534-306">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="7a534-307">Se o usuário tiver uma licença de plano de chamada, a chamada será roteada automaticamente de acordo com as políticas do plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a534-307">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="7a534-308">O plano de chamadas da Microsoft aplica-se automaticamente como a última rota para todos os usuários com a licença do plano de chamadas da Microsoft e não requer configuração de roteamento de chamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="7a534-308">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="7a534-309">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números canadenses e números (chamadas que vão para o padrão de número chamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="7a534-309">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="7a534-311">Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="7a534-311">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="7a534-312">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, encaminhe pelo plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a534-312">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="7a534-313">Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="7a534-313">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7a534-314">O valor de prioridade para a rota "Other + 1" não importa nesse caso, pois há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="7a534-314">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="7a534-315">Se um usuário fizer uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiverem indisponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="7a534-315">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="7a534-316">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="7a534-316">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="7a534-317">Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="7a534-317">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="7a534-318">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="7a534-318">**PSTN usage**</span></span>|<span data-ttu-id="7a534-319">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="7a534-319">**Voice route**</span></span>|<span data-ttu-id="7a534-320">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="7a534-320">**Number pattern**</span></span>|<span data-ttu-id="7a534-321">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="7a534-321">**Priority**</span></span>|<span data-ttu-id="7a534-322">**SBC**</span><span class="sxs-lookup"><span data-stu-id="7a534-322">**SBC**</span></span>|<span data-ttu-id="7a534-323">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7a534-323">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a534-324">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="7a534-324">US only</span></span>|<span data-ttu-id="7a534-325">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="7a534-325">"Redmond 1"</span></span>|<span data-ttu-id="7a534-326">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="7a534-326">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7a534-327">1</span><span class="sxs-lookup"><span data-stu-id="7a534-327">1</span></span>|<span data-ttu-id="7a534-328">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-328">sbc1.contoso.biz</span></span><br/><span data-ttu-id="7a534-329">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-329">sbc2.contoso.biz</span></span>|<span data-ttu-id="7a534-330">Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7a534-330">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7a534-331">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="7a534-331">US only</span></span>|<span data-ttu-id="7a534-332">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="7a534-332">"Redmond 2"</span></span>|<span data-ttu-id="7a534-333">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="7a534-333">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7a534-334">2</span><span class="sxs-lookup"><span data-stu-id="7a534-334">2</span></span>|<span data-ttu-id="7a534-335">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-335">sbc3.contoso.biz</span></span><br/><span data-ttu-id="7a534-336">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-336">sbc4.contoso.biz</span></span>|<span data-ttu-id="7a534-337">Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7a534-337">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7a534-338">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="7a534-338">US only</span></span>|<span data-ttu-id="7a534-339">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="7a534-339">"Other +1"</span></span>|<span data-ttu-id="7a534-340">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="7a534-340">^\\+1(\d{10})$</span></span>|<span data-ttu-id="7a534-341">3</span><span class="sxs-lookup"><span data-stu-id="7a534-341">3</span></span>|<span data-ttu-id="7a534-342">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-342">sbc5.contoso.biz</span></span><br/><span data-ttu-id="7a534-343">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-343">sbc6.contoso.biz</span></span>|<span data-ttu-id="7a534-344">Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="7a534-344">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="7a534-345">Todas as rotas são associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado apenas à política de roteamento de voz "apenas para os EUA".</span><span class="sxs-lookup"><span data-stu-id="7a534-345">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="7a534-346">Neste exemplo, a política de roteamento de voz é atribuída ao usuário Spencer baixo.</span><span class="sxs-lookup"><span data-stu-id="7a534-346">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="7a534-347">Exemplos de roteiros de chamada</span><span class="sxs-lookup"><span data-stu-id="7a534-347">Examples of call routes</span></span>

<span data-ttu-id="7a534-348">No exemplo a seguir, demonstramos como configurar rotas, usos de PSTN e políticas de roteamento, e atribuímos a política ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7a534-348">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="7a534-349">**Etapa 1:** Crie o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="7a534-349">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="7a534-350">Em uma sessão do PowerShell remoto do Skype for Business, digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-350">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="7a534-351">Valide se o uso foi criado inserindo:</span><span class="sxs-lookup"><span data-stu-id="7a534-351">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="7a534-352">Que retorna uma lista de nomes que podem estar truncados:</span><span class="sxs-lookup"><span data-stu-id="7a534-352">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="7a534-353">No exemplo abaixo, você pode ver o resultado do comando `(Get-CSOnlinePSTNUsage).usage` running the PowerShell para exibir nomes completos (não truncados).</span><span class="sxs-lookup"><span data-stu-id="7a534-353">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="7a534-354">**Etapa 2:** Em uma sessão do PowerShell no Skype for Business Online, crie três roteiros: 1, Redmond 2 e outros + 1, conforme detalhado na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="7a534-354">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="7a534-355">Para criar a rota "Redmond 1", digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-355">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="7a534-356">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="7a534-356">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="7a534-357">Para criar a rota Redmond 2, digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-357">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="7a534-358">Para criar a outra rota + 1, digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-358">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="7a534-359">Certifique-se de que sua expressão regular no atributo NumberPattern é uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="7a534-359">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="7a534-360">Você pode testá-lo usando este site:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="7a534-360">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="7a534-361">Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="7a534-361">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="7a534-362">Rotear todas as chamadas para o mesmo SBC</span><span class="sxs-lookup"><span data-stu-id="7a534-362">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="7a534-363">Valide se você configurou corretamente a rota executando o comando `Get-CSOnlineVoiceRoute` do PowerShell usando as opções, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="7a534-363">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="7a534-364">Que deve retornar:</span><span class="sxs-lookup"><span data-stu-id="7a534-364">Which should return:</span></span>
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

<span data-ttu-id="7a534-365">No exemplo, a rota "Other + 1" foi automaticamente atribuída à prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="7a534-365">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="7a534-366">**Etapa 3:** Crie uma política de roteamento de voz "apenas EUA" e adicione à política o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="7a534-366">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="7a534-367">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-367">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="7a534-368">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="7a534-368">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="7a534-369">**Etapa 4:** Conceder ao usuário Spencer uma política de roteamento de voz baixa usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a534-369">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="7a534-370">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-370">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="7a534-371">Valide a atribuição de política inserindo este comando:</span><span class="sxs-lookup"><span data-stu-id="7a534-371">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="7a534-372">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="7a534-372">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="7a534-373">Criando uma política de roteamento de voz com vários usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="7a534-373">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="7a534-374">A política de roteamento de voz criada anteriormente só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do plano de chamadas da Microsoft também seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7a534-374">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="7a534-375">No exemplo a seguir, você pode criar a política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="7a534-375">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="7a534-376">A política reutiliza o uso de PSTN "EUA e Canadá" criado no exemplo anterior, bem como o novo uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="7a534-376">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="7a534-377">Isso roteia todas as outras chamadas para a SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7a534-377">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="7a534-378">Os exemplos mostrados atribuir apenas a política US para o usuário "Spencer baixo" e sem restrições ao usuário "John Woods".</span><span class="sxs-lookup"><span data-stu-id="7a534-378">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="7a534-379">Spencer baixo – chamadas permitidas somente para números canadenses e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="7a534-379">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="7a534-380">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBC deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="7a534-380">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="7a534-381">Os números que não são dos EUA não serão roteados, a menos que a licença do plano de chamada seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7a534-381">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="7a534-382">John Woods – chamadas permitidas para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="7a534-382">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="7a534-383">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBC deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="7a534-383">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="7a534-384">Os números que não são dos EUA serão roteados via sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7a534-384">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário Spencer baixo](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="7a534-386">Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="7a534-386">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="7a534-387">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, encaminhe pelo plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a534-387">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="7a534-388">Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="7a534-388">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="7a534-390">A tabela a seguir resume as designações de uso de política de roteamento "sem restrições" e rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="7a534-390">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="7a534-391">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="7a534-391">**PSTN usage**</span></span>|<span data-ttu-id="7a534-392">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="7a534-392">**Voice route**</span></span>|<span data-ttu-id="7a534-393">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="7a534-393">**Number pattern**</span></span>|<span data-ttu-id="7a534-394">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="7a534-394">**Priority**</span></span>|<span data-ttu-id="7a534-395">**SBC**</span><span class="sxs-lookup"><span data-stu-id="7a534-395">**SBC**</span></span>|<span data-ttu-id="7a534-396">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7a534-396">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a534-397">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="7a534-397">US Only</span></span>|<span data-ttu-id="7a534-398">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="7a534-398">"Redmond 1"</span></span>|<span data-ttu-id="7a534-399">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="7a534-399">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7a534-400">1</span><span class="sxs-lookup"><span data-stu-id="7a534-400">1</span></span>|<span data-ttu-id="7a534-401">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-401">sbc1.contoso.biz</span></span><br/><span data-ttu-id="7a534-402">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-402">sbc2.contoso.biz</span></span>|<span data-ttu-id="7a534-403">Roteiro ativo para números de chamada + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7a534-403">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7a534-404">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="7a534-404">US Only</span></span>|<span data-ttu-id="7a534-405">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="7a534-405">"Redmond 2"</span></span>|<span data-ttu-id="7a534-406">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="7a534-406">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7a534-407">2</span><span class="sxs-lookup"><span data-stu-id="7a534-407">2</span></span>|<span data-ttu-id="7a534-408">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-408">sbc3.contoso.biz</span></span><br/><span data-ttu-id="7a534-409">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-409">sbc4.contoso.biz</span></span>|<span data-ttu-id="7a534-410">Rota de backup para números do chamado + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7a534-410">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7a534-411">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="7a534-411">US Only</span></span>|<span data-ttu-id="7a534-412">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="7a534-412">"Other +1"</span></span>|<span data-ttu-id="7a534-413">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="7a534-413">^\\+1(\d{10})$</span></span>|<span data-ttu-id="7a534-414">3</span><span class="sxs-lookup"><span data-stu-id="7a534-414">3</span></span>|<span data-ttu-id="7a534-415">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-415">sbc5.contoso.biz</span></span><br/><span data-ttu-id="7a534-416">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-416">sbc6>.contoso.biz</span></span>|<span data-ttu-id="7a534-417">Rota para números de chamada + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="7a534-417">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="7a534-418">International</span><span class="sxs-lookup"><span data-stu-id="7a534-418">International</span></span>|<span data-ttu-id="7a534-419">International</span><span class="sxs-lookup"><span data-stu-id="7a534-419">International</span></span>|<span data-ttu-id="7a534-420">\d +</span><span class="sxs-lookup"><span data-stu-id="7a534-420">\d+</span></span>|<span data-ttu-id="7a534-421">4</span><span class="sxs-lookup"><span data-stu-id="7a534-421">4</span></span>|<span data-ttu-id="7a534-422">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-422">sbc2.contoso.biz</span></span><br/><span data-ttu-id="7a534-423">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7a534-423">sbc5.contoso.biz</span></span>|<span data-ttu-id="7a534-424">Rota para qualquer padrão de número</span><span class="sxs-lookup"><span data-stu-id="7a534-424">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="7a534-425">A ordem dos usos de PSTN nas políticas de roteamento de voz é crítica.</span><span class="sxs-lookup"><span data-stu-id="7a534-425">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="7a534-426">Os usos são aplicados em ordem e, se for encontrada uma coincidência no primeiro uso, outros usos nunca serão avaliados.</span><span class="sxs-lookup"><span data-stu-id="7a534-426">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="7a534-427">O uso de PSTN "internacional" deve ser colocado após o uso de PSTN "somente EUA".</span><span class="sxs-lookup"><span data-stu-id="7a534-427">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="7a534-428">Para alterar a ordem dos usos de PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="7a534-428">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="7a534-429">Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "internacional" segundo a execução da ordem inversa:</span><span class="sxs-lookup"><span data-stu-id="7a534-429">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="7a534-430">A prioridade para as rotas de voz "Other + 1" e "International" são atribuídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a534-430">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="7a534-431">Não importa tão tempo que tenham prioridades menores do que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="7a534-431">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="7a534-432">Exemplo de política de roteamento de voz para usuário John Woods</span><span class="sxs-lookup"><span data-stu-id="7a534-432">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="7a534-433">As etapas para criar o uso de PSTN "internacional", a rota de voz "internacional", a política de roteamento de voz "sem restrições" e, em seguida, atribuí-lo ao usuário "John Woods" são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="7a534-433">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="7a534-434">Primeiro, crie o uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="7a534-434">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="7a534-435">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="7a534-435">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="7a534-436">Em seguida, crie a nova rota de voz "internacional".</span><span class="sxs-lookup"><span data-stu-id="7a534-436">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="7a534-437">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="7a534-437">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="7a534-438">Em seguida, crie uma política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="7a534-438">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="7a534-439">O uso de PSTN "Redmond 1" e "Redmond" é reutilizado nesta política de roteamento de voz para preservar a manipulação especial de chamadas para número "+ 1 425 XXX XX XX XX" e "+ 1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="7a534-439">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="7a534-440">Que retorna</span><span class="sxs-lookup"><span data-stu-id="7a534-440">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="7a534-441">Atribua a política de roteamento de voz ao usuário "John Woods" usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="7a534-441">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="7a534-442">Em seguida, verifique a tarefa usando o comando:</span><span class="sxs-lookup"><span data-stu-id="7a534-442">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="7a534-443">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="7a534-443">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="7a534-444">O resultado é que a política de voz aplicada a chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para chamadas para os EUA, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="7a534-444">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="7a534-445">Configurar o Microsoft Teams como o cliente de chamadas preferencial para usuários</span><span class="sxs-lookup"><span data-stu-id="7a534-445">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="7a534-446">O roteamento direto só direciona chamadas para usuários e para usuários se usarem o cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="7a534-446">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="7a534-447">Se a sua organização usa apenas o Microsoft Teams, a configuração do modo "somente equipes" na política de atualização é recomendada.</span><span class="sxs-lookup"><span data-stu-id="7a534-447">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="7a534-448">Se a sua organização usa o Skype for Business Server ou o Skype for Business Online, consulte o artigo a seguir para obter mais informações e selecione a opção apropriada: [entender a coexistência e atualizar a viagem para o Skype for Business e](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)o Teams.</span><span class="sxs-lookup"><span data-stu-id="7a534-448">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="7a534-449">Confira também</span><span class="sxs-lookup"><span data-stu-id="7a534-449">See also</span></span>

[<span data-ttu-id="7a534-450">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="7a534-450">Plan Direct Routing</span></span>](direct-routing-plan.md)
