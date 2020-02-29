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
ms.openlocfilehash: 525e898bd0eafe88d6893249465734d7c33a10b2
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341797"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Como usar dispositivos analógicos com o roteamento direto do sistema telefônico

Este artigo descreve como usar dispositivos analógicos com o roteamento direto do sistema telefônico. Para conectar dispositivos analógicos ao roteamento direto, você deve usar um adaptador de telefonia analógica (ATA) e esse adaptador deve ser compatível com o fornecedor do controlador de borda de sessão (SBC) certificado. 

Quando um usuário faz uma chamada de um dispositivo analógico, o sinal e a mídia fluem pelo adaptador de telefonia analógica (ATA) para o SBC.  O SBC envia a chamada para um ponto de extremidade do Microsoft Teams ou para a rede telefônica pública comutada (PSTN) com base na tabela de roteamento interno.  Quando um dispositivo faz uma chamada, a rota necessária depende das políticas de roteamento criadas para o dispositivo.

No diagrama a seguir, o roteamento direto é configurado para que todas as equipes liguem para e dos números entre + 1425 4XX XX XX e + 1425 5XX XX XX devem levar a rota vermelha (linha pontilhada) e qualquer chamada PSTN para e de números entre + 1425 4XX XX XX e qualquer outro número, exceto  intervalo de números + 1425 5XX XX XX deve levar a rota azul (linha sólida). 

![Diagrama mostrando a configuração de roteamento direto](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Exemplo: como configurar o uso de dispositivos analógicos com roteamento direto

Para configurar o uso de dispositivos analógicos com roteamento direto, você deve conectar o adaptador de telefonia analógica ao SBC e configurar o SBC para funcionar com o roteamento direto. 

Este exemplo percorre as seguintes etapas:

1. Conectar o SBC ao roteamento direto
2. Criar o uso de PSTN
3. Criar uma rota de voz e associá-la ao uso de PSTN
4. Atribuir a rota de voz ao uso de PSTN
5. Habilitar o usuário online
6. Atribuir a política de rota de voz ao usuário
7. Criar uma rota de voz para um dispositivo analógico

Para obter informações sobre como conectar um ATA a um SBC e configurar o SBC, consulte o guia de configuração do fabricante do SBC:
- [Documentação de configuração do AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Etapa 1.  Conectar o SBC ao roteamento direto

O comando a seguir configura a conexão SBC da seguinte forma:

- FQDN sbc.contoso.com
- Porta de sinalização 5068
- Modo de bypass de mídia
- Informações do histórico de chamadas encaminhadas ao SBC-
- Cabeçalho P-declarado-identidade (PAI) encaminhado junto com a chamada 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Etapa 2: criar o uso de PSTN 

O próximo comando cria um uso de PSTN vazio. Os usos de PSTN online são valores de cadeia de caracteres que são usados para autorização de chamadas. Um uso de PSTN online vincula uma política de voz online a uma rota. Este exemplo adiciona a cadeia de caracteres "Interop" à lista atual de usos de PSTN disponíveis. 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Etapa 3: criar uma rota de voz e associá-la ao uso de PSTN:

Esse comando cria uma nova rota de voz online com a identidade "analógica-Interop" para o intervalo de números + 1425 XXX XX XX.  A rota de voz se aplica a uma lista de gateways online sbc.contoso.com e associa a rota com o uso de "interoperabilidade" de PSTN online. Uma rota de voz inclui uma expressão regular que identifica os números de telefone que serão roteados por meio de uma determinada rota de voz:

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Etapa 4: atribuir a rota de voz ao uso de PSTN:

Esse comando cria uma nova política de roteamento de voz por usuário online com a identidade "AnalogInteropPolicy". Essa política é atribuída a um único uso PSTN online: "Interop".

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Etapa 5: habilitar o usuário online

Esse comando modifica a conta de usuário com o Identity exampleuser@contoso.com. Nesse caso, a conta é modificada para habilitar o Enterprise Voice, a implementação de VoIP da Microsoft, com a caixa postal habilitada e atribui o número + 14255000000 a esse usuário.  Esse comando deve ser executado para cada usuário do Teams (excluindo usuários de dispositivos ATA) no locatário da empresa.

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Etapa 6: atribuir a política de rota de voz a um usuário

Esse comando atribui a política de roteamento de voz online por usuário AnalogInteropPolicy ao usuário com a identidade exampleuser@contoso.com.  Esse comando deve ser executado para cada usuário do Teams (excluindo usuários de dispositivos ATA) no locatário da empresa.

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Etapa 7: criar uma rota de voz para um dispositivo analógico

Esse comando cria uma rota de voz online com identidade "analógica-Interop" para o intervalo de números + 1425 4XX XX XX aplicáveis a uma lista de gateways online sbc.contoso.com e o associa ao uso de "interoperabilidade online de uso PSTN.  Esse comando deve ser executado para cada dispositivo analógico com o padrão de número de telefone apropriado. Como alternativa, um padrão de número adequado para dispositivos analógicos pode ser usado ao configurar a rota de voz online durante uma das etapas anteriores.

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Considerações

- A menos que observe de outra forma, um dispositivo analógico é qualquer dispositivo que possa enviar dígitos DTMF para fazer uma chamada. Por exemplo, telefones analógicos, aparelhos de fax e pagers de sobrecarga.
- Os telefones analógicos conectados a um ATA não podem ser pesquisados pelo Teams. Usuários do teams devem digitar manualmente o número de telefone associado ao dispositivo para chamar esse dispositivo.  
 

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
