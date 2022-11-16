---
title: Conectar seu Controlador de Borda de Sessão (SBC) ao Roteamento Direto
ms.reviewer: fillipse
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
description: Saiba como configurar e conectar seu SBC ao Roteamento Direto do Sistema de Telefonia do Teams.
ms.openlocfilehash: b34762b9df84839b17be6693b9ed782b5029525a
ms.sourcegitcommit: 2f9a83a1bae8cbee5a0d65464bd47f6735b2d206
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "69025163"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Conectar seu Controlador de Borda de Sessão (SBC) ao Roteamento Direto

Este artigo descreve como configurar um SBC (Controlador de Borda de Sessão) e conectá-lo ao Roteamento Direto.  Esta é a etapa 1 das seguintes etapas para configurar o Roteamento Direto:

- **Etapa 1. Conecte seu SBC ao Sistema Telefônico e valide a conexão** (Este artigo)
- Etapa 2. [Habilitar usuários para Roteamento Direto](direct-routing-enable-users.md)
- Etapa 3. [Configurar o roteamento de chamadas](direct-routing-voice-routing.md)
- Etapa 4. [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md)

Para obter informações sobre todas as etapas necessárias para configurar o [Roteamento Direto, consulte Configurar o Roteamento Direto](direct-routing-configure.md).

Você pode usar o [centro de administração do Microsoft Teams](#using-the-microsoft-teams-admin-center) ou [o PowerShell](#using-powershell) para configurar e conectar um SBC ao Roteamento Direto.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, acesse **Roteamento Direto** de **Voz** >  e clique na guia **SBCs**.

2. Clique em **Adicionar**.

3. Insira um FQDN para o SBC. <br><br>Verifique se a parte do nome de domínio do FQDN corresponde a um domínio registrado em seu locatário e tenha em mente que o `*.onmicrosoft.com` nome de domínio não tem suporte para o nome de domínio SBC FQDN. Por exemplo, se você tiver dois nomes `contoso.com` de domínio e `contoso.onmicrosoft.com`, use `sbc.contoso.com` como o nome SBC. Se estiver usando um subdomínio, verifique se esse subdomínio também está registrado em seu locatário. Por exemplo, se você quiser usar `sbc.service.contoso.com`, precisará `service.contoso.com` ser registrado.

4. Configure as seguintes configurações para o SBC, com base nas necessidades da sua organização. Para obter detalhes sobre cada uma dessas configurações, confira [Configurações do SBC](#sbc-settings).

    ![Captura de tela da página adicionar SBC no centro de administração do Microsoft Teams.](media/direct-routing-add-sbc.png)

5. Quando terminar, clique em **Salvar**.

## <a name="using-powershell"></a>Usando o Windows PowerShell

Para conectar seu SBC ao Roteamento Direto, você precisará:

1. [Conecte-se ao Skype for Business Online usando o PowerShell](#connect-to-skype-for-business-online-by-using-powershell).

2. [Conecte o SBC ao locatário](#connect-the-sbc-to-the-tenant).

3. [Verifique a conexão SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectar-se ao Skype for Business Online usando o PowerShell

Para emparelhar o SBC com a interface de Roteamento Direto, use uma sessão do PowerShell conectada ao locatário. Para abrir uma sessão do PowerShell, siga as etapas descritas em [Configurar seu computador para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Depois de estabelecer uma sessão remota do PowerShell, verifique se você pode ver os comandos para gerenciar o SBC. Para verificar os comandos, digite ou copie e cole o seguinte comando na sessão do PowerShell e pressione Enter: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

O comando retorna as quatro funções mostradas aqui que permitirão gerenciar o SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Conectar o SBC ao locatário

Para conectar o SBC ao locatário, use o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . Em uma sessão do PowerShell, digite o seguinte e pressione Enter:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Recomendamos que você defina um limite máximo de chamada no SBC usando informações que possam ser encontradas na documentação do SBC. O limite disparará uma notificação se o SBC estiver no nível de capacidade.
  > 2. Você só poderá conectar o SBC se a parte de domínio do FQDN corresponder a um dos domínios registrados em seu locatário, exceto \*.onmicrosoft.com. Não há suporte para o uso \*de nomes de domínio .onmicrosoft.com para o nome SBC FQDN. Por exemplo, se você tiver dois nomes de domínio, **contoso.com** e **contoso.onmicrosoft.com**, poderá usar sbc.contoso.com para o nome SBC. Se você tentar conectar o SBC com um nome como sbc.contoso.abc, o sistema não permitirá, pois o domínio não pertence a esse locatário.<br/>
  > Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída. Caso contrário, você receberá o seguinte erro:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. Não há suporte para vários IPs mapeados com o mesmo FQDN no lado do SBC.
  > 4. Para fornecer a melhor criptografia da classe aos nossos clientes, a Microsoft forçará o uso do TLS1.2 para a interface SIP de Roteamento Direto.
  > Para evitar qualquer impacto no serviço, verifique se os SBCs estão configurados para dar suporte ao TLS1.2 e podem se conectar usando um dos seguintes pacotes de criptografia: TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 ou seja. ECDHE-RSA-AES256-GCM-SHA384 TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 ou seja, ECDHE-RSA-AES128-GCM-SHA256 TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 ou seja, ECDHE-RSA-AES256-SHA384 TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 ou seja, ECDHE-RSA-AES128-SHA256
  > 5. Os pings DE OPÇÕES SIP NÃO DEVEM exceder uma frequência de uma transação a cada 60 segundos e NÃO devem ser mais ou menos frequentes do que uma transação a cada 180 segundos para cada tronco configurado para cada ponto de extremidade.

Veja um exemplo:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

O que retorna:

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
> Este exemplo mostra apenas os parâmetros mínimos necessários. Há parâmetros adicionais que você pode definir com o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) durante o processo de conexão. Para saber mais, confira [Configurações do SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Verificar a conexão SBC

Para verificar a conexão:

- [Verifique se o SBC está na lista de SBCs emparelhados](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Validar opções SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Verifique se o SBC está na lista de SBCs emparelhados

Depois de conectar o SBC, use o cmdlet [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) para verificar se o SBC está presente na lista de SBCs emparelhados. Digite o seguinte em uma sessão remota do PowerShell e pressione Enter:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

O gateway emparelhado deve aparecer na lista, conforme mostrado no exemplo abaixo, e o parâmetro **Habilitado** deve exibir um valor de **True**.

O que retorna:

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

Quando o Roteamento Direto vir OPções de entrada, ele começará a enviar mensagens de saída do SIP Options para o SBC FQDN configurado no campo Cabeçalho contato na mensagem OPções de entrada. 

Para validar o emparelhamento usando opções SIP de entrada, use a interface de gerenciamento SBC e consulte se o SBC envia uma resposta às mensagens OPTIONS provenientes do Roteamento Direto e que o código de resposta que ele envia é 200 OK.

## <a name="sbc-settings"></a>Configurações do SBC

Esta tabela lista as opções que você pode definir para o SBC no centro de administração do Microsoft Teams e usando o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) .

|Necessário?|Configuração do centro de administração do Teams|Parâmetro do PowerShell|Descrição|Padrão|Valores possíveis|Tipo e restrições|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sim|**Adicionar um FQDN para o SBC**|FQDN |Nenhum|Nome FQDN, limite 63 caracteres|Cadeia de caracteres, confira a lista de caracteres permitidos e não [permitidos em convenções de nomenclatura no Active Directory para computadores, domínios, sites e OUs](https://support.microsoft.com/help/909264)|
|Não|**Habilitado**|Habilitado|Use para ativar o SBC para chamadas de saída. Você pode usá-lo para remover temporariamente o SBC do serviço enquanto ele estiver sendo atualizado ou durante a manutenção. |Falso|Verdadeiro<br/>Falso|Boolean|
|Sim|**Porta de sinalização SIP**|SipSignalingPort |Essa é a porta de escuta usada para se comunicar com o Roteamento Direto usando o protocolo TLS (Camada de Transporte).|Nenhum|Qualquer porta|0 a 65535 |
|Não|**Enviar opções SIP**|SendSIPOptions |Define se o SBC enviará mensagens de opções SIP. É altamente recomendável ativar essa configuração. Quando essa configuração está desativada, o SBC é excluído do sistema de Monitoramento e Alerta.|Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não|**Histórico de chamadas de encaminhamento**|ForwardCallHistory |Indica se as informações de histórico de chamadas são encaminhadas pelo tronco. Quando você ativa isso, o proxy do Microsoft 365 envia um cabeçalho Histórico e Referenciado por. |Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Cabeçalho P-Asserted-identity (PAI)**|ForwardPAI|Indica se o cabeçalho pai é encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador. Se essa configuração estiver ativada, o cabeçalho Privacy:ID também será enviado.|Falso|Verdadeiro<br/>Falso|Boolean|
|Não|**Capacidade de chamada simultânea**|Maxconcurrentsessions |Quando você definir um valor, o sistema de alerta notificará você quando o número de sessões simultâneas for 90% ou superior a esse valor. Se você não definir um valor, os alertas não serão gerados. No entanto, o sistema de monitoramento relatará o número de sessões simultâneas a cada 24 horas. |Null|Null<br/>1 a 100.000 ||
|Não|**Códigos de resposta de failover**|FailoverResponseCodes<br>|Se o Roteamento Direto receber qualquer código de erro SIP 4xx ou 6xx em resposta a um Convite de saída, a chamada será considerada concluída por padrão. Saída significa uma chamada de um cliente do Teams para o PSTN com fluxo de tráfego: cliente do Teams -> Roteamento Direto -> rede de telefonia SBC ->). Quando você especifica um código de resposta de failover, isso força o Roteamento Direto a experimentar outro SBC (se houver outro SBC na política de roteamento de voz do usuário) quando ele recebe os códigos especificados se o SBC não puder fazer uma chamada devido à rede ou outros problemas. Para saber mais, confira [Failover de códigos SIP específicos recebidos do SBC (Controlador de Borda de Sessão)](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Int|
|Não|**Tempos de failover (segundos)**|FailoverTimeSeconds |Quando você define um valor, as chamadas de saída que não são atendidas pelo gateway no tempo definido são roteadas para o próximo tronco disponível. Se não houver troncos adicionais, a chamada será descartada automaticamente. O valor padrão é de 10 segundos. Em uma organização com redes lentas e respostas de gateway, isso poderia potencialmente resultar em chamadas sendo descartadas desnecessariamente.|10|Número|Int|
|Não|**País ou região preferencial para tráfego de mídia**|MediaRelayRoutingLocationOverride | Não aplicável ao Roteamento Direto. Esse parâmetro é reservado para uso com operadoras gerenciadas em Planos de Chamada |Nenhum|||
|Não|**O SBC dá suporte a PIDF/LO para chamadas de emergência**|PidfloSupported|Especifique se o SBC dá suporte a PIDF/LO (Objeto local de formato de dados de informações de presença) para chamadas de emergência.||||
|Não| - |MediaBypass|Essa configuração indica se o SBC dá suporte a bypass de mídia e se você deseja usá-la para este SBC. |Nenhum|Verdadeiro<br/>Falso|Boolean|

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
