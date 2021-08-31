---
title: Conexão controlador de borda de sessão (SBC) para Roteamento Direto
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
description: Saiba como configurar e conectar seu SBC ao Sistema de Telefonia Roteamento Direto.
ms.openlocfilehash: d18ff8a8f0c398979a2c04d3aca1ff69b8bdc8f1
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726120"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conexão controlador de borda de sessão (SBC) para Roteamento Direto

Este artigo descreve como configurar um Controlador de Borda de Sessão (SBC) e conectá-lo Sistema de Telefonia Roteamento Direto.  Esta é a etapa 1 das seguintes etapas para configurar o Roteamento Direto:

- **Etapa 1. Conexão seu SBC com Sistema de Telefonia e valide a conexão** (Este artigo)
- Etapa 2. [Habilitar usuários para Roteamento Direto](direct-routing-enable-users.md)
- Etapa 3. [Configurar roteamento de chamadas](direct-routing-voice-routing.md)
- Etapa 4. [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md)

Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).

Você pode usar o [Microsoft Teams de](#using-the-microsoft-teams-admin-center) administração ou [o PowerShell](#using-powershell) para configurar e conectar um SBC ao Roteamento Direto.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para **Roteamento Direto** de  >  Voz e clique na guia **SBCs.**
2. Clique em **Adicionar**.
3. Insira um FQDN para o SBC. <br><br>Certifique-se de que a parte do nome de domínio do FQDN corresponde a um domínio registrado em seu locatário e tenha em mente que o nome de domínio não é suportado para o nome de domínio `*.onmicrosoft.com` FQDN SBC. Por exemplo, se você tiver dois nomes de domínio `contoso.com` e , use como o nome `contoso.onmicrosoft.com` `sbc.contoso.com` SBC. Se estiver usando um subdomínio, certifique-se de que esse subdomínio também esteja registrado em seu locatário. Por exemplo, se você quiser usar `sbc.service.contoso.com` , então precisa ser `service.contoso.com` registrado.
4. Configure as configurações a seguir para o SBC, com base nas necessidades da sua organização. Para obter detalhes sobre cada uma dessas configurações, consulte [Configurações SBC](#sbc-settings).

    ![Captura de tela da página adicionar SBC no Microsoft Teams de administração.](media/direct-routing-add-sbc.png)

5. Quando terminar, clique em **Salvar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Para conectar seu SBC ao Roteamento Direto, você precisará:

1. [Conexão para Skype for Business Online usando o PowerShell](#connect-to-skype-for-business-online-by-using-powershell).
2. [Conexão SBC para o locatário](#connect-the-sbc-to-the-tenant).
3. [Verifique a conexão SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conexão para Skype for Business Online usando o PowerShell

Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC à interface de Roteamento Direto. Para abrir uma sessão do PowerShell, siga as etapas descritas em [Configurar o computador para](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)Windows PowerShell .
 
Depois de estabelecer uma sessão remota do PowerShell, verifique se você pode ver os comandos para gerenciar o SBC. Para verificar os comandos, digite ou copie e colar o seguinte comando na sessão do PowerShell e pressione Enter: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

O comando retorna as quatro funções mostradas aqui que permitirão que você gerencie o SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Conexão SBC para o locatário

Use o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) para conectar o SBC ao locatário. Em uma sessão do PowerShell, digite o seguinte e pressione Enter:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Recomendamos definir um limite máximo de chamada no SBC usando informações que podem ser encontradas na documentação do SBC. O limite disparará uma notificação se o SBC estiver no nível de capacidade.
  > 2. Você só poderá conectar o SBC se a parte de domínio de seu FQDN corresponde a um dos domínios registrados em seu locatário, exceto \* .onmicrosoft.com. O uso de nomes de domínio \* .onmicrosoft.com não é suportado para o nome FQDN SBC. Por exemplo, se você tiver dois nomes de domínio, **contoso**.com e **contoso**.onmicrosoft.com, poderá usar sbc.contoso.com para o nome SBC. Se você tentar conectar o SBC a um nome como sbc.contoso.abc, o sistema não permitirá, pois o domínio não é de propriedade desse locatário.<br/>
  > Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída. Caso não seja, você receberá o seguinte erro:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Veja um exemplo:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Que retorna:

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

> [!NOTE]
> Este exemplo mostra apenas os parâmetros mínimos necessários. Há parâmetros adicionais que você pode definir com o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) durante o processo de conexão. Para saber mais, confira [Configurações SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Verificar a conexão SBC

Para verificar a conexão:

- [Verifique se o SBC está na lista de SBCs emparelhados.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Validar opções SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verifique se o SBC está na lista de SBCs emparelhados

Depois de conectar o SBC, use o cmdlet [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) para verificar se o SBC está presente na lista de SBCs emparelhados. Digite o seguinte em uma sessão remota do PowerShell e pressione Enter:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

O gateway emparelhado deve aparecer na lista, conforme mostrado no exemplo abaixo, e o parâmetro **Enabled** deve exibir um valor **true**.

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

#### <a name="validate-sip-options"></a>Validar opções SIP

Para validar o emparelhamento usando opções SIP de saída, use a interface de gerenciamento SBC e confirme se o SBC recebe 200 respostas OK para suas mensagens OPTIONS de saída.

Quando o Roteamento Direto vir OPÇÕES de entrada, ele começará a enviar mensagens de opções SIP de saída para o FQDN SBC configurado no campo De contato do header na mensagem OPÇÕES de entrada. 

Para validar o emparelhamento usando opções SIP de entrada, use a interface de gerenciamento SBC e veja se o SBC envia uma resposta às mensagens OPTIONS que chegam do Roteamento Direto e que o código de resposta que ele envia é 200 OK.

## <a name="sbc-settings"></a>Configurações SBC

Esta tabela lista as opções que você pode definir para o SBC no centro de administração Microsoft Teams e usando o cmdlet [New-CsOnlinePSTNGateway.](/powershell/module/skype/new-csonlinepstngateway)

|Necessário?|Microsoft Teams de centro de administração|Parâmetro do PowerShell|Descrição|Padrão|Valores possíveis|Tipo e restrições|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sim|**Adicionar um FQDN para o SBC**|FQDN |Nenhum|Nome do FQDN, limite 63 caracteres|String, consulte a lista de caracteres permitidos e não permitidos em Convenções de Nomenal no Active Directory para [computadores, domínios, sites e OUs](https://support.microsoft.com/help/909264)|
|Não|**Habilitado**|Habilitado|Use para ativar o SBC para chamadas de saída. Você pode usar isso para remover temporariamente o SBC do serviço enquanto ele está sendo atualizado ou durante a manutenção. |Falso|Verdadeiro<br/>Falso|Boolean|
|Sim|**Porta de sinalização SIP**|SipSignalingPort |Essa é a porta de escuta usada para se comunicar com o Roteamento Direto usando o protocolo TLS (Camada de Transporte).|Nenhum|Qualquer porta|0 a 65535 |
|Não|**Enviar opções SIP**|SendSIPOptions |Define se o SBC enviará mensagens de opções SIP. É altamente recomendável ativar essa configuração. Quando essa configuração é desligada, o SBC é excluído do sistema de Monitoramento e Alerta.|Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não|**Histórico de chamada de encaminhamento**|ForwardCallHistory |Indica se as informações do histórico de chamada são encaminhadas pelo tronco. Quando você ativar isso, o proxy Microsoft 365 ou Office 365 enviará um header History-info e Referred-by. |Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Header forward P-Asserted-identity (PAI)**|ForwardPAI|Indica se o header pai é encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador. Se essa configuração estiver em, o header Privacy:ID também será enviado.|Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Capacidade de chamada simultânea**|MaxConcurrentSessions |Quando você definir um valor, o sistema de alertas notificará você quando o número de sessões simultâneas for 90% ou superior a esse valor. Se você não definir um valor, os alertas não são gerados. No entanto, o sistema de monitoramento relatará o número de sessões simultâneas a cada 24 horas. |Null|Null<br/>1 a 100.000 ||
|Não|**Códigos de resposta de failover**|FailoverResponseCodes<br>|Se o Roteamento Direto receber qualquer código de erro SIP 4xx ou 6xx em resposta a um Convite de saída, a chamada será considerada concluída por padrão. Saída significa uma chamada de um cliente Teams para a PSTN com fluxo de tráfego: Teams cliente -> Roteamento Direto -> SBC -> rede de telefonia). Quando você especifica um código de resposta de failover, isso força o Roteamento Direto a tentar outro SBC (se houver outro SBC na política de roteamento de voz do usuário) quando ele receber os códigos especificados se o SBC não puder fazer uma chamada por causa da rede ou outros problemas. Para saber mais, confira [Failover de códigos SIP específicos recebidos do Controlador](direct-routing-trunk-failover-on-outbound-call.md)de Borda de Sessão (SBC).|408, 503, 504||Int|
|Não|**Tempos de failover (segundos)**|FailoverTimeSeconds |Quando você definir um valor, as chamadas de saída que não são atendidas pelo gateway no tempo definido são roteadas para o próximo tronco disponível. Se não houver troncos adicionais, a chamada será automaticamente retirada. O valor padrão é 10 segundos. Em uma organização com redes lentas e respostas de gateway, isso pode resultar em chamadas sendo retiradas desnecessariamente.|10|Número|Int|
|Não|**País ou região preferencial para tráfego de mídia**|MediaRelayRoutingLocationOverride |Use para definir manualmente seu país ou região preferencial para tráfego de mídia. Recomendamos definir isso somente se os logs de chamada indicarem claramente que a atribuição padrão do datacenter para o caminho de mídia não usa o caminho mais próximo do datacenter SBC. Por padrão, o Roteamento Direto atribui um datacenter com base no endereço IP público do SBC e sempre seleciona o caminho mais próximo do datacenter SBC. No entanto, em alguns casos, o caminho padrão pode não ser o caminho ideal. Esse parâmetro permite definir manualmente a região preferencial para tráfego de mídia. |Nenhum|Códigos de país no formato ISO||
|Não|**SBC dá suporte a PIDF/LO para chamadas de emergência**|PidfloSupported|Especifique se o SBC dá suporte ao Objeto de Local de Formato de Dados de Presença (PIDF/LO) para chamadas de emergência.||||
|Não| - |MediaBypass|Essa configuração indica se o SBC dá suporte ao bypass de mídia e se você deseja usá-lo para esse SBC. |Nenhum|Verdadeiro<br/>Falso|Boolean|

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)