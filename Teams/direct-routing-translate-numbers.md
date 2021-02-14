---
title: Traduzir números de telefone para Roteamento Direto
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
f1.keywords:
- NOCSH
description: Saiba como configurar o Roteamento Direto do Sistema do Microsoft Phone.
ms.openlocfilehash: 7d48e9163dd5927cbeddf4a4104d2382e69e7e2b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369156"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traduzir números de telefone para um formato alternativo

Este artigo descreve como traduzir números de chamadas de entrada e saída para um formato alternativo.  Esta é a etapa 4 das seguintes etapas para configurar o Roteamento Direto:

- Etapa 1. [Conectar o SBC ao Microsoft Phone System e validar a conexão](direct-routing-connect-the-sbc.md) 
- Etapa 2. [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)   
- Etapa 3. [Configurar roteamento de voz](direct-routing-voice-routing.md)
- **Etapa 4. Traduzir números para um formato alternativo**   (este artigo)

Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configurar Roteamento Direto.](direct-routing-configure.md)

Às vezes, os administradores de locatários podem querer alterar o número de chamadas de saída e/ou de entrada com base nos padrões criados para garantir a interoperabilidade com SBCs (Controladores de Borda de Sessão). Este artigo descreve como você pode especificar uma política de Regras de Tradução de Números para traduzir números para um formato alternativo. 

Você pode usar a política regras de tradução de números para traduzir números para o seguinte:

- Chamadas de entrada: Chamadas de um ponto de extremidade PSTN (chamador) para um cliente do Teams (chamador)
- Chamadas de saída: Chamadas de um cliente do Teams (chamador) para um ponto de extremidade PSTN (destinatário da chamada)

A política é aplicada no nível SBC. Você pode atribuir várias regras de tradução a um SBC, que são aplicadas na ordem em que aparecem quando você as lista no PowerShell. Você também pode alterar a ordem das regras na política.

Para criar, modificar, exibir e excluir regras de manipulação de número, use os cmdlets [New-CsTeamsTranslationRule,](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule.](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule)

Para atribuir, configurar e listar regras de manipulação de números em SBCs, use os cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) juntamente com os cmdlets InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules e OutboundPSTNNumberTranslationRules.

> [!NOTE]
> O número total máximo de regras de tradução é 400, o comprimento máximo do nome do parâmetro de tradução é de 100 símbolos, o comprimento máximo do padrão de parâmetro de tradução é de 1024 símbolos e o comprimento máximo do parâmetro de tradução é de 256 símbolos.


## <a name="example-sbc-configuration"></a>Exemplo de configuração SBC

Para esse cenário, o ```New-CsOnlinePSTNGateway``` cmdlet é executado para criar a seguinte configuração SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

As regras de tradução atribuídas ao SBC são resumidas na tabela a seguir:

|Nome  |Padrão |Conversão  |
|---------|---------|---------|
|AdicionarPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

Nos exemplos a seguir, há dois usuários, Alice e Bob. Alice é um usuário do Teams cujo número é +1 206 555 0100. Bob é um usuário PSTN cujo número é +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemplo 1: Chamada de entrada para um número de dez dígitos

Bob liga para Alice usando um número de dez dígitos que não seja E.164. Bob disca 2065550100 para chegar a Alice.
O SBC usa 206550100 nos headers RequestURI e Para e 4255550100 no header From.


|Cabeçalho  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVIDAR sip:2065550100@sbc.contoso.com|CONVIDAR sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|Para    |Para: \<sip:2065550100@sbc.contoso.com>|Para: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberLhelationRules 'AddPlus1'|
|De   |De: \<sip:4255550100@sbc.contoso.com>|De: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemplo 2: Chamada de entrada para um número de quatro dígitos

Bob liga para Alice usando um número de quatro dígitos. Bob disca 0100 para chegar a Alice.
O SBC usa 0100 nos headers RequestURI e To e 4255550100 no header From.


|Cabeçalho  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVIDAR sip:0100@sbc.contoso.com          |CONVIDAR sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberLhelationRules 'AddE164SeattleAreaCode'        |
|Para    |Para: \<sip:0100@sbc.contoso.com>|Para: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberLhelationRules 'AddE164SeattleAreaCode'         |
|De   |De: \<sip:4255550100@sbc.contoso.com>|De: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberEjalationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemplo 3: Chamada de saída usando um número de dez dígitos que não seja E.164

Alice liga para Bob usando um número de dez dígitos. Alice disca 425 555 0100 para chegar a Bob.
O SBC está configurado para usar números de dez dígitos que não são E.164 para usuários do Teams e PSTN.

Nesse cenário, um plano de discagem traduz o número antes de enviá-lo para a interface de Roteamento Direto. Quando Alice inserir 425 555 0100 no cliente do Teams, o número será convertido em +14255550100 pelo plano de discagem do país. Os números resultantes são uma normalização cumulativa das regras de plano de discagem e regras de tradução do Teams. As regras de tradução do Teams removem o "+1" que foi adicionado pelo plano de discagem.


|Cabeçalho  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVIDAR sip:+14255550100@sbc.contoso.com          |CONVIDAR sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberEjalationRules 'StripPlus1'         |
|Para    |Para: \<sip:+14255550100@sbc.contoso.com>|Para: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberEjalationRules 'StripPlus1'       |
|De   |De: \<sip:+12065550100@sbc.contoso.com>|De: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberLhelationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemplo 4: Chamada de saída usando um número de quatro dígitos que não seja E.164

Alice liga para Bob usando um número de quatro dígitos. Alice usa o 0100 para contatar Bob de Chamadas ou usando um contato.
O SBC está configurado para usar números de quatro dígitos que não são E.164 para usuários do Teams e números de dez dígitos para usuários PSTN. O plano de discagem não é aplicado neste cenário.


|Cabeçalho  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVIDAR sip:0100@sbc.contoso.com           |CONVIDAR sip:4255550100@sbc.contoso.com       |InboundTeamsNumber BluetoothlationRules 'AddSeattleAreaCode'         |
|Para    |Para: \<sip:0100@sbc.contoso.com>|Para: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumber BluetoothlationRulesList 'AddSeattleAreaCode'       |
|De   |De: \<sip:+12065550100@sbc.contoso.com>|De: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberNumlationRules 'StripPlus1' |

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
