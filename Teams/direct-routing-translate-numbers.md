---
title: Traduzir números de telefone para Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o Telefone Microsoft Roteamento Direto do Sistema.
ms.openlocfilehash: 2e94da39c23c10a912f4b3f0433467439b5ecf77
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766364"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traduzir números de telefone para um formato alternativo

Este artigo descreve como traduzir números para chamadas de saída e de entrada para um formato alternativo.  Esta é a etapa 4 das seguintes etapas para configurar o Roteamento Direto:

- Etapa 1. [Conexão SBC com Telefone Microsoft System e validar a conexão](direct-routing-connect-the-sbc.md) 
- Etapa 2. [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)   
- Etapa 3. [Configurar roteamento de voz](direct-routing-voice-routing.md)
- **Etapa 4. Converter números em um formato alternativo**   (Este artigo)

Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).

Às vezes, os administradores de locatários podem querer alterar o número de chamadas de saída e/ou de entrada com base nos padrões criados para garantir a interoperabilidade com controladores de borda de sessão (SBCs). Este artigo descreve como você pode especificar uma política regras de conversão de números para traduzir números para um formato alternativo. 

Você pode usar a política Regras de Conversão de Números para traduzir números para o seguinte:

- Chamadas de entrada: Chamadas de um ponto de extremidade PSTN (chamador) para um cliente Teams (chamador)
- Chamadas de saída: chamadas de um cliente Teams (chamador) para um ponto de extremidade PSTN (chamador)

A política é aplicada no nível SBC. Você pode atribuir várias regras de conversão a um SBC, que são aplicadas na ordem em que elas aparecem quando você as lista no PowerShell. Você também pode alterar a ordem das regras na política.

Para criar, modificar, exibir e excluir regras de manipulação de números, use os cmdlets [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Para atribuir, configurar e listar regras de manipulação de números em SBCs, use os cmdlets [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) e [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) juntamente com os cmdlets InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules e OutboundPSTNNumberTranslationRules.

> [!NOTE]
> O número total máximo de regras de conversão é 400, o comprimento máximo do nome do parâmetro de conversão é 100 símbolos, o comprimento máximo do padrão do parâmetro de conversão é 1024 símbolos e o comprimento máximo da conversão do parâmetro de conversão é de 256 símbolos.


## <a name="example-sbc-configuration"></a>Exemplo de configuração SBC

Para esse cenário, o ```New-CsOnlinePSTNGateway``` cmdlet é executado para criar a seguinte configuração SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

As regras de conversão atribuídas ao SBC são resumidas na tabela a seguir:

|Nome  |Padrão |Conversão  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

Nos exemplos a seguir, há dois usuários, Alice e Bob. Alice é uma Teams cujo número é +1 206 555 0100. Bob é um usuário PSTN cujo número é +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemplo 1: chamada de entrada para um número de dez dígitos

Bob chama Alice usando um número de dez dígitos que não seja E.164. Bob disca 2065550100 para chegar a Alice.
SBC usa 2065550100 nos headers RequestURI e To e 4255550100 no header From.


|Header  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:2065550100@sbc.contoso.com|CONVIDAR sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|PARA    |PARA: \<sip:2065550100@sbc.contoso.com>|PARA: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemplo 2: chamada de entrada para um número de quatro dígitos

Bob chama Alice usando um número de quatro dígitos. Bob disca 0100 para chegar a Alice.
SBC usa 0100 nos headers RequestURI e To e 4255550100 no header From.


|Header  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:0100@sbc.contoso.com          |CONVIDAR sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|PARA    |PARA: \<sip:0100@sbc.contoso.com>|PARA: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemplo 3: Chamada de saída usando um número não E.164 de dez dígitos

Alice chama Bob usando um número de dez dígitos. Alice disca 425 555 0100 para alcançar Bob.
O SBC está configurado para usar números de dez dígitos que não são E.164 para usuários Teams ESTN.

Nesse cenário, um plano de discagem converte o número antes de enviá-lo para a interface de Roteamento Direto. Quando Alice inseja 425 555 0100 no cliente Teams, o número é convertido em +14255550100 pelo plano de discagem do país. Os números resultantes são uma normalização cumulativa das regras de plano de discagem e Teams de conversão. As Teams de conversão removem o "+1" adicionado pelo plano de discagem.


|Header  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:+14255550100@sbc.contoso.com          |CONVIDAR sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|PARA    |PARA: \<sip:+14255550100@sbc.contoso.com>|PARA: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemplo 4: Chamada de saída usando um número não E.164 de quatro dígitos

Alice chama Bob usando um número de quatro dígitos. Alice usa 0100 para alcançar Bob de Chamadas ou usando um contato.
O SBC está configurado para usar números de quatro dígitos que não são E.164 para usuários Teams e números de dez dígitos para usuários PSTN. O plano de discagem não é aplicado neste cenário.


|Header  |Original |Header traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:0100@sbc.contoso.com           |CONVIDAR sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|PARA    |PARA: \<sip:0100@sbc.contoso.com>|PARA: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
