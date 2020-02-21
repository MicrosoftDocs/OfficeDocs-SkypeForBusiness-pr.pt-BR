---
title: Conectar o seu controlador de borda de sessão (SBC) ao roteamento direto
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
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157921"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar o seu controlador de borda de sessão (SBC) ao roteamento direto 

Este artigo descreve como conectar o seu controlador de borda de sessão (SBC) ao encaminhamento direto do sistema telefônico.  Esta é a etapa 1 das seguintes etapas para configurar o roteamento direto:

- **Etapa 1. Conecte seu SBC com o sistema telefônico e valide a conexão** (este artigo)
- Etapa 2. [Habilitar usuários para roteamento direto](direct-routing-enable-users.md)
- Etapa 3. [Configurar o encaminhamento de chamadas](direct-routing-voice-routing.md)
- Etapa 4. [Converter números em um formato alternativo](direct-routing-translate-numbers.md) 

Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).

Para conectar o SBC ao encaminhamento direto, você precisará: 

1. Conecte-se ao centro **de administração do Skype for Business online** usando o PowerShell.            
2. Conecte o SBC ao locatário.
3. Validar a conexão. 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectar-se ao Skype for Business online usando o PowerShell 

Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC com a interface de roteamento direto. Para abrir uma sessão do PowerShell, siga as etapas descritas em [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Depois de estabelecer uma sessão remota do PowerShell, valide se você pode ver os comandos para gerenciar o SBC. Para validar os comandos, digite ou copie e cole o seguinte comando na sessão do PowerShell e pressione ENTER: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

O comando retorna as quatro funções mostradas aqui que permitem que você gerencie o SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a>Conectar o SBC ao locatário 

Para conectar o SBC ao locatário, na sessão do PowerShell, digite o seguinte e pressione ENTER: 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. A Microsoft recomenda a configuração de um limite máximo de chamadas no SBC, usando as informações que podem ser encontradas na documentação do SBC. O limite acionará uma notificação se o SBC estiver no nível de capacidade.
  > 2. Você só pode emparelhar o SBC se a parte do domínio de seu FQDN corresponder a um dos domínios registrados em seu locatário \*, exceto. onmicrosoft.com. Não \*há suporte para o uso de nomes de domínio. onmicrosoft.com para o nome FQDN do SBC. Por exemplo, se você tiver dois nomes de domínio:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Para o nome do SBC, você pode usar o nome sbc.contoso.com. Se você tentar emparelhar o SBC com um nome SBC. contoso. ABC, o sistema não permitirá que o domínio não seja pertencente a esse locatário.<br/>
  > Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída. Se não for, você receberá o seguinte erro:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
Devolver
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Há opções adicionais que podem ser definidas durante o processo de conexão. No exemplo anterior, no entanto, somente os parâmetros mínimos necessários são exibidos. 
 
A tabela a seguir lista os parâmetros adicionais que você pode usar em definir parâmetros ```New-CsOnlinePstnGateway```para.

|Necessário?|Nome|Descrição|Padrão|Valores possíveis|Tipo e restrições|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Sim|FQDN|O nome FQDN do SBC |Nenhum|Nome do NoneFQDN, limite de 63 caracteres|Cadeia de caracteres, lista de caracteres permitidos e não permitidos em [convenções de nomenclatura no Active Directory para computadores, domínios, sites e UOs](https://support.microsoft.com/help/909264)|
|Não|MediaBypass |O parâmetro indicado do SBC dá suporte à bypass de mídia e o administrador deseja usá-la.|Nenhum|Verdadeiro<br/>Falso|Boolean|
|Sim|SipSignalingPort |Porta de escuta usada para comunicação com serviços de roteamento direto usando o protocolo TLS (Transport Layer Security).|Nenhum|Qualquer porta|0 a 65535 |
|Não|FailoverTimeSeconds |Quando definido como 10 (valor padrão), as chamadas de saída que não são respondidas pelo gateway em 10 segundos são roteadas para o próximo tronco disponível; Se não houver troncos adicionais, a chamada será automaticamente cancelada. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente. O valor padrão é 10.|254|Número|Núm|
|Não|ForwardCallHistory |Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco. Se habilitado, o proxy PSTN do Office 365 envia dois cabeçalhos: histórico-informações e referenciado por. O valor padrão é **false** ($false). |Falso|Verdadeiro<br/>Falso|Boolean|
|Não|ForwardPAI|Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador. Se habilitado, o cabeçalho de identificação privacidade: também será enviado. O valor padrão é **false** ($false).|Falso|Verdadeiro<br/>Falso|Boolean|
|Não|SendSIPOptions |Define se um SBC irá ou não enviará as opções de SIP. Se desabilitado, o SBC será excluído do sistema de monitoramento e alerta. É altamente recomendável que você ative as opções do SIP. O valor padrão é **true**. |Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não|MaxConcurrentSessions |Usado pelo sistema de alerta. Quando qualquer valor for definido, o sistema de alerta gerará um alerta para o administrador do locatário quando o número de sessões simultâneas for 90% ou superior a este valor. Se o parâmetro não estiver definido, os alertas não serão gerados. No entanto, o sistema de monitoramento reportará o número de sessões simultâneas a cada 24 horas. |Vazio|Vazio<br/>de 1 a 100.000 ||
|Não|MediaRelayRoutingLocationOverride |Permite a seleção de caminho para mídia manualmente. O roteamento direto atribui um datacenter para caminho de mídia com base no IP público do SBC. Sempre selecionamos mais próximo ao Datacenter do SBC. No entanto, em alguns casos, um IP público de, por exemplo, um intervalo dos EUA pode ser atribuído a um SBC localizado na Europa. Nesse caso, usaremos o caminho de mídia ideal. Esse parâmetro permite definir manualmente a região preferida para tráfego de mídia. A Microsoft recomenda definir esse parâmetro apenas se os logs de chamada indicar claramente que a atribuição automática do Media Center para o caminho de mídia não atribui o mais próximo possível ao datacenter de SBC. |Nenhum|Códigos de país no formato ISO||
|Não|Habilitado|Usado para habilitar este SBC para chamadas de saída. Pode ser usado para remover temporariamente o SBC enquanto ele está sendo atualizado ou durante a manutenção. |Falso|Verdadeiro<br/>Falso|Boolean|
 
## <a name="verify-the-sbc-connection"></a>Verificar a conexão SBC 

Para verificar a conexão: 
- Verifique se o SBC está na lista de SBCs emparelhado. 
- Validar opções de SIP. 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verifique se o SBC está na lista de SBCs emparelhado 

Depois de conectar o SBC, valide se o SBC está presente na lista de SBCs emparelhada executando o seguinte comando em uma sessão remota do PowerShell: 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

O gateway emparelhado deve aparecer na lista, como mostrado no exemplo abaixo, e o parâmetro **Enabled** deve exibir um valor de **true**. 


Que retorna:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a>Validar o fluxo de opções do SIP 

Para validar o emparelhamento usando as opções de SIP de saída, use a interface de gerenciamento do SBC e confirme se o SBC recebe as respostas de OK do 200 para suas mensagens de opções de saída.

Quando o roteamento direto vê as opções de entrada, ele começará a enviar mensagens de opções de SIP de saída para o FQDN do SBC configurado no campo de cabeçalho de contato na mensagem de opções de entrada. 

Para validar o emparelhamento usando as opções do SIP de entrada, use a interface de gerenciamento do SBC e veja se o SBC envia uma resposta às mensagens de opções que chegam do roteamento direto e que o código de resposta que ele envia é 200 OK.


## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
