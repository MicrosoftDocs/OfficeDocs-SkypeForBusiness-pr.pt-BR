---
title: Roteamento Direto - Conectando dispositivos analógicos
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leia este artigo para saber como usar dispositivos analógicos com o Roteamento Direto do Sistema de Telefonia microsoft.
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841482"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="e88d9-103">Como usar dispositivos analógicos com Roteamento Direto do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="e88d9-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="e88d9-104">Este artigo descreve como usar dispositivos analógicos com Roteamento Direto do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="e88d9-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="e88d9-105">Para conectar dispositivos analógicos ao Roteamento Direto, você deve usar um Adaptador de Telefonia Analógico (ATA) e esse adaptador deve ter suporte do fornecedor certificado do Controlador de Borda de Sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="e88d9-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="e88d9-106">Quando um usuário faz uma chamada de um dispositivo analógico, a sinalização e a mídia fluem pelo Adaptador de Telefonia Analógico (ATA) para o SBC.</span><span class="sxs-lookup"><span data-stu-id="e88d9-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="e88d9-107">O SBC envia a chamada para um ponto de extremidade do Microsoft Teams ou para a PSTN (Rede Telefônica Pública Comucionada) com base na tabela de roteamento interno.</span><span class="sxs-lookup"><span data-stu-id="e88d9-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="e88d9-108">Quando um dispositivo faz uma chamada, a rota que ele faz depende das políticas de roteamento criadas para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e88d9-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="e88d9-109">No diagrama a seguir, o Roteamento Direto é configurado para que qualquer chamada do Teams de e para os números entre +1425 4XX XX e +1425 5XX XX XX deve tomar a rota vermelha (linha pontilhada), e qualquer chamada PSTN de e para números entre +1425 4XX XX e qualquer outro número, exceto intervalo de números +1425 5XX XX, deve levar a rota azul (linha sólida).</span><span class="sxs-lookup"><span data-stu-id="e88d9-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e88d9-110">![Diagrama mostrando a configuração de Roteamento Direto](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="e88d9-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="e88d9-111">Exemplo: como configurar o uso de dispositivos analógicos com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e88d9-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="e88d9-112">Para configurar o uso de dispositivos analógicos com o Roteamento Direto, você deve conectar o Adaptador de Telefonia Analógico ao SBC e configurar o SBC para funcionar com o Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="e88d9-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="e88d9-113">Este exemplo orienta você pelas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e88d9-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="e88d9-114">Conecte o SBC ao Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="e88d9-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="e88d9-115">Crie o uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="e88d9-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="e88d9-116">Crie uma rota de voz e associá-la ao Uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="e88d9-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="e88d9-117">Atribua a rota de voz ao Uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="e88d9-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="e88d9-118">Habilita o usuário online.</span><span class="sxs-lookup"><span data-stu-id="e88d9-118">Enable the online user.</span></span>
6. <span data-ttu-id="e88d9-119">Atribua a política de rota de voz ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e88d9-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="e88d9-120">Crie uma rota de voz para um dispositivo analógico.</span><span class="sxs-lookup"><span data-stu-id="e88d9-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="e88d9-121">Para obter informações sobre como conectar um ATA a um SBC e configurar o SBC, consulte o guia de configuração do fabricante do SBC:</span><span class="sxs-lookup"><span data-stu-id="e88d9-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="e88d9-122">Documentação de configuração de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e88d9-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="e88d9-123">Documentação de configuração da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="e88d9-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="e88d9-124">Documentação de configuração oracle</span><span class="sxs-lookup"><span data-stu-id="e88d9-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="e88d9-125">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="e88d9-125">Step 1.</span></span>  <span data-ttu-id="e88d9-126">Conectar o SBC ao Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e88d9-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="e88d9-127">O comando a seguir configura a conexão SBC da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e88d9-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="e88d9-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e88d9-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="e88d9-129">Porta de sinalização 5068</span><span class="sxs-lookup"><span data-stu-id="e88d9-129">Signaling port 5068</span></span>
- <span data-ttu-id="e88d9-130">Modo de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="e88d9-130">Media bypass mode</span></span>
- <span data-ttu-id="e88d9-131">Informações do histórico de chamada encaminhadas para o SBC-</span><span class="sxs-lookup"><span data-stu-id="e88d9-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="e88d9-132">Header P-Asserted-Identity (PAI) encaminhado junto com a chamada</span><span class="sxs-lookup"><span data-stu-id="e88d9-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="e88d9-133">Etapa 2: Criar o uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="e88d9-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="e88d9-134">O próximo comando cria um uso PSTN vazio.</span><span class="sxs-lookup"><span data-stu-id="e88d9-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="e88d9-135">Os usos de PSTN online são valores de cadeia de caracteres usados para autorização de chamada.</span><span class="sxs-lookup"><span data-stu-id="e88d9-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="e88d9-136">Um uso de PSTN online vincula uma política de voz online a uma rota.</span><span class="sxs-lookup"><span data-stu-id="e88d9-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="e88d9-137">Este exemplo adiciona a cadeia de caracteres "Interop" à lista atual de usos de PSTN disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e88d9-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="e88d9-138">Etapa 3: Criar uma rota de voz e associá-la ao uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="e88d9-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="e88d9-139">Este comando cria uma nova rota de voz online com a identidade "interop analógica" para o intervalo de números +1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="e88d9-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="e88d9-140">A rota de voz é aplicável a uma lista de gateways online sbc.contoso.com e associa a rota ao uso de PSTN online "Interop".</span><span class="sxs-lookup"><span data-stu-id="e88d9-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="e88d9-141">Uma rota de voz inclui uma expressão regular que identifica quais números de telefone serão roteados por uma determinada rota de voz:</span><span class="sxs-lookup"><span data-stu-id="e88d9-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="e88d9-142">Etapa 4: Atribuir a rota de voz ao uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="e88d9-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="e88d9-143">Este comando cria uma nova política de roteamento de voz online por usuário com a Identidade "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="e88d9-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="e88d9-144">Essa política é atribuída a um único uso de PSTN online: "Interop".</span><span class="sxs-lookup"><span data-stu-id="e88d9-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="e88d9-145">Etapa 5: Habilitar o usuário online</span><span class="sxs-lookup"><span data-stu-id="e88d9-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="e88d9-146">Este comando modifica a conta de usuário com a identidade exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e88d9-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="e88d9-147">Nesse caso, a conta é modificada para habilitar o Enterprise Voice, a implementação do VoIP da Microsoft, com caixa postal habilitada e atribui o número +142550000000 a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="e88d9-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="e88d9-148">Esse comando deve ser executado para cada usuário do Teams (excluindo usuários de dispositivoS ATA) no locatário da empresa.</span><span class="sxs-lookup"><span data-stu-id="e88d9-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="e88d9-149">Etapa 6: Atribuir a política de rota de voz a um usuário</span><span class="sxs-lookup"><span data-stu-id="e88d9-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="e88d9-150">Este comando atribui a política de roteamento de voz online por usuário AnalogInteropPolicy ao usuário com a identidade exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e88d9-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="e88d9-151">Esse comando deve ser executado para cada usuário do Teams (excluindo usuários de dispositivoS ATA) no locatário da empresa.</span><span class="sxs-lookup"><span data-stu-id="e88d9-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="e88d9-152">Etapa 7: Criar uma rota de voz para um dispositivo analógico</span><span class="sxs-lookup"><span data-stu-id="e88d9-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="e88d9-153">Este comando cria uma rota de voz online com a identidade "interop analógica" para o intervalo de números +1425 4XX XX XX aplicáveis a uma lista de gateways online sbc.contoso.com e a associa ao uso de PSTN online "Interop".</span><span class="sxs-lookup"><span data-stu-id="e88d9-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="e88d9-154">Esse comando deve ser executado para cada dispositivo analógico com o padrão de número de telefone apropriado.</span><span class="sxs-lookup"><span data-stu-id="e88d9-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="e88d9-155">Como alternativa, um padrão de número adequado para dispositivos analógicos pode ser usado durante a configuração da rota de voz online durante uma das etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="e88d9-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="e88d9-156">Considerações</span><span class="sxs-lookup"><span data-stu-id="e88d9-156">Considerations</span></span>

- <span data-ttu-id="e88d9-157">A menos que o contrário, um dispositivo analógico é qualquer dispositivo que pode enviar dígitos DTMF para fazer uma chamada.</span><span class="sxs-lookup"><span data-stu-id="e88d9-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="e88d9-158">Por exemplo, telefones analógicos, aparelhos de fax e pagers de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="e88d9-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="e88d9-159">Telefones analógicos conectados a um ATA não são pesquisáveis no Teams.</span><span class="sxs-lookup"><span data-stu-id="e88d9-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="e88d9-160">Os usuários do Teams devem inserir manualmente o número de telefone associado ao dispositivo para chamar esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e88d9-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="e88d9-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="e88d9-161">See also</span></span>

[<span data-ttu-id="e88d9-162">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e88d9-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="e88d9-163">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e88d9-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
