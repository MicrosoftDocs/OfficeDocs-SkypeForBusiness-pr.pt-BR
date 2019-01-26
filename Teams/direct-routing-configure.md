---
title: Configurar o Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Saiba como configurar o roteamento direto do Microsoft Phone System.
ms.openlocfilehash: 565d25566843a507cb875eb96f32531d2ee77caf
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562819"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="7d67e-103">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="7d67e-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="7d67e-104">Assista a sessão de seguir para saber mais sobre os benefícios do direto, roteamento, como planejar para ele e como implantá-la: [Roteamento direta em equipes da Microsoft](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="7d67e-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="7d67e-105">Se você não tiver feito isso, leia [Planejar roteamento direto](direct-routing-plan.md) para os pré-requisitos e para examinar outras etapas você precisará executar antes de configurar sua rede Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="7d67e-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="7d67e-106">Este artigo descreve como configurar o roteamento direto do Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="7d67e-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="7d67e-107">Ele detalha como emparelhar um suportados borda controlador sessão (SBC) roteamento direto e como configurar usuários Teams da Microsoft para usar o roteamento diretas para conectar-se para a comutação telefônica PSTN (rede pública).</span><span class="sxs-lookup"><span data-stu-id="7d67e-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7d67e-108">Para concluir as etapas explicadas neste artigo, os administradores precisam de familiaridade com os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d67e-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="7d67e-109">Para obter mais informações sobre como usar o PowerShell, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d67e-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="7d67e-110">Recomendamos que você confirme que seu SBC já foi configurado conforme recomendado pelo seu fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="7d67e-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="7d67e-111">Documentação de implantação AudioCodes</span><span class="sxs-lookup"><span data-stu-id="7d67e-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="7d67e-112">Documentação de implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="7d67e-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="7d67e-113">Você pode configurar seu sistema telefônico de Microsoft e permitem aos usuários utilizar o roteamento direto e depois configurar o Microsoft Teams como o cliente preferencial da chamada ao concluir os procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="7d67e-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="7d67e-114">Emparelhar o SBC com um sistema de telefone da Microsoft e validar o emparelhamento</span><span class="sxs-lookup"><span data-stu-id="7d67e-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="7d67e-115">Habilitar usuários para o serviço de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="7d67e-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="7d67e-116">Certifique-se de que a Microsoft Teams é o cliente preferencial da chamada para os usuários</span><span class="sxs-lookup"><span data-stu-id="7d67e-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="7d67e-117">Emparelhar o SBC ao serviço de roteamento direto do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="7d67e-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="7d67e-118">Estes são os três passos de alto nível para permitem que você conecte ou emparelhar, o SBC à interface de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="7d67e-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="7d67e-119">Conecte-se ao centro de administração do **Skype para Business Online** usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d67e-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="7d67e-120">Par o SBC</span><span class="sxs-lookup"><span data-stu-id="7d67e-120">Pair the SBC</span></span> 
- <span data-ttu-id="7d67e-121">Validar o emparelhamento</span><span class="sxs-lookup"><span data-stu-id="7d67e-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="7d67e-122">Se conectam ao Skype para Business Online usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d67e-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="7d67e-123">Você pode usar uma sessão do PowerShell conectada ao inquilino emparelhar o SBC à interface de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="7d67e-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="7d67e-124">Para abrir uma sessão do PowerShell, execute as etapas descritas em [configurar seu computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d67e-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="7d67e-125">Depois de estabelecer uma sessão PowerShell remota, valide que você pode ver os comandos para gerenciar o SBC.</span><span class="sxs-lookup"><span data-stu-id="7d67e-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="7d67e-126">Para validar os comandos, digite ou copiar/colar nas seguintes na sessão PowerShell e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="7d67e-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="7d67e-127">Seu comando vai retornar as funções de quatro mostradas aqui que permitirá que você gerencie o SBC.</span><span class="sxs-lookup"><span data-stu-id="7d67e-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="7d67e-128">Par o SBC ao inquilino</span><span class="sxs-lookup"><span data-stu-id="7d67e-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="7d67e-129">Para emparelhar o SBC ao inquilino, na sessão PowerShell, digite o seguinte e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="7d67e-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="7d67e-130">É altamente recomendável definir um limite máximo de chamadas na SBC, usando as informações que podem ser encontradas na documentação de SBC.</span><span class="sxs-lookup"><span data-stu-id="7d67e-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="7d67e-131">O limite irá disparar uma notificação se o SBC está no nível de capacidade.</span><span class="sxs-lookup"><span data-stu-id="7d67e-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="7d67e-132">Você só pode emparelhar o SBC se corresponder a um dos domínios registrados no seu locatário, exceto a parte de domínio do seu FQDN \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7d67e-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="7d67e-133">Usando \*. onmicrosoft.com nomes de domínio não é suportado para o nome de SBC FQDN.</span><span class="sxs-lookup"><span data-stu-id="7d67e-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="7d67e-134">Por exemplo, se você tiver dois nomes de domínio:</span><span class="sxs-lookup"><span data-stu-id="7d67e-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="7d67e-135">**Contoso**.com</span><span class="sxs-lookup"><span data-stu-id="7d67e-135">**contoso**.com</span></span><br/><span data-ttu-id="7d67e-136">**Contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7d67e-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="7d67e-137">Para o nome SBC, você pode usar o nome sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7d67e-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="7d67e-138">Se você tentar emparelhar o SBC com sbc.contoso.abc um nome, o sistema não permitirá que você, como o domínio não pertence este locatário.</span><span class="sxs-lookup"><span data-stu-id="7d67e-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="7d67e-139">Retorna:</span><span class="sxs-lookup"><span data-stu-id="7d67e-139">Returns:</span></span>
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
<span data-ttu-id="7d67e-140">Há opções adicionais que podem ser definidas durante o processo de emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="7d67e-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="7d67e-141">No exemplo anterior, no entanto, somente o mínimo necessário parâmetros são mostrados.</span><span class="sxs-lookup"><span data-stu-id="7d67e-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="7d67e-142">A tabela a seguir lista os parâmetros adicionais que você pode usar a configuração de parâmetros para`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="7d67e-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="7d67e-143">Necessário?</span><span class="sxs-lookup"><span data-stu-id="7d67e-143">Required?</span></span>|<span data-ttu-id="7d67e-144">Nome</span><span class="sxs-lookup"><span data-stu-id="7d67e-144">Name</span></span>|<span data-ttu-id="7d67e-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d67e-145">Description</span></span>|<span data-ttu-id="7d67e-146">Padrão</span><span class="sxs-lookup"><span data-stu-id="7d67e-146">Default</span></span>|<span data-ttu-id="7d67e-147">Valores possíveis</span><span class="sxs-lookup"><span data-stu-id="7d67e-147">Possible values</span></span>|<span data-ttu-id="7d67e-148">Tipo e restrições</span><span class="sxs-lookup"><span data-stu-id="7d67e-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d67e-149">Sim</span><span class="sxs-lookup"><span data-stu-id="7d67e-149">Yes</span></span>|<span data-ttu-id="7d67e-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="7d67e-150">FQDN</span></span>|<span data-ttu-id="7d67e-151">O nome do FQDN do SBC</span><span class="sxs-lookup"><span data-stu-id="7d67e-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="7d67e-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7d67e-152">None</span></span>|<span data-ttu-id="7d67e-153">Nome de NoneFQDN, limitar 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="7d67e-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="7d67e-154">Cadeia de caracteres, lista de caracteres permitidos e não permitidos nas [convenções de nomenclatura no Active Directory para computadores, domínios, sites e OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="7d67e-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="7d67e-155">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-155">No</span></span>|<span data-ttu-id="7d67e-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="7d67e-156">MediaBypass</span></span> |<span data-ttu-id="7d67e-157">O parâmetro reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="7d67e-157">The parameter reserved for future use.</span></span> <span data-ttu-id="7d67e-158">Parâmetro indicado do SBC suporta Bypass de mídia e o administrador deseja usá-lo.</span><span class="sxs-lookup"><span data-stu-id="7d67e-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="7d67e-159">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7d67e-159">None</span></span>|<span data-ttu-id="7d67e-160">True</span><span class="sxs-lookup"><span data-stu-id="7d67e-160">True</span></span><br/><span data-ttu-id="7d67e-161">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-161">False</span></span>|<span data-ttu-id="7d67e-162">Booliano</span><span class="sxs-lookup"><span data-stu-id="7d67e-162">Boolean</span></span>|
|<span data-ttu-id="7d67e-163">Sim</span><span class="sxs-lookup"><span data-stu-id="7d67e-163">Yes</span></span>|<span data-ttu-id="7d67e-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="7d67e-164">SipSignallingPort</span></span> |<span data-ttu-id="7d67e-165">Porta de escuta usada para comunicação com os serviços de roteamento direta usando o protocolo de segurança de camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="7d67e-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="7d67e-166">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7d67e-166">None</span></span>|<span data-ttu-id="7d67e-167">Qualquer porta</span><span class="sxs-lookup"><span data-stu-id="7d67e-167">Any port</span></span>|<span data-ttu-id="7d67e-168">0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="7d67e-168">0 to 65535</span></span> |
|<span data-ttu-id="7d67e-169">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-169">No</span></span>|<span data-ttu-id="7d67e-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="7d67e-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="7d67e-171">Quando definido como 10 (valor padrão), chamadas de saída que não for atendidas pelo gateway dentro de 10 segundos são roteadas para o próximo tronco disponível; Se não houver nenhuma troncos adicionais, a chamada será interrompida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7d67e-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="7d67e-172">Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="7d67e-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="7d67e-173">O valor padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="7d67e-173">The default value is 10.</span></span>|<span data-ttu-id="7d67e-174"> 10</span><span class="sxs-lookup"><span data-stu-id="7d67e-174">10</span></span>|<span data-ttu-id="7d67e-175">Número</span><span class="sxs-lookup"><span data-stu-id="7d67e-175">Number</span></span>|<span data-ttu-id="7d67e-176">Int</span><span class="sxs-lookup"><span data-stu-id="7d67e-176">Int</span></span>|
|<span data-ttu-id="7d67e-177">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-177">No</span></span>|<span data-ttu-id="7d67e-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="7d67e-178">ForwardCallHistory</span></span> |<span data-ttu-id="7d67e-179">Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.</span><span class="sxs-lookup"><span data-stu-id="7d67e-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="7d67e-180">Se for habilitada, o Proxy do Office 365 PSTN envia dois cabeçalhos: histórico-info e mencionados por.</span><span class="sxs-lookup"><span data-stu-id="7d67e-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="7d67e-181">O valor padrão é **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="7d67e-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="7d67e-182">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-182">False</span></span>|<span data-ttu-id="7d67e-183">True</span><span class="sxs-lookup"><span data-stu-id="7d67e-183">True</span></span><br/><span data-ttu-id="7d67e-184">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-184">False</span></span>|<span data-ttu-id="7d67e-185">Booliano</span><span class="sxs-lookup"><span data-stu-id="7d67e-185">Boolean</span></span>|
|<span data-ttu-id="7d67e-186">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-186">No</span></span>|<span data-ttu-id="7d67e-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="7d67e-187">ForwardPAI</span></span>|<span data-ttu-id="7d67e-188">Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada.</span><span class="sxs-lookup"><span data-stu-id="7d67e-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="7d67e-189">O header PAI oferece uma forma de verificar a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="7d67e-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="7d67e-190">O valor padrão é **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="7d67e-190">The default value is **False** ($False).</span></span>|<span data-ttu-id="7d67e-191">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-191">False</span></span>|<span data-ttu-id="7d67e-192">True</span><span class="sxs-lookup"><span data-stu-id="7d67e-192">True</span></span><br/><span data-ttu-id="7d67e-193">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-193">False</span></span>|<span data-ttu-id="7d67e-194">Booliano</span><span class="sxs-lookup"><span data-stu-id="7d67e-194">Boolean</span></span>|
|<span data-ttu-id="7d67e-195">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-195">No</span></span>|<span data-ttu-id="7d67e-196">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="7d67e-196">SendSIPOptions</span></span> |<span data-ttu-id="7d67e-197">Define se um SBC será ou não enviará as opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="7d67e-197">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="7d67e-198">Se desabilitada, o SBC será excluído do sistema de monitoramento e alerta.</span><span class="sxs-lookup"><span data-stu-id="7d67e-198">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="7d67e-199">É altamente recomendável que você habilite as opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="7d67e-199">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="7d67e-200">Valor padrão é **True**.</span><span class="sxs-lookup"><span data-stu-id="7d67e-200">Default value is **True**.</span></span> |<span data-ttu-id="7d67e-201">True</span><span class="sxs-lookup"><span data-stu-id="7d67e-201">True</span></span>|<span data-ttu-id="7d67e-202">True</span><span class="sxs-lookup"><span data-stu-id="7d67e-202">True</span></span><br/><span data-ttu-id="7d67e-203">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-203">False</span></span>|<span data-ttu-id="7d67e-204">Booliano</span><span class="sxs-lookup"><span data-stu-id="7d67e-204">Boolean</span></span>|
|<span data-ttu-id="7d67e-205">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-205">No</span></span>|<span data-ttu-id="7d67e-206">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="7d67e-206">MaxConcurrentSessions</span></span> |<span data-ttu-id="7d67e-207">Usada pelo sistema de alertas.</span><span class="sxs-lookup"><span data-stu-id="7d67e-207">Used by alerting system.</span></span> <span data-ttu-id="7d67e-208">Quando nenhum valor for definido, o sistema de alertas irá gerar um alerta ao administrador do locatário quando o número de sessão simultânea é 90% ou maior do que esse valor.</span><span class="sxs-lookup"><span data-stu-id="7d67e-208">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="7d67e-209">Se o parâmetro não for definido, os alertas não serão gerados.</span><span class="sxs-lookup"><span data-stu-id="7d67e-209">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="7d67e-210">No entanto, o sistema de monitoramento irá relatar o número de sessão simultânea a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="7d67e-210">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="7d67e-211">NULL</span><span class="sxs-lookup"><span data-stu-id="7d67e-211">Null</span></span>|<span data-ttu-id="7d67e-212">NULL</span><span class="sxs-lookup"><span data-stu-id="7d67e-212">Null</span></span><br/><span data-ttu-id="7d67e-213">1 a 100.000</span><span class="sxs-lookup"><span data-stu-id="7d67e-213">1 to 100,000</span></span> ||
|<span data-ttu-id="7d67e-214">Não</span><span class="sxs-lookup"><span data-stu-id="7d67e-214">No</span></span>|<span data-ttu-id="7d67e-215">Habilitado \*</span><span class="sxs-lookup"><span data-stu-id="7d67e-215">Enabled\*</span></span>|<span data-ttu-id="7d67e-216">Usado para habilitar este SBC para chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="7d67e-216">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="7d67e-217">Pode ser usado para remover temporariamente o SBC, enquanto ela está sendo atualizada ou durante a manutenção.</span><span class="sxs-lookup"><span data-stu-id="7d67e-217">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="7d67e-218">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-218">False</span></span>|<span data-ttu-id="7d67e-219">True</span><span class="sxs-lookup"><span data-stu-id="7d67e-219">True</span></span><br/><span data-ttu-id="7d67e-220">False</span><span class="sxs-lookup"><span data-stu-id="7d67e-220">False</span></span>|<span data-ttu-id="7d67e-221">Booliano</span><span class="sxs-lookup"><span data-stu-id="7d67e-221">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="7d67e-222">Verifique se o emparelhamento de SBC</span><span class="sxs-lookup"><span data-stu-id="7d67e-222">Verify the SBC pairing</span></span> 

<span data-ttu-id="7d67e-223">Verifique se a conexão:</span><span class="sxs-lookup"><span data-stu-id="7d67e-223">Verify the connection:</span></span> 
- <span data-ttu-id="7d67e-224">Verifique se o SBC está na lista de SBCs emparelhados.</span><span class="sxs-lookup"><span data-stu-id="7d67e-224">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="7d67e-225">Valide as opções de SIP.</span><span class="sxs-lookup"><span data-stu-id="7d67e-225">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="7d67e-226">Validar se o SBC está na lista de SBCs emparelhados</span><span class="sxs-lookup"><span data-stu-id="7d67e-226">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="7d67e-227">Depois de par de SBC, valide que o SBC está presente na lista de SBCs emparelhados executando o seguinte comando em uma sessão PowerShell remota:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="7d67e-227">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="7d67e-228">O gateway emparelhado deve aparecer na lista, conforme mostrado no exemplo a seguir e verifique se o parâmetro *Enabled* exibe o valor **True**.</span><span class="sxs-lookup"><span data-stu-id="7d67e-228">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="7d67e-229">Insira:</span><span class="sxs-lookup"><span data-stu-id="7d67e-229">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="7d67e-230">Qual retorna:</span><span class="sxs-lookup"><span data-stu-id="7d67e-230">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="7d67e-231">Validar o fluxo de SIP Options</span><span class="sxs-lookup"><span data-stu-id="7d67e-231">Validate SIP Options flow</span></span> 

<span data-ttu-id="7d67e-232">Para validar o emparelhamento usando as opções de SIP de saída, use a interface de gerenciamento de SBC e confirme que o SBC recebe 200 respostas Okey às suas mensagens enviadas de opções.</span><span class="sxs-lookup"><span data-stu-id="7d67e-232">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="7d67e-233">Quando o roteamento direto vê as opções de entrada, será iniciado o envio de saída SIP Options mensagens para o FQDN de SBC são configuradas no campo de cabeçalho de contato da mensagem de entrada opções.</span><span class="sxs-lookup"><span data-stu-id="7d67e-233">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="7d67e-234">Para validar o emparelhamento usando as opções de SIP de entrada, use a interface de gerenciamento de SBC e veja o que o SBC envia uma resposta para as mensagens de opções que chegam de roteamento direto e ele envia o código de resposta é 200 Okey.</span><span class="sxs-lookup"><span data-stu-id="7d67e-234">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="7d67e-235">Habilitar usuários para o serviço de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="7d67e-235">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="7d67e-236">Quando você estiver pronto para habilitar usuários para o serviço de roteamento direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7d67e-236">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="7d67e-237">Criar um usuário no Office 365 e atribuir uma licença de sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="7d67e-237">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="7d67e-238">Certifique-se de que o usuário está hospedado no Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="7d67e-238">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="7d67e-239">Configurar o número de telefone e habilitar o enterprise voice e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="7d67e-239">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="7d67e-240">Configure o roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-240">Configure voice routing.</span></span> <span data-ttu-id="7d67e-241">A rota é validada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7d67e-241">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="7d67e-242">Criar um usuário no Office 365 e atribuir a licença</span><span class="sxs-lookup"><span data-stu-id="7d67e-242">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="7d67e-243">Há duas opções para criar um novo usuário no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d67e-243">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="7d67e-244">No entanto, recomendamos que sua organização selecione e usar uma opção para evitar problemas de roteamento:</span><span class="sxs-lookup"><span data-stu-id="7d67e-244">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="7d67e-245">Criar o usuário no Active Directory no local e sincronizar o usuário para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="7d67e-245">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="7d67e-246">Consulte [os diretórios de seu local integra-se com o Windows Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="7d67e-246">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="7d67e-247">Crie o usuário diretamente no Portal do administrador do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d67e-247">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="7d67e-248">Consulte [Adicionar usuários individualmente ou em massa para o Office 365 - ajuda de Admin](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="7d67e-248">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="7d67e-249">Se seu Skype para implantação Business Online co existir com Skype para negócios 2015 ou o Lync 2010/2013 local, a única opção com suporte é criar o usuário no Active Directory no local e sincronizar o usuário para a nuvem (opção 1).</span><span class="sxs-lookup"><span data-stu-id="7d67e-249">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="7d67e-250">Licenças necessárias:</span><span class="sxs-lookup"><span data-stu-id="7d67e-250">Required licenses:</span></span> 

- <span data-ttu-id="7d67e-251">O Office 365 Enterprise E3 (incluindo SfB Plan2, Exchange plano2 e equipes) + sistema de telefone</span><span class="sxs-lookup"><span data-stu-id="7d67e-251">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="7d67e-252">O Office 365 Enterprise E5 (incluindo SfB Plan2, Exchange plano2, equipes e sistema telefônico)</span><span class="sxs-lookup"><span data-stu-id="7d67e-252">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="7d67e-253">Licenças opcionais:</span><span class="sxs-lookup"><span data-stu-id="7d67e-253">Optional licenses:</span></span> 

- <span data-ttu-id="7d67e-254">Chamar o plano</span><span class="sxs-lookup"><span data-stu-id="7d67e-254">Calling Plan</span></span> 
- <span data-ttu-id="7d67e-255">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="7d67e-255">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="7d67e-256">Certifique-se de que o usuário está hospedado no Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="7d67e-256">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="7d67e-257">Roteamento direto exige que o usuário a ser hospedados no Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="7d67e-257">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="7d67e-258">Você pode verificar isso examinando o parâmetro RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="7d67e-258">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="7d67e-259">Ele precisa ter um valor no domínio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7d67e-259">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="7d67e-260">Conecte ao PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="7d67e-260">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="7d67e-261">Execute o comando:</span><span class="sxs-lookup"><span data-stu-id="7d67e-261">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="7d67e-262">Configurar o número de telefone e habilitar o enterprise voice e caixa postal</span><span class="sxs-lookup"><span data-stu-id="7d67e-262">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="7d67e-263">Após ter criado o usuário e atribuiu uma licença, a próxima etapa é configurar sua caixa postal e o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="7d67e-263">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="7d67e-264">Isso pode ser feito em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="7d67e-264">This can be done in one step.</span></span> 

<span data-ttu-id="7d67e-265">Para adicionar o número de telefone e habilitar a caixa postal:</span><span class="sxs-lookup"><span data-stu-id="7d67e-265">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="7d67e-266">Conecte a uma sessão PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="7d67e-266">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="7d67e-267">Insira o comando:</span><span class="sxs-lookup"><span data-stu-id="7d67e-267">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="7d67e-268">Por exemplo, para adicionar um número de telefone para o usuário "Low Silva", digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d67e-268">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="7d67e-269">O número de telefone usado deve ser configurado como um número de telefone e. 164 completo com o código de país.</span><span class="sxs-lookup"><span data-stu-id="7d67e-269">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="7d67e-270">Se o número de telefone do usuário é gerenciado no local, use Skype local para o painel de controle ou o Shell de gerenciamento de negócios para configurar o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="7d67e-270">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="7d67e-271">Configurar o roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="7d67e-271">Configure Voice Routing</span></span> 

<span data-ttu-id="7d67e-272">Sistema de telefone da Microsoft possui um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC específico com base em:</span><span class="sxs-lookup"><span data-stu-id="7d67e-272">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="7d67e-273">Padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="7d67e-273">Called number pattern</span></span> 
- <span data-ttu-id="7d67e-274">Padrão de número chamado + usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="7d67e-274">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="7d67e-275">SBCs podem ser designados como ativos e de backup.</span><span class="sxs-lookup"><span data-stu-id="7d67e-275">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="7d67e-276">Isso significa que quando o SBC que está configurado como ativo para este padrão de número, ou padrão de número + usuário específico, não estiver disponível, então, as chamadas serão roteadas para um SBC backup.</span><span class="sxs-lookup"><span data-stu-id="7d67e-276">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="7d67e-277">Roteamento de chamadas é composto pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="7d67e-277">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="7d67e-278">Política de roteamento de voz – contêiner para usos de PSTN; podem ser atribuídas a um usuário ou a vários usuários</span><span class="sxs-lookup"><span data-stu-id="7d67e-278">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="7d67e-279">Usos da PSTN – contêiner para rotas de voz e usos de PSTN; podem ser compartilhados em diferentes políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="7d67e-279">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="7d67e-280">Rotas – padrão de número e o conjunto de Gateways de PSTN Online para usar para chamadas onde chamar número corresponde ao padrão de voz</span><span class="sxs-lookup"><span data-stu-id="7d67e-280">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="7d67e-281">Gateway PSTN online - ponteiro para um SBC, também armazena a configuração que é aplicada quando a chamada é feita por meio de SBC, como forward P-Asserted-Identity (PAI) ou Codecs preferencial; podem ser adicionados às rotas de voz</span><span class="sxs-lookup"><span data-stu-id="7d67e-281">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="7d67e-282">Criando uma política de roteamento de voz com um uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="7d67e-282">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="7d67e-283">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz no fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7d67e-283">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="7d67e-284">**1 de fluxo de chamada (no lado esquerdo):** Se um usuário faz uma chamada para +1 425 XXX XX XX ou +1 206 XXX XX XX, a chamada é roteada para SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-284">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="7d67e-285">Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="7d67e-285">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="7d67e-286">**2 de fluxo de chamada (à direita):** Se um usuário faz uma chamada para +1 425 XXX XX XX ou +1 206 XXX XX XX, a chamada é encaminhada primeiramente para SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-286">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="7d67e-287">Se nenhuma das SBC estiver disponível, a rota com prioridade mais baixa será tentou (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="7d67e-287">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="7d67e-288">Se nenhum dos SBCs estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="7d67e-288">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="7d67e-290">Nos dois exemplos, enquanto a rota de voz é atribuída prioridades, os SBCs nas rotas são tentados em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="7d67e-290">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7d67e-291">A menos que o usuário também tem uma licença Microsoft chamar planejar, chamadas para qualquer número, exceto os padrões de +1 425 XXX XX XX ou +1 206 XXX XX XX na configuração de exemplo de correspondência de números são colocadas.</span><span class="sxs-lookup"><span data-stu-id="7d67e-291">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="7d67e-292">Se o usuário tem uma licença chamar plano, a chamada automaticamente é roteada de acordo com as políticas do Microsoft chamar plano.</span><span class="sxs-lookup"><span data-stu-id="7d67e-292">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="7d67e-293">O Microsoft chamar planeje automaticamente como a rota de última aplica a todos os usuários com a licença Microsoft chamar planejar e não requer configuração de roteamento de chamada adicional.</span><span class="sxs-lookup"><span data-stu-id="7d67e-293">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="7d67e-294">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outro Estados Unidos e do Canadá número (chamadas que vá para o padrão de número chamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="7d67e-294">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra com uma rota a terceira política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="7d67e-296">Para todas as chamadas, se ambas as licenças (sistema de telefone da Microsoft e chamar plano Microsoft), o usuário tem automático rota será usada.</span><span class="sxs-lookup"><span data-stu-id="7d67e-296">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="7d67e-297">Se nada corresponder os padrões de número em que as rotas de voz online criados pelo administrador, rotear via Microsoft chamar planejar.</span><span class="sxs-lookup"><span data-stu-id="7d67e-297">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="7d67e-298">Se o usuário tiver apenas o Microsoft Phone System, a chamada será interrompida, pois não há regras de correspondência estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7d67e-298">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7d67e-299">A prioridade de valor para a rota "Outros + 1" não importa nesse caso, pois não há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="7d67e-299">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="7d67e-300">Se um usuário faz uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e o sbc6.contoso.biz não estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="7d67e-300">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="7d67e-301">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-301">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="7d67e-302">Neste exemplo, todas as rotas de três fazem parte do uso de PSTN mesmo "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="7d67e-302">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="7d67e-303">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="7d67e-303">**PSTN usage**</span></span>|<span data-ttu-id="7d67e-304">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="7d67e-304">**Voice route**</span></span>|<span data-ttu-id="7d67e-305">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="7d67e-305">**Number pattern**</span></span>|<span data-ttu-id="7d67e-306">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="7d67e-306">**Priority**</span></span>|<span data-ttu-id="7d67e-307">**SBC**</span><span class="sxs-lookup"><span data-stu-id="7d67e-307">**SBC**</span></span>|<span data-ttu-id="7d67e-308">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7d67e-308">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d67e-309">Somente nos EUA</span><span class="sxs-lookup"><span data-stu-id="7d67e-309">US only</span></span>|<span data-ttu-id="7d67e-310">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="7d67e-310">"Redmond 1"</span></span>|<span data-ttu-id="7d67e-311">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="7d67e-311">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7d67e-312">1</span><span class="sxs-lookup"><span data-stu-id="7d67e-312">1</span></span>|<span data-ttu-id="7d67e-313">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-313">sbc1.contoso.biz</span></span><br/><span data-ttu-id="7d67e-314">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-314">sbc2.contoso.biz</span></span>|<span data-ttu-id="7d67e-315">Roteiro ativo para números chamados +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7d67e-315">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7d67e-316">Somente nos EUA</span><span class="sxs-lookup"><span data-stu-id="7d67e-316">US only</span></span>|<span data-ttu-id="7d67e-317">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="7d67e-317">"Redmond 2"</span></span>|<span data-ttu-id="7d67e-318">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="7d67e-318">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7d67e-319">2</span><span class="sxs-lookup"><span data-stu-id="7d67e-319">2</span></span>|<span data-ttu-id="7d67e-320">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-320">sbc3.contoso.biz</span></span><br/><span data-ttu-id="7d67e-321">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-321">sbc4.contoso.biz</span></span>|<span data-ttu-id="7d67e-322">Rota de backup para números chamados +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7d67e-322">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7d67e-323">Somente nos EUA</span><span class="sxs-lookup"><span data-stu-id="7d67e-323">US only</span></span>|<span data-ttu-id="7d67e-324">"Outros + 1"</span><span class="sxs-lookup"><span data-stu-id="7d67e-324">"Other +1"</span></span>|<span data-ttu-id="7d67e-325">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="7d67e-325">^\\+1(\d{10})$</span></span>|<span data-ttu-id="7d67e-326">3</span><span class="sxs-lookup"><span data-stu-id="7d67e-326">3</span></span>|<span data-ttu-id="7d67e-327">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-327">sbc5.contoso.biz</span></span><br/><span data-ttu-id="7d67e-328">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-328">sbc6.contoso.biz</span></span>|<span data-ttu-id="7d67e-329">Encaminhar para números chamados + 1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="7d67e-329">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="7d67e-330">Todas as rotas são associadas com o uso da PSTN "EUA e Canadá" e o uso da PSTN é associado a política de roteamento de voz "Somente nos EUA."</span><span class="sxs-lookup"><span data-stu-id="7d67e-330">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="7d67e-331">Neste exemplo, a política de roteamento de voz é atribuída ao usuário Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="7d67e-331">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="7d67e-332">Exemplos de rotas de chamada</span><span class="sxs-lookup"><span data-stu-id="7d67e-332">Examples of call routes</span></span>

<span data-ttu-id="7d67e-333">No exemplo a seguir, podemos Demonstre como configurar rotas, usos da PSTN e políticas de roteamento e atribuímos a política ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7d67e-333">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="7d67e-334">**Etapa 1:** Crie o uso da PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="7d67e-334">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="7d67e-335">Em um Skype para sessão de negócios o PowerShell remoto, digite:</span><span class="sxs-lookup"><span data-stu-id="7d67e-335">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="7d67e-336">Valide se o uso foi criado digitando:</span><span class="sxs-lookup"><span data-stu-id="7d67e-336">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="7d67e-337">Qual retorna uma lista de nomes que pode estar truncada:</span><span class="sxs-lookup"><span data-stu-id="7d67e-337">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="7d67e-338">No exemplo a seguir, é possível ver o resultado da execução do comando do PowerShell `(Get-CSOnlinePSTNUsage).usage` para exibir nomes completos (não truncados).</span><span class="sxs-lookup"><span data-stu-id="7d67e-338">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="7d67e-339">**Etapa 2:** Em uma sessão do PowerShell no Skype para Business Online, crie três rotas: Redmond 1, Redmond 2 e outros + 1, conforme detalhado na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="7d67e-339">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="7d67e-340">Para criar a rota de "Redmond 1", digite:</span><span class="sxs-lookup"><span data-stu-id="7d67e-340">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="7d67e-341">Qual retorna:</span><span class="sxs-lookup"><span data-stu-id="7d67e-341">Which returns:</span></span>
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
<span data-ttu-id="7d67e-342">Para criar a rota de Redmond 2, digite:</span><span class="sxs-lookup"><span data-stu-id="7d67e-342">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="7d67e-343">Para criar a rota de + 1, digite:</span><span class="sxs-lookup"><span data-stu-id="7d67e-343">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="7d67e-344">Certifique-se de que sua expressão regular no atributo NumberPattern é uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="7d67e-344">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="7d67e-345">Você pode testá-lo usando este site:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="7d67e-345">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="7d67e-346">Em alguns casos, há uma necessidade para rotear todas as chamadas para o mesmo SBC; use - NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="7d67e-346">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="7d67e-347">Rotear todas as chamadas para o mesmo SBC</span><span class="sxs-lookup"><span data-stu-id="7d67e-347">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="7d67e-348">Validar se você configurou corretamente o roteiro executando o `Get-CSOnlineVoiceRoute` comando do PowerShell usando opções, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="7d67e-348">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="7d67e-349">Qual deve retornar:</span><span class="sxs-lookup"><span data-stu-id="7d67e-349">Which should return:</span></span>
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

<span data-ttu-id="7d67e-350">No exemplo, a rota "Outros + 1" foi atribuído automaticamente a prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="7d67e-350">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="7d67e-351">**Etapa 3:** Criar uma política de roteamento de voz "Somente nos EUA" e adicionar à política, o uso da PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="7d67e-351">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="7d67e-352">Em uma sessão do PowerShell no Skype para Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="7d67e-352">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="7d67e-353">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d67e-353">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="7d67e-354">**Etapa 4:** Conceda ao usuário Spencer Low uma política de roteamento de voz usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d67e-354">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="7d67e-355">Em uma sessão do PowerShell no Skype para Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="7d67e-355">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="7d67e-356">Valide a atribuição de política digitando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d67e-356">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="7d67e-357">Qual retorna:</span><span class="sxs-lookup"><span data-stu-id="7d67e-357">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="7d67e-358">Criando uma política de roteamento de voz com vários usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="7d67e-358">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="7d67e-359">A política de roteamento de voz criado anteriormente só permite chamadas para números de telefone nos Estados Unidos e no Canadá –, a menos que a licença chamar plano Microsoft também é atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7d67e-359">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="7d67e-360">No exemplo a seguir, é possível criar a política de roteamento de voz "Sem restrições."</span><span class="sxs-lookup"><span data-stu-id="7d67e-360">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="7d67e-361">A política reutiliza o uso da PSTN "EUA e Canadá" criado no exemplo anterior, bem como o uso da PSTN novo "Internacional".</span><span class="sxs-lookup"><span data-stu-id="7d67e-361">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="7d67e-362">Isso encaminha todos os outras chamadas para o sbc2.contoso.biz SBCs e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-362">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="7d67e-363">Os exemplos mostrados atribuem conosco apenas uma política para o usuário "Low Silva" e sem restrições ao usuário "John Woods".</span><span class="sxs-lookup"><span data-stu-id="7d67e-363">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="7d67e-364">Baixa Silva – chamadas permitidas somente aos números nos EUA e Canadá.</span><span class="sxs-lookup"><span data-stu-id="7d67e-364">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="7d67e-365">Durante a chamada para o intervalo de números de Redmond, o conjunto específico de SBC deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="7d67e-365">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="7d67e-366">Números de fora dos EUA não serão roteados, a menos que a licença chamar planejar é atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7d67e-366">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="7d67e-367">Carlos Lacerda – chamadas permitidas para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="7d67e-367">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="7d67e-368">Durante a chamada para o intervalo de números de Redmond, o conjunto específico de SBC deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="7d67e-368">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="7d67e-369">Fora dos EUA números serão roteados via sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-369">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="7d67e-371">Para todas as chamadas, se ambas as licenças (sistema de telefone da Microsoft e chamar plano Microsoft), o usuário tem automático rota será usada.</span><span class="sxs-lookup"><span data-stu-id="7d67e-371">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="7d67e-372">Se nada corresponder os padrões de número em que as rotas de voz online criados pelo administrador, rotear via Microsoft chamar planejar.</span><span class="sxs-lookup"><span data-stu-id="7d67e-372">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="7d67e-373">Se o usuário tiver apenas o Microsoft Phone System, a chamada será interrompida, pois não há regras de correspondência estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7d67e-373">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="7d67e-375">A tabela a seguir resume o roteamento designações de uso de "Sem restrições" diretiva e rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="7d67e-375">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="7d67e-376">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="7d67e-376">**PSTN usage**</span></span>|<span data-ttu-id="7d67e-377">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="7d67e-377">**Voice route**</span></span>|<span data-ttu-id="7d67e-378">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="7d67e-378">**Number pattern**</span></span>|<span data-ttu-id="7d67e-379">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="7d67e-379">**Priority**</span></span>|<span data-ttu-id="7d67e-380">**SBC**</span><span class="sxs-lookup"><span data-stu-id="7d67e-380">**SBC**</span></span>|<span data-ttu-id="7d67e-381">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7d67e-381">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d67e-382">Somente nos EUA</span><span class="sxs-lookup"><span data-stu-id="7d67e-382">US Only</span></span>|<span data-ttu-id="7d67e-383">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="7d67e-383">"Redmond 1"</span></span>|<span data-ttu-id="7d67e-384">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="7d67e-384">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7d67e-385">1</span><span class="sxs-lookup"><span data-stu-id="7d67e-385">1</span></span>|<span data-ttu-id="7d67e-386">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-386">sbc1.contoso.biz</span></span><br/><span data-ttu-id="7d67e-387">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-387">sbc2.contoso.biz</span></span>|<span data-ttu-id="7d67e-388">Rota ativa para o receptor números +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7d67e-388">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7d67e-389">Somente nos EUA</span><span class="sxs-lookup"><span data-stu-id="7d67e-389">US Only</span></span>|<span data-ttu-id="7d67e-390">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="7d67e-390">"Redmond 2"</span></span>|<span data-ttu-id="7d67e-391">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="7d67e-391">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="7d67e-392">2</span><span class="sxs-lookup"><span data-stu-id="7d67e-392">2</span></span>|<span data-ttu-id="7d67e-393">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-393">sbc3.contoso.biz</span></span><br/><span data-ttu-id="7d67e-394">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-394">sbc4.contoso.biz</span></span>|<span data-ttu-id="7d67e-395">Rota de backup para números de receptor +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="7d67e-395">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="7d67e-396">Somente nos EUA</span><span class="sxs-lookup"><span data-stu-id="7d67e-396">US Only</span></span>|<span data-ttu-id="7d67e-397">"Outros + 1"</span><span class="sxs-lookup"><span data-stu-id="7d67e-397">"Other +1"</span></span>|<span data-ttu-id="7d67e-398">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="7d67e-398">^\\+1(\d{10})$</span></span>|<span data-ttu-id="7d67e-399">3</span><span class="sxs-lookup"><span data-stu-id="7d67e-399">3</span></span>|<span data-ttu-id="7d67e-400">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-400">sbc5.contoso.biz</span></span><br/><span data-ttu-id="7d67e-401">sbc6>.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-401">sbc6>.contoso.biz</span></span>|<span data-ttu-id="7d67e-402">Números de rota para o receptor + 1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="7d67e-402">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="7d67e-403">International</span><span class="sxs-lookup"><span data-stu-id="7d67e-403">International</span></span>|<span data-ttu-id="7d67e-404">International</span><span class="sxs-lookup"><span data-stu-id="7d67e-404">International</span></span>|<span data-ttu-id="7d67e-405">\ d \d+</span><span class="sxs-lookup"><span data-stu-id="7d67e-405">\d+</span></span>|<span data-ttu-id="7d67e-406">4</span><span class="sxs-lookup"><span data-stu-id="7d67e-406">4</span></span>|<span data-ttu-id="7d67e-407">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-407">sbc2.contoso.biz</span></span><br/><span data-ttu-id="7d67e-408">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="7d67e-408">sbc5.contoso.biz</span></span>|<span data-ttu-id="7d67e-409">Rota para qualquer número padrão</span><span class="sxs-lookup"><span data-stu-id="7d67e-409">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="7d67e-410">A ordem de usos da PSTN em políticas de roteamento de voz é crítica.</span><span class="sxs-lookup"><span data-stu-id="7d67e-410">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="7d67e-411">Os usos são aplicados na ordem, e se uma correspondência for encontrada no uso do primeiro, em seguida, outros usos são nunca avaliados.</span><span class="sxs-lookup"><span data-stu-id="7d67e-411">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="7d67e-412">O uso da PSTN "Internacional" deve ser colocado após o uso da PSTN "Somente nos EUA."</span><span class="sxs-lookup"><span data-stu-id="7d67e-412">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="7d67e-413">Para alterar a ordem dos usos da PSTN, execute o `Set-CSOnlineRouteRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="7d67e-413">To change the order of the PSTN Usages, run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="7d67e-414">Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "Internacional" segundo a ordem inversa execute:</span><span class="sxs-lookup"><span data-stu-id="7d67e-414">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="7d67e-415">A prioridade para "Outros + 1" e "Internacional" Voice routes recebem automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7d67e-415">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="7d67e-416">Eles não importam, desde que eles têm prioridades mais baixas que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="7d67e-416">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="7d67e-417">Exemplo da política de roteamento de voz para o usuário John Woods</span><span class="sxs-lookup"><span data-stu-id="7d67e-417">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="7d67e-418">As etapas para criar o uso da PSTN "Internacional", "Internacional", da rota de voz "Sem restrições," política de roteamento de voz e, em seguida, atribuí-la ao usuário "Carlos Lacerda" são os seguintes.</span><span class="sxs-lookup"><span data-stu-id="7d67e-418">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="7d67e-419">Primeiro, crie o uso da PSTN "Internacional".</span><span class="sxs-lookup"><span data-stu-id="7d67e-419">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="7d67e-420">Em uma sessão PowerShell remota no Skype para Business Online, insira:</span><span class="sxs-lookup"><span data-stu-id="7d67e-420">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="7d67e-421">Em seguida, criar a nova rota de voz "Internacional".</span><span class="sxs-lookup"><span data-stu-id="7d67e-421">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="7d67e-422">Qual retorna:</span><span class="sxs-lookup"><span data-stu-id="7d67e-422">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="7d67e-423">Em seguida, crie uma política de roteamento de voz "Sem restrições".</span><span class="sxs-lookup"><span data-stu-id="7d67e-423">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="7d67e-424">O uso de PSTN "Redmond 1" e "Redmond" são reutilizadas nesta política de roteamento de voz para preservar a ação especial para chamadas de número "+1 425 XXX XX XX" e "+1 206 XXX XX XX" como local ou no local.</span><span class="sxs-lookup"><span data-stu-id="7d67e-424">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="7d67e-425">Qual retorna</span><span class="sxs-lookup"><span data-stu-id="7d67e-425">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="7d67e-426">Atribua a política de roteamento de voz ao usuário "John Woods" usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="7d67e-426">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="7d67e-427">Verifique se a atribuição usando o comando:</span><span class="sxs-lookup"><span data-stu-id="7d67e-427">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="7d67e-428">Qual retorna:</span><span class="sxs-lookup"><span data-stu-id="7d67e-428">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="7d67e-429">O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponíveis para as chamadas dos Estados Unidos, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="7d67e-429">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="7d67e-430">Configurar o Microsoft Teams como o cliente de chamada preferencial para usuários</span><span class="sxs-lookup"><span data-stu-id="7d67e-430">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="7d67e-431">Roteamento direto somente roteia as chamadas de e para os usuários se eles usarem o cliente de equipes.</span><span class="sxs-lookup"><span data-stu-id="7d67e-431">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="7d67e-432">Se sua organização usa somente equipes, definindo "Equipes apenas" na política de atualização é recomendado.</span><span class="sxs-lookup"><span data-stu-id="7d67e-432">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="7d67e-433">Se sua organização usa Skype para Business Server ou Skype para Business Online, consulte o seguinte artigo para obter mais informações e selecione a opção apropriada: [entender a coexistência e atualizar jornada para Skype para equipes e de negócios](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="7d67e-433">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="7d67e-434">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7d67e-434">See also</span></span>

[<span data-ttu-id="7d67e-435">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="7d67e-435">Plan Direct Routing</span></span>](direct-routing-plan.md)
