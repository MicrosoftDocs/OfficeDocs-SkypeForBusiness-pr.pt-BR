---
title: Roteamento direto – conectando dispositivos analógicos
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
description: Leia este artigo para saber como usar dispositivos analógicos com o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558511"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="f8805-103">Como usar dispositivos analógicos com o roteamento direto do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="f8805-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="f8805-104">Este artigo descreve como usar dispositivos analógicos com o roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="f8805-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="f8805-105">Para conectar dispositivos analógicos ao roteamento direto, você deve usar um adaptador de telefonia analógica (ATA) e esse adaptador deve ser compatível com o fornecedor do controlador de borda de sessão (SBC) certificado.</span><span class="sxs-lookup"><span data-stu-id="f8805-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="f8805-106">Quando um usuário faz uma chamada de um dispositivo analógico, o sinal e a mídia fluem pelo adaptador de telefonia analógica (ATA) para o SBC.</span><span class="sxs-lookup"><span data-stu-id="f8805-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="f8805-107">O SBC envia a chamada para um ponto de extremidade do Microsoft Teams ou para a rede telefônica pública comutada (PSTN) com base na tabela de roteamento interno.</span><span class="sxs-lookup"><span data-stu-id="f8805-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="f8805-108">Quando um dispositivo faz uma chamada, a rota necessária depende das políticas de roteamento criadas para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8805-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="f8805-109">No diagrama a seguir, o roteamento direto é configurado para que todas as equipes liguem para e dos números entre + 1425 4XX XX XX e + 1425 5XX XX XX devem levar a rota vermelha (linha pontilhada) e qualquer chamada PSTN para e de números entre + 1425 4XX XX XX e qualquer outro número, exceto  intervalo de números + 1425 5XX XX XX deve levar a rota azul (linha sólida).</span><span class="sxs-lookup"><span data-stu-id="f8805-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![Diagrama mostrando a configuração de roteamento direto](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="f8805-111">Exemplo: como configurar o uso de dispositivos analógicos com roteamento direto</span><span class="sxs-lookup"><span data-stu-id="f8805-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="f8805-112">Para configurar o uso de dispositivos analógicos com roteamento direto, você deve conectar o adaptador de telefonia analógica ao SBC e configurar o SBC para funcionar com o roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="f8805-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="f8805-113">Este exemplo percorre as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f8805-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="f8805-114">Conecte o SBC ao roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="f8805-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="f8805-115">Criar o uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8805-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="f8805-116">Crie uma rota de voz e associe-a ao uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8805-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="f8805-117">Atribua a rota de voz ao uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8805-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="f8805-118">Habilite o usuário online.</span><span class="sxs-lookup"><span data-stu-id="f8805-118">Enable the online user.</span></span>
6. <span data-ttu-id="f8805-119">Atribua a política de rota de voz ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f8805-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="f8805-120">Crie uma rota de voz para um dispositivo analógico.</span><span class="sxs-lookup"><span data-stu-id="f8805-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="f8805-121">Para obter informações sobre como conectar um ATA a um SBC e configurar o SBC, consulte o guia de configuração do fabricante do SBC:</span><span class="sxs-lookup"><span data-stu-id="f8805-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="f8805-122">Documentação de configuração do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f8805-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [<span data-ttu-id="f8805-123">Documentação de configuração da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="f8805-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="f8805-124">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f8805-124">Step 1.</span></span>  <span data-ttu-id="f8805-125">Conectar o SBC ao roteamento direto</span><span class="sxs-lookup"><span data-stu-id="f8805-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="f8805-126">O comando a seguir configura a conexão SBC da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f8805-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="f8805-127">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8805-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="f8805-128">Porta de sinalização 5068</span><span class="sxs-lookup"><span data-stu-id="f8805-128">Signaling port 5068</span></span>
- <span data-ttu-id="f8805-129">Modo de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="f8805-129">Media bypass mode</span></span>
- <span data-ttu-id="f8805-130">Informações do histórico de chamadas encaminhadas ao SBC-</span><span class="sxs-lookup"><span data-stu-id="f8805-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="f8805-131">Cabeçalho P-declarado-identidade (PAI) encaminhado junto com a chamada</span><span class="sxs-lookup"><span data-stu-id="f8805-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="f8805-132">Etapa 2: criar o uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="f8805-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="f8805-133">O próximo comando cria um uso de PSTN vazio.</span><span class="sxs-lookup"><span data-stu-id="f8805-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="f8805-134">Os usos de PSTN online são valores de cadeia de caracteres que são usados para autorização de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f8805-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="f8805-135">Um uso de PSTN online vincula uma política de voz online a uma rota.</span><span class="sxs-lookup"><span data-stu-id="f8805-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="f8805-136">Este exemplo adiciona a cadeia de caracteres "Interop" à lista atual de usos de PSTN disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f8805-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="f8805-137">Etapa 3: criar uma rota de voz e associá-la ao uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="f8805-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="f8805-138">Esse comando cria uma nova rota de voz online com a identidade "analógica-Interop" para o intervalo de números + 1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="f8805-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="f8805-139">A rota de voz se aplica a uma lista de gateways online sbc.contoso.com e associa a rota com o uso de "interoperabilidade" de PSTN online.</span><span class="sxs-lookup"><span data-stu-id="f8805-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="f8805-140">Uma rota de voz inclui uma expressão regular que identifica os números de telefone que serão roteados por meio de uma determinada rota de voz:</span><span class="sxs-lookup"><span data-stu-id="f8805-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="f8805-141">Etapa 4: atribuir a rota de voz ao uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="f8805-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="f8805-142">Esse comando cria uma nova política de roteamento de voz por usuário online com a identidade "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="f8805-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="f8805-143">Essa política é atribuída a um único uso PSTN online: "Interop".</span><span class="sxs-lookup"><span data-stu-id="f8805-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="f8805-144">Etapa 5: habilitar o usuário online</span><span class="sxs-lookup"><span data-stu-id="f8805-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="f8805-145">Esse comando modifica a conta de usuário com o Identity exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f8805-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="f8805-146">Nesse caso, a conta é modificada para habilitar o Enterprise Voice, a implementação de VoIP da Microsoft, com a caixa postal habilitada e atribui o número + 14255000000 a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="f8805-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="f8805-147">Esse comando deve ser executado para cada usuário do Teams (excluindo usuários de dispositivos ATA) no locatário da empresa.</span><span class="sxs-lookup"><span data-stu-id="f8805-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="f8805-148">Etapa 6: atribuir a política de rota de voz a um usuário</span><span class="sxs-lookup"><span data-stu-id="f8805-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="f8805-149">Esse comando atribui a política de roteamento de voz online por usuário AnalogInteropPolicy ao usuário com a identidade exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f8805-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="f8805-150">Esse comando deve ser executado para cada usuário do Teams (excluindo usuários de dispositivos ATA) no locatário da empresa.</span><span class="sxs-lookup"><span data-stu-id="f8805-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="f8805-151">Etapa 7: criar uma rota de voz para um dispositivo analógico</span><span class="sxs-lookup"><span data-stu-id="f8805-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="f8805-152">Esse comando cria uma rota de voz online com identidade "analógica-Interop" para o intervalo de números + 1425 4XX XX XX aplicáveis a uma lista de gateways online sbc.contoso.com e o associa ao uso de "interoperabilidade online de uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8805-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="f8805-153">Esse comando deve ser executado para cada dispositivo analógico com o padrão de número de telefone apropriado.</span><span class="sxs-lookup"><span data-stu-id="f8805-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="f8805-154">Como alternativa, um padrão de número adequado para dispositivos analógicos pode ser usado ao configurar a rota de voz online durante uma das etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="f8805-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="f8805-155">Considerações</span><span class="sxs-lookup"><span data-stu-id="f8805-155">Considerations</span></span>

- <span data-ttu-id="f8805-156">A menos que observe de outra forma, um dispositivo analógico é qualquer dispositivo que possa enviar dígitos DTMF para fazer uma chamada.</span><span class="sxs-lookup"><span data-stu-id="f8805-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="f8805-157">Por exemplo, telefones analógicos, aparelhos de fax e pagers de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="f8805-157">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="f8805-158">Os telefones analógicos conectados a um ATA não podem ser pesquisados pelo Teams.</span><span class="sxs-lookup"><span data-stu-id="f8805-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="f8805-159">Usuários do teams devem digitar manualmente o número de telefone associado ao dispositivo para chamar esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8805-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="f8805-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="f8805-160">See also</span></span>

[<span data-ttu-id="f8805-161">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f8805-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="f8805-162">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f8805-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
