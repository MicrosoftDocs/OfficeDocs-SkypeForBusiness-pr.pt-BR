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
description: Saiba como configurar e conectar seu SBC ao encaminhamento direto do sistema telefônico.
ms.openlocfilehash: 8ceb4d1811b479fbcdc0d4ca83f4dbc4672227bd
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691257"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar o seu controlador de borda de sessão (SBC) ao roteamento direto

Este artigo descreve como configurar um SBC (controlador de borda de sessão) e conectá-lo ao roteamento direto do sistema telefônico.  Esta é a etapa 1 das etapas a seguir para configurar o roteamento direto:

- **Etapa 1. Conecte seu SBC com o sistema telefônico e valide a conexão** (este artigo)
- Etapa 2. [Habilitar usuários para roteamento direto](direct-routing-enable-users.md)
- Etapa 3. [Configurar o encaminhamento de chamadas](direct-routing-voice-routing.md)
- Etapa 4. [Converter números em um formato alternativo](direct-routing-translate-numbers.md) 

Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).

Você pode usar o [centro de administração do Microsoft Teams](#using-the-microsoft-teams-admin-center) ou o [PowerShell](#using-powershell) para configurar e conectar um SBC ao roteamento direto.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá **Voice**para  >  **Roteamento direto**de voz e clique na guia **SBCS** .
2. Clique em **Adicionar**.
3. Digite um FQDN para o SBC. <br><br>Verifique se a parte do nome do domínio do FQDN corresponde a um domínio registrado em seu locatário e lembre-se de que o nome de `*.onmicrosoft.com` domínio não tem suporte para o nome de domínio do FQDN do SBC. Por exemplo, se você tiver dois nomes de domínio `contoso.com` e `contoso.on.microsoft.com` usar `sbc.contoso.com` como o nome SBC.
4. Defina as configurações a seguir para o SBC, com base nas necessidades da sua organização. Para obter detalhes sobre cada uma dessas configurações, consulte [configurações de SBC](#sbc-settings).

    ![Captura de tela da página Adicionar SBC no centro de administração do Microsoft Teams](media/direct-routing-add-sbc.png)

5. Quando terminar, clique em **Salvar**.

## <a name="using-powershell"></a>Usando o PowerShell

Para conectar o SBC ao encaminhamento direto, você precisará:

1. [Conecte-se ao Skype for Business online usando o PowerShell](#connect-to-skype-for-business-online-by-using-powershell).
2. [Conecte o SBC ao locatário](#connect-the-sbc-to-the-tenant).
3. [Verifique a conexão SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectar-se ao Skype for Business online usando o PowerShell

Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC com a interface de roteamento direto. Para abrir uma sessão do PowerShell, siga as etapas descritas em [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Depois de estabelecer uma sessão remota do PowerShell, verifique se é possível ver os comandos para gerenciar o SBC. Para verificar os comandos, digite ou copie e cole o seguinte comando na sessão do PowerShell e pressione ENTER: 

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

### <a name="connect-the-sbc-to-the-tenant"></a>Conectar o SBC ao locatário

Use o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para conectar o SBC ao locatário. Em uma sessão do PowerShell, digite o seguinte e pressione ENTER:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Recomendamos que você defina um limite máximo de chamadas no SBC usando as informações que podem ser encontradas na documentação do SBC. O limite acionará uma notificação se o SBC estiver no nível de capacidade.
  > 2. Você só poderá se conectar ao SBC se a parte do domínio de seu FQDN corresponder a um dos domínios registrados em seu locatário, exceto \* . onmicrosoft.com. \*Não há suporte para o uso de nomes de domínio. onmicrosoft.com para o nome FQDN do SBC. Por exemplo, se você tiver dois nomes de domínio, **contoso**. com e **contoso**. onmicrosoft.com, poderá usar SBC. contoso. con para o nome do SBC. Se você tentar conectar o SBC com um nome como o SBC. contoso. ABC, o sistema não permitirá que o domínio não seja pertencente a esse locatário.<br/>
  > Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída. Caso contrário, você receberá a seguinte mensagem de erro:<br/>
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
> Este exemplo mostra apenas os parâmetros mínimos necessários. Há parâmetros adicionais que você pode definir com o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) durante o processo de conexão. Para saber mais, confira [configurações de SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Verificar a conexão SBC

Para verificar a conexão:

- [Verifique se o SBC está na lista de SBCS emparelhado](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Validar opções de SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verifique se o SBC está na lista de SBCs emparelhado

Depois de conectar o SBC, use o cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) para verificar se o SBC está presente na lista de SBCS emparelhado. Digite o seguinte em uma sessão remota do PowerShell e pressione ENTER:

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

#### <a name="validate-sip-options"></a>Validar opções do SIP

Para validar o emparelhamento usando as opções de SIP de saída, use a interface de gerenciamento do SBC e confirme se o SBC recebe as respostas de OK do 200 para suas mensagens de opções de saída.

Quando o roteamento direto vê as opções de entrada, ele começará a enviar mensagens de opções de SIP de saída para o FQDN do SBC configurado no campo de cabeçalho de contato na mensagem de opções de entrada. 

Para validar o emparelhamento usando as opções do SIP de entrada, use a interface de gerenciamento do SBC e veja se o SBC envia uma resposta às mensagens de opções que chegam do roteamento direto e que o código de resposta que ele envia é 200 OK.

## <a name="sbc-settings"></a>Configurações do SBC

Esta tabela lista as opções que você pode definir para o SBC no centro de administração do Microsoft Teams e usando o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) .

|Necessário?|Configuração do centro de administração do Microsoft Teams|Parâmetro do PowerShell|Descrição|Padrão|Valores possíveis|Tipo e restrições|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sim|**Adicionar um FQDN para o SBC**|FQDN |Nenhum|Nome FQDN, limite de 63 caracteres|Confira a lista de caracteres permitidos e não permitidos em convenções de [nomenclatura no Active Directory para computadores, domínios, sites e UOs](https://support.microsoft.com/help/909264)|
|Não|**Habilitado**|Habilitado|Use para ativar o SBC para chamadas de saída. Você pode usá-lo para remover temporariamente o SBC do serviço enquanto ele estiver sendo atualizado ou durante a manutenção. |Falso|Verdadeiro<br/>Falso|Boolean|
|Sim|**Porta de sinalização SIP**|SipSignalingPort |Essa é a porta de escuta usada para se comunicar com o roteamento direto usando o protocolo TLS (Transport Layer).|Nenhum|Qualquer porta|0 a 65535 |
|Não|**Opções de enviar SIP**|SendSIPOptions |Define se o SBC enviará mensagens de opções SIP. É altamente recomendável que você ative essa configuração. Quando essa configuração está desativada, o SBC é excluído do sistema de monitoramento e de alerta.|Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não|**Encaminhar histórico de chamadas**|ForwardCallHistory |Indica se as informações do histórico de chamadas são encaminhadas pelo tronco. Quando você ativa isso, o Microsoft 365 ou o proxy do Office 365 envia um histórico-informações e um cabeçalho referenciado. |Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Encaminhar cabeçalho de identidade (PAI)-declarado P**|ForwardPAI|Indica se o cabeçalho PAI é encaminhado juntamente com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador. Se essa configuração estiver ativada, o cabeçalho privacidade: ID também será enviado.|Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Capacidade de chamadas simultâneas**|MaxConcurrentSessions |Quando você definir um valor, o sistema de alerta o notificará quando o número de sessões simultâneas for 90% ou superior a este valor. Se você não definir um valor, os alertas não serão gerados. No entanto, o sistema de monitoramento reportará o número de sessões simultâneas a cada 24 horas. |Vazio|Vazio<br/>de 1 a 100.000 ||
|Não|**Códigos de resposta de failover**|FailoverResponseCodes<br>|Se o roteamento direto receber um código de erro 4xx ou 6xx SIP em resposta a um convite de saída, a chamada será considerada concluída por padrão. Saída significa uma chamada de um cliente do teams para o PSTN com fluxo de tráfego: cliente do teams-> Direct Routing-> SBC-> Telephony networky). Quando você especifica um código de resposta de failover, isso força o roteamento direto a experimentar outro SBC (se houver outro SBC na política de roteamento de voz do usuário) quando receber os códigos especificados se o SBC não puder fazer uma chamada devido a uma rede ou outros problemas. Para saber mais, consulte [failover de códigos SIP específicos recebidos do controlador de borda de sessão (SBC)](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Núm|
|Não|**Tempo de failover (segundos)**|FailoverTimeSeconds |Quando você define um valor, as chamadas de saída que não são respondidas pelo gateway dentro do momento definido são roteadas para o próximo tronco disponível. Se não houver troncos adicionais, a chamada será automaticamente cancelada. O valor padrão é 10 segundos. Em uma organização com redes lentas e respostas de gateway, isso pode fazer com que as chamadas sejam canceladas desnecessariamente.|254|Número|Núm|
|Não|**País ou região preferencial para tráfego de mídia**|MediaRelayRoutingLocationOverride |Use para definir manualmente seu país ou região preferencial para o tráfego de mídia. Recomendamos que você defina isso somente se os logs de chamada indicar claramente que a atribuição padrão do datacenter para o caminho de mídia não usa o caminho mais próximo ao Datacenter do SBC. Por padrão, o roteamento direto atribui um datacenter com base no endereço IP público do SBC e sempre seleciona o caminho mais próximo ao Datacenter do SBC. No entanto, em alguns casos, o caminho padrão pode não ser o caminho ideal. Esse parâmetro permite definir manualmente a região preferida para tráfego de mídia. |Nenhum|Códigos de país no formato ISO||
|Não|**O SBC tem suporte para PIDF/LO para chamadas de emergência**|PidfloSupported|Especifique se o SBC dá suporte ao objeto de local de formato de dados de informações de presença (PIDF/LO) para chamadas de emergência.||||
|Não|**Ligar para telefone enquanto estiver tentando localizar o usuário**|GenerateRingingWhileLocatingUser|Defina se um sinal de áudio é reproduzido no chamador para indicar que as equipes estão no processo de estabelecimento da chamada. Essa configuração aplica-se somente ao roteamento direto no modo de bypass de não mídia. Às vezes, as chamadas recebidas da PSTN para os clientes do teams podem levar mais tempo do que o esperado para serem estabelecidas. Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não entra em contato e a chamada pode ser cancelada por alguns provedores de telecomunicações. Esta configuração ajuda a evitar silêncios inesperados que podem ocorrer nesses cenários.|Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não| - |MediaBypass|Essa configuração indica se o SBC dá suporte à bypass de mídia e se você deseja usá-lo para esse SBC. |Nenhum|Verdadeiro<br/>Falso|Boolean|

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
