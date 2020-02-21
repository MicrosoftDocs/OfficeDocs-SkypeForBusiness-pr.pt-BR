---
title: Converter números de telefone para roteamento direto
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
description: Saiba como configurar o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 2b675948153589c73fa545a95ac785b716b55265
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157928"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Converter números de telefone em um formato alternativo

Este artigo descreve como converter números de chamadas de entrada e saída em um formato alternativo.  Esta é a etapa 4 das etapas a seguir para configurar o roteamento direto:

- Etapa 1. [Conectar o SBC com o sistema Microsoft Phone e validar a conexão](direct-routing-connect-the-sbc.md) 
- Etapa 2. [Habilite os usuários para roteamento direto, voz e correio de voz](direct-routing-enable-users.md)   
- Etapa 3. [Configurar roteamento de voz](direct-routing-voice-routing.md)
- **Etapa 4. Converter números em um formato alternativo** (este artigo)

Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).

Às vezes, os administradores de locatários podem querer alterar o número de chamadas de entrada e saída com base nos padrões que criaram para garantir a interoperabilidade com controladores de borda de sessão (SBCs). Este artigo descreve como você pode especificar uma política de regras de tradução de números para traduzir números para um formato alternativo. 

Você pode usar a política de regras de tradução de números para traduzir números para o seguinte:

- Chamadas recebidas: chamadas de um ponto de extremidade PSTN (chamador) para um cliente do Teams (chamado)
- Chamadas de saída: chamadas de um cliente do Teams (chamador) para um ponto de extremidade PSTN (chamado)

A política é aplicada no nível de SBC. Você pode atribuir várias regras de tradução a um SBC, que são aplicadas na ordem em que aparecem quando você as lista no PowerShell. Você também pode alterar a ordem das regras na política.

Para criar, modificar, exibir e excluir regras de manipulação de números, use os cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Para atribuir, configurar e listar as regras de manipulação de números no SBCs, use os cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) juntos com InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRulesList, InboundPSTNNumberTranslationRulesList, OutboundTeamsNumberTranslationRulesList e OutboundPSTNNumberTranslationRulesList os.


## <a name="example-sbc-configuration"></a>Exemplo de configuração do SBC

Para esse cenário, o ```New-CsOnlinePSTNGateway``` cmdlet é executado para criar a seguinte configuração de SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

As regras de tradução atribuídas ao SBC são resumidas na tabela a seguir:

|Nome  |Padrão |Conversão  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

Nos exemplos a seguir, há dois usuários, Alice e Bob. Alice é um usuário do teams cujo número é + 1 206 555 0100. Bob é um usuário PSTN cujo número é + 1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemplo 1: chamada de entrada para um número de 10 dígitos

Bob chama Alice usando um número que não seja E. 164 de dez dígitos. Bob disca 2065550100 para falar com Alice.
O SBC usa 2065550100 no RequestURI e em cabeçalhos e 4255550100 no cabeçalho de.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:2065550100@sbc.contoso.com|CONVIDAR sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|Para    |PARA: \<SIP:2065550100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemplo 2: chamada de entrada para um número de quatro dígitos

Bob chama Alice usando um número de quatro dígitos. Bob disca 0100 para falar com Alice.
O SBC usa 0100 no RequestURI e em cabeçalhos e 4255550100 no cabeçalho de.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:0100@sbc.contoso.com          |CONVIDAR sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemplo 3: chamada de saída usando um número não-E de dez dígitos. 164

Alice chama Bob usando um número de dez dígitos. Ana discagem 425 555 0100 para falar com o Bob.
O SBC está configurado para usar números de dez dígitos que não são E. 164 para equipes e usuários de PSTN.

Nesse cenário, um plano de discagem converte o número antes de enviá-lo para a interface de roteamento direto. Quando Ana entra em 425 555 0100 no cliente do Teams, o número é convertido em + 14255550100 pelo plano de discagem do país. Os números resultantes são uma normalização cumulativa das regras do plano de discagem e das regras de tradução do teams. As regras de tradução do teams removem o "+ 1" que foi adicionado pelo plano de discagem.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:+14255550100@sbc.contoso.com          |CONVIDAR sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|Para    |PARA: \<SIP:+14255550100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemplo 4: chamada de saída usando um número de quatro dígitos que não é E. 164

Alice chama Bob usando um número de quatro dígitos. Alice usa 0100 para se comunicar com Bob em chamadas ou usando um contato.
O SBC está configurado para usar números de quatro dígitos que não são E. 164 para usuários do Teams e números de dez dígitos para usuários de PSTN. O plano de discagem não é aplicado nesse cenário.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:0100@sbc.contoso.com           |CONVIDAR sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
