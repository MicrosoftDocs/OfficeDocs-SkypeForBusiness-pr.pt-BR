---
title: Traduzir números de telefone para Roteamento Direto
ms.reviewer: filippse
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
description: Saiba como configurar o Roteamento Direto do Sistema de Telefone da Microsoft.
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727763"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traduzir números de telefone para um formato alternativo

Este artigo descreve como traduzir números para chamadas de saída e de entrada para um formato alternativo. Esta é a etapa 4 das seguintes etapas para configurar o Roteamento Direto:

- Etapa 1. [Conectar o SBC ao Microsoft Phone System e validar a conexão](direct-routing-connect-the-sbc.md) 
- Etapa 2. [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)   
- Etapa 3. [Configurar o roteamento de voz](direct-routing-voice-routing.md)
- **Etapa 4. Traduzir números para um formato alternativo**   (Este artigo)

Para obter informações sobre todas as etapas necessárias para configurar o [Roteamento Direto, consulte Configurar Roteamento Direto](direct-routing-configure.md).

Às vezes, os administradores de locatários podem querer alterar o número para chamadas de saída e/ou de entrada com base nos padrões criados para garantir a interoperabilidade com os SBCs (Controladores de Borda de Sessão). Este artigo descreve como você pode especificar uma política de Regras de Tradução de Números para traduzir números para um formato alternativo. 

Você pode usar a política Regras de Tradução numérica para traduzir números para o seguinte:

- Chamadas de entrada: chamadas de um ponto de extremidade PSTN (chamador) para um cliente do Teams (callee)
- Chamadas de saída: chamadas de um cliente do Teams (chamador) para um ponto de extremidade PSTN (callee)

A política é aplicada no nível SBC. Você pode atribuir várias regras de tradução a um SBC, que são aplicadas na ordem em que elas aparecem quando você as lista no PowerShell. Você também pode alterar a ordem das regras na política.

Para criar, modificar, exibir e excluir regras de manipulação de número, use os [cmdlets New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) e [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) .

Para atribuir, configurar e listar regras de manipulação de números em SBCs, use os cmdlets [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) e [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) junto com os parâmetros InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules e OutboundPSTNNumberTranslationRules.

> [!NOTE]
> O número total máximo de regras de tradução é 400, o comprimento máximo do nome do parâmetro de tradução é de 100 símbolos, o comprimento máximo do padrão de parâmetro de tradução é de 1024 símbolos e o comprimento máximo de tradução do parâmetro de tradução é de 256 símbolos.


## <a name="example-sbc-configuration"></a>Configuração SBC de exemplo

Para esse cenário, o cmdlet New-CsOnlinePSTNGateway é executado para criar a seguinte configuração SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

As regras de tradução atribuídas ao SBC são resumidas na seguinte tabela:

|Nome  |Padrão |Conversão  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

Nos exemplos a seguir, há dois usuários, Alice e Bob. Alice é um usuário do Teams cujo número é +1 206 555 0100. Bob é um usuário PSTN cujo número é +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemplo 1: chamada de entrada para um número de dez dígitos

Bob chama Alice usando um número de dez dígitos que não é E.164. Bob disca 2065550100 para alcançar Alice.
O SBC usa 2065550100 nos cabeçalhos RequestURI e To e 4255550100 no cabeçalho De.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVITE sip:2065550100@sbc.contoso.com|CONVITE sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|PARA    |PARA: \<sip:2065550100@sbc.contoso.com>|PARA: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemplo 2: chamada de entrada para um número de quatro dígitos

Bob chama Alice usando um número de quatro dígitos. Bob disca 0100 para alcançar Alice.
O SBC usa 0100 nos cabeçalhos RequestURI e To e 4255550100 no cabeçalho De.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVITE sip:0100@sbc.contoso.com          |CONVITE sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|PARA    |PARA: \<sip:0100@sbc.contoso.com>|PARA: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemplo 3: chamada de saída usando um número de dez dígitos que não é E.164

Alice chama Bob usando um número de dez dígitos. Alice disca 425 555 0100 para alcançar Bob.
O SBC está configurado para usar números de dez dígitos não E.164 para usuários do Teams e PSTN.

Nesse cenário, um plano de discagem traduz o número antes de enviá-lo para a interface de Roteamento Direto. Quando Alice insere 425 555 0100 no cliente do Teams, o número é traduzido para +14255550100 pelo plano de discagem do país. Os números resultantes são uma normalização cumulativa das regras de plano de discagem e das regras de tradução do Teams. As regras de tradução do Teams removem o "+1" que foi adicionado pelo plano de discagem.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVITE sip:+14255550100@sbc.contoso.com          |CONVITE sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|PARA    |PARA: \<sip:+14255550100@sbc.contoso.com>|PARA: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemplo 4: chamada de saída usando um número de quatro dígitos que não é E.164

Alice chama Bob usando um número de quatro dígitos. Alice usa o 0100 para acessar Bob a partir de Chamadas ou usando um contato.
O SBC está configurado para usar números de quatro dígitos não E.164 para usuários do Teams e números de dez dígitos para usuários PSTN. O plano de discagem não é aplicado neste cenário.


|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|Requesturi  |CONVITE sip:0100@sbc.contoso.com           |CONVITE sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|PARA    |PARA: \<sip:0100@sbc.contoso.com>|PARA: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
