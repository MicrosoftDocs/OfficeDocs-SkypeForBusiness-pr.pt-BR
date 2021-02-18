---
title: Conectar seu Controlador de Borda de Sessão (SBC) ao Roteamento Direto
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
description: Saiba como configurar e conectar seu SBC ao Roteamento Direto do Sistema telefônico.
ms.openlocfilehash: 4240eb4000e813df51b2678ad2e9c37f6bc0c2ac
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278701"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar seu Controlador de Borda de Sessão (SBC) ao Roteamento Direto

Este artigo descreve como configurar um SBC (Controlador de Borda de Sessão) e conectá-lo ao Roteamento Direto do Sistema telefônico.  Esta é a etapa 1 das seguintes etapas para configurar o Roteamento Direto:

- **Etapa 1. Conecte seu SBC ao Sistema telefônico e valide a conexão** (este artigo)
- Etapa 2. [Habilitar usuários para Roteamento Direto](direct-routing-enable-users.md)
- Etapa 3. [Configurar roteamento de chamadas](direct-routing-voice-routing.md)
- Etapa 4. [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md)

Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configurar Roteamento Direto.](direct-routing-configure.md)

Você pode usar o [Centro de administração do Microsoft Teams](#using-the-microsoft-teams-admin-center) ou o [PowerShell](#using-powershell) para configurar e conectar um SBC ao Roteamento Direto.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para **Roteamento Direto** de Voz e  >  clique na **guia SBCs.**
2. Clique em **Adicionar**.
3. Insira um FQDN para o SBC. <br><br>Certifique-se de que a parte de nome de domínio do FQDN corresponde a um domínio registrado em seu locatário e lembre-se de que não há suporte para o nome de domínio `*.onmicrosoft.com` FQDN SBC. Por exemplo, se você tiver dois nomes de domínio `contoso.com` `contoso.onmicrosoft.com` e, usar `sbc.contoso.com` como o nome SBC. Se estiver usando um subdomínio, certifique-se de que esse subdomínio também esteja registrado em seu locatário. Por exemplo, se você quiser `sbc.service.contoso.com` usar, precisará `service.contoso.com` ser registrado.
4. Configure as configurações a seguir para o SBC, com base nas necessidades da sua organização. Para obter detalhes sobre cada uma dessas configurações, consulte as [configurações de SBC.](#sbc-settings)

    ![Captura de tela da página Adicionar SBC no Centro de administração do Microsoft Teams](media/direct-routing-add-sbc.png)

5. Quando terminar, clique em **Salvar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Para conectar seu SBC ao Roteamento Direto, você precisará:

1. [Conecte-se ao Skype for Business Online usando o PowerShell.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Conecte o SBC ao locatário.](#connect-the-sbc-to-the-tenant)
3. [Verifique a conexão SBC.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectar-se ao Skype for Business Online usando o PowerShell

Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC à interface de Roteamento Direto. Para abrir uma sessão do PowerShell, siga as etapas descritas em [Configurar seu computador para Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
Depois de estabelecer uma sessão remota do PowerShell, verifique se você pode ver os comandos para gerenciar o SBC. Para verificar os comandos, digite ou copie e copie o seguinte comando na sessão do PowerShell e pressione Enter: 

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

### <a name="connect-the-sbc-to-the-tenant"></a>Conectar o SBC ao locatário

Use o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para conectar o SBC ao locatário. Em uma sessão do PowerShell, digite o seguinte e pressione Enter:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Recomendamos definir um limite máximo de chamada no SBC usando informações que podem ser encontradas na documentação SBC. O limite disparará uma notificação se o SBC estiver no nível de capacidade.
  > 2. Você só poderá conectar o SBC se a parte de domínio de seu FQDN corresponde a um dos domínios registrados em seu locatário, exceto \* .onmicrosoft.com. O \* uso onmicrosoft.com de domínio .onmicrosoft.com não é suportado para o nome FQDN SBC. Por exemplo, se você tiver dois nomes de domínio, **contoso**.com e **contoso**.onmicrosoft.com, poderá usar sbc.contoso.com para o nome SBC. Se você tentar conectar o SBC com um nome como sbc.contoso.abc, o sistema não permitirá que você, uma vez que o domínio não é de propriedade desse locatário.<br/>
  > Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída. Caso não, você receberá o seguinte erro:<br/>
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
> Este exemplo mostra apenas os parâmetros mínimos necessários. Há parâmetros adicionais que você pode definir com o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) durante o processo de conexão. Para saber mais, confira as [configurações de SBC.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Verificar a conexão SBC

Para verificar a conexão:

- [Verifique se o SBC está na lista de SBCs emparelhados.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Valide as opções SIP.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verificar se o SBC está na lista de SBCs emparelhados

Depois de conectar o SBC, use o cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) para verificar se o SBC está presente na lista de SBCs emparelhados. Digite o seguinte em uma sessão remota do PowerShell e pressione Enter:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

O gateway emparelhado deve aparecer na lista, conforme  mostrado no exemplo abaixo, e o parâmetro Habilitado deve exibir um valor de **True.**

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

Para validar o emparelhamento usando opções SIP de saída, use a interface de gerenciamento SBC e confirme se o SBC recebe 200 respostas OK às suas mensagens OPÇÕES de saída.

Quando o Roteamento Direto vir OPÇÕES de entrada, ele começará a enviar mensagens de opções SIP de saída para o FQDN SBC configurado no campo de header contato na mensagem OPÇÕES de entrada. 

Para validar o emparelhamento usando opções SIP de entrada, use a interface de gerenciamento SBC e veja se o SBC envia uma resposta para as mensagens OPÇÕES que vêm do Roteamento Direto e que o código de resposta que ele envia é 200 OK.

## <a name="sbc-settings"></a>Configurações de SBC

Esta tabela lista as opções que você pode definir para o SBC no centro de administração do Microsoft Teams e usando o cmdlet [New-CsOnlinePSTNGateway.](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)

|Necessário?|Configuração do Centro de administração do Microsoft Teams|Parâmetro do PowerShell|Descrição|Padrão|Valores possíveis|Tipo e restrições|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sim|**Adicionar um FQDN para o SBC**|FQDN |Nenhum|Nome FQDN, limite de 63 caracteres|Cadeia de caracteres, veja a lista de caracteres permitidos e não permitidos em convenções de nomenbo no Active Directory para [computadores, domínios, sites e OUs](https://support.microsoft.com/help/909264)|
|Não|**Habilitado**|Habilitado|Use para ativar o SBC para chamadas de saída. Você pode usá-lo para remover temporariamente o SBC do serviço enquanto ele estiver sendo atualizado ou durante a manutenção. |Falso|Verdadeiro<br/>Falso|Boolean|
|Sim|**Porta de sinalização SIP**|SipSignalingPort |Essa é a porta de ouvindo que é usada para se comunicar com o Roteamento Direto usando o protocolo TLS (Camada de Transporte).|Nenhum|Qualquer porta|0 a 65535 |
|Não|**Enviar opções SIP**|SendSIPOptions |Define se o SBC enviará mensagens de opções SIP. É altamente recomendável ativar essa configuração. Quando essa configuração está desligada, o SBC é excluído do sistema de Monitoramento e Alerta.|Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não|**Encaminhar histórico de chamada**|ForwardCallHistory |Indica se as informações do histórico de chamada são encaminhadas pelo tronco. Quando você a ativar, o proxy do Microsoft 365 ou do Office 365 enviará um header Histórico-informações e Encaminhamento por. |Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Forward P-Asserted-identity (PAI) header**|ForwardPAI|Indica se o header PAI foi encaminhado juntamente com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador. Se essa configuração estiver on, o header privacy:ID também será enviado.|Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Capacidade de chamada simultânea**|Maxconcurrentsessions |Quando você definir um valor, o sistema de alertas notificará você quando o número de sessões simultâneas for 90% ou superior a esse valor. Se você não definir um valor, os alertas não são gerados. No entanto, o sistema de monitoramento relatará o número de sessões simultâneas a cada 24 horas. |Null|Null<br/>De 1 a 100.000 ||
|Não|**Códigos de resposta de failover**|FailoverResponseCodes<br>|Se o Roteamento Direto receber qualquer código de erro SIP 4xx ou 6xx em resposta a um Convite de saída, a chamada será considerada concluída por padrão. Saída significa uma chamada de um cliente do Teams para o PSTN com fluxo de tráfego: cliente do Teams -> Roteamento Direto -> SBC -> rede de telefonia). Quando você especifica um código de resposta de failover, isso força o Roteamento Direto a experimentar outro SBC (se houver outro SBC na política de roteamento de voz do usuário) quando ele receber os códigos especificados se o SBC não puder fazer uma chamada por causa da rede ou outros problemas. Para saber mais, consulte [Failover de códigos SIP específicos recebidos do Controlador de](direct-routing-trunk-failover-on-outbound-call.md)Borda de Sessão (SBC).|408, 503, 504||Int|
|Não|**Tempos de failover (segundos)**|FailoverTimeSeconds |Quando você definir um valor, as chamadas de saída que não são atendidas pelo gateway dentro do tempo definido são roteadas para o próximo tronco disponível. Se não houver troncos adicionais, a chamada será automaticamente retirada. O valor padrão é 10 segundos. Em uma organização com redes lentas e respostas de gateway, isso pode resultar em chamadas desnecessariamente desnecessariamente.|10|Número|Int|
|Não|**País ou região preferencial para tráfego de mídia**|MediaRelayRoutingLocationOverride |Use para definir manualmente seu país ou região preferencial para tráfego de mídia. Recomendamos definir isso somente se os logs de chamada indicarem claramente que a atribuição padrão do datacenter para o caminho de mídia não usa o caminho mais próximo do datacenter SBC. Por padrão, o Roteamento Direto atribui um datacenter com base no endereço IP público do SBC e sempre seleciona o caminho mais próximo do datacenter SBC. No entanto, em alguns casos, o caminho padrão pode não ser o caminho ideal. Esse parâmetro permite definir manualmente a região preferencial para o tráfego de mídia. |Nenhum|Códigos de país no formato ISO||
|Não|**O SBC dá suporte a PIDF/LO para chamadas de emergência**|PidfloSupported|Especifique se o SBC dá suporte ao Objeto de Localização de Formato de Dados de Informações de Presença (PIDF/LO) para chamadas de emergência.||||
|Não|**Ligar para o telefone ao tentar encontrar o usuário**|GenerateRingingWhileLocUser|De definir se um sinal de áudio é tocado para o chamador para indicar que o Teams está em processo de estabelecimento da chamada. Essa configuração só se aplica ao Roteamento Direto no modo de bypass sem mídia. Às vezes, as chamadas de entrada do PSTN para clientes do Teams podem levar mais tempo do que o esperado para serem estabelecidas. Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não toca e a chamada pode ser cancelada por alguns provedores de telecomunicações. Essa configuração ajuda a evitar silêncios inesperados que podem ocorrer nesses cenários.|Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não| - |MediaBypass|Essa configuração indica se o SBC dá suporte ao bypass de mídia e se você deseja usá-lo para esse SBC. |Nenhum|Verdadeiro<br/>Falso|Boolean|

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
