---
title: Configurar o Roteamento Direto
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
description: Saiba como configurar o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: c109dd919ad2842f38d135cba848ad2a7b34914d
ms.sourcegitcommit: fa20ea88e6a1c5d16ec3a364fc9d2b9a942cec9d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2020
ms.locfileid: "41022286"
---
# <a name="configure-direct-routing"></a>Configurar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

Se você ainda não tiver feito isso, leia [planejar o roteamento direto](direct-routing-plan.md) para pré-requisitos e revise outras etapas necessárias antes de configurar a rede do Microsoft Phone System. 

Este artigo descreve como configurar o roteamento direto do sistema de telefonia da Microsoft. Ele detalha como emparelhar um SBC (controlador de borda de sessão) com suporte para roteamento direto e como configurar os usuários do Microsoft Teams para usar o roteamento direto para se conectar à rede telefônica pública comutada (PSTN). Para concluir as etapas explicadas neste artigo, os administradores precisam estar familiarizados com cmdlets do PowerShell. Para obter mais informações sobre como usar o PowerShell, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Recomendamos que você confirme que o seu SBC já foi configurado como recomendado pelo fornecedor do SBC: 

- [Documentação de implantação do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação da implantação de comunicações da faixa de opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do anynode (File-Systems)](https://www.anynode.de/anynode-and-microsoft-teams/)

Você pode configurar seu sistema telefônico da Microsoft e permitir que os usuários usem o roteamento direto e, em seguida, configurar o Microsoft Teams como o cliente de chamada preferencial, completando os seguintes procedimentos: 

- [Emparelhar o SBC com um sistema telefônico da Microsoft e validar o emparelhamento](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Habilitar usuários para o serviço de roteamento direto](#enable-users-for-direct-routing-service)
- Garantir que o Microsoft Teams seja o cliente de chamadas preferencial para os usuários

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Emparelhar o SBC com o serviço de roteamento direto do sistema telefônico 

Veja a seguir as três etapas de alto nível para permitir que você conecte ou Emparelhe o SBC à interface de roteamento direto: 

- Conectar-se ao centro **de administração do Skype for Business online** usando o PowerShell 
- Emparelhar o SBC 
- Validar o emparelhamento 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Conectar-se ao Skype for Business online usando o PowerShell 

Você pode usar uma sessão do PowerShell conectada ao locatário para emparelhar o SBC com a interface de roteamento direto. Para abrir uma sessão do PowerShell, siga as etapas descritas em [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Depois de estabelecer uma sessão remota do PowerShell, valide se você pode ver os comandos para gerenciar o SBC. Para validar os comandos, digite ou copie/cole o seguinte na sessão do PowerShell e pressione ENTER: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Seu comando retornará as quatro funções mostradas aqui que permitirão que você gerencie o SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Emparelhar o SBC ao locatário 

Para emparelhar o SBC com o locatário, na sessão do PowerShell, digite o seguinte e pressione ENTER: 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. É altamente recomendável definir um limite máximo de chamadas no SBC, usando as informações que podem ser encontradas na documentação do SBC. O limite acionará uma notificação se o SBC estiver no nível de capacidade.
  > 2. Você só pode emparelhar o SBC se a parte do domínio de seu FQDN corresponder a um dos domínios registrados em seu locatário \*, exceto. onmicrosoft.com. Não \*há suporte para o uso de nomes de domínio. onmicrosoft.com para o nome FQDN do SBC. Por exemplo, se você tiver dois nomes de domínio:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Para o nome do SBC, você pode usar o nome sbc.contoso.com. Se você tentar emparelhar o SBC com um nome SBC. contoso. ABC, o sistema não permitirá que o domínio não seja pertencente a esse locatário.<br/>
  > Além do domínio registrado em seu locatário, é importante que haja um usuário com esse domínio e uma licença E3 ou E5 atribuída. Se não for, você receberá o seguinte erro:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Devolver
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Há opções adicionais que podem ser definidas durante o processo de emparelhamento. No exemplo anterior, no entanto, somente os parâmetros mínimos necessários são exibidos. 
 
A tabela a seguir lista os parâmetros adicionais que você pode usar em definir parâmetros ```New-CsOnlinePstnGateway```para.

|Necessário?|Nome|Descrição|Padrão|Valores possíveis|Tipo e restrições|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Sim|FQDN|O nome FQDN do SBC |Nenhum|Nome do NoneFQDN, limite de 63 caracteres|Cadeia de caracteres, lista de caracteres permitidos e não permitidos em [convenções de nomenclatura no Active Directory para computadores, domínios, sites e UOs](https://support.microsoft.com/help/909264)|
|Não|MediaBypass |O parâmetro indicado do SBC dá suporte à bypass de mídia e o administrador deseja usá-la.|Nenhum|Verdadeiro<br/>Falso|Boolean|
|Sim|SipSignallingPort |Porta de escuta usada para comunicação com serviços de roteamento direto usando o protocolo TLS (Transport Layer Security).|Nenhum|Qualquer porta|0 a 65535 |
|Não|FailoverTimeSeconds |Quando definido como 10 (valor padrão), as chamadas de saída que não são respondidas pelo gateway em 10 segundos são roteadas para o próximo tronco disponível; Se não houver troncos adicionais, a chamada será automaticamente cancelada. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente. O valor padrão é 10.|254|Número|Núm|
|Não|ForwardCallHistory |Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco. Se habilitado, o proxy PSTN do Office 365 envia dois cabeçalhos: histórico-informações e referenciado por. O valor padrão é **false** ($false). |Falso|Verdadeiro<br/>Falso|Boolean|
|Não|ForwardPAI|Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador. Se habilitado, o cabeçalho de identificação privacidade: também será enviado. O valor padrão é **false** ($false).|Falso|Verdadeiro<br/>Falso|Boolean|
|Não|SendSIPOptions |Define se um SBC irá ou não enviará as opções de SIP. Se desabilitado, o SBC será excluído do sistema de monitoramento e alerta. É altamente recomendável que você ative as opções do SIP. O valor padrão é **true**. |Verdadeiro|Verdadeiro<br/>Falso|Boolean|
|Não|MaxConcurrentSessions |Usado pelo sistema de alerta. Quando qualquer valor for definido, o sistema de alerta gerará um alerta para o administrador do locatário quando o número da sessão simultânea for 90% ou superior a este valor. Se o parâmetro não estiver definido, os alertas não serão gerados. No entanto, o sistema de monitoramento reportará o número da sessão simultânea a cada 24 horas. |Vazio|Vazio<br/>de 1 a 100.000 ||
|Não|MediaRelayRoutingLocationOverride |Permite a seleção de caminho para mídia manualmente. O roteamento direto atribui um datacenter para caminho de mídia com base no IP público do SBC. Sempre selecionamos mais próximo ao Datacenter do SBC. No entanto, em alguns casos, um IP público de, por exemplo, um intervalo dos EUA pode ser atribuído a um SBC localizado na Europa. Nesse caso, vamos usar o caminho de mídia ideal. Esse parâmetro permite definir manualmente a região preferida para tráfego de mídia. Recomendamos configurar esse parâmetro apenas se os logs de chamada indicar claramente que a atribuição automática do Media Center para o caminho de mídia não atribui o mais próximo possível ao Datacenter do SBC. |Nenhum|Códigos de país no formato ISO||
|Não|Habilitado|Usado para habilitar este SBC para chamadas de saída. Pode ser usado para remover temporariamente o SBC, enquanto ele está sendo atualizado ou durante a manutenção. |Falso|Verdadeiro<br/>Falso|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>Verificar o emparelhamento de SBC 

Verifique a conexão: 
- Verifique se o SBC está na lista de SBCs emparelhado. 
- Validar opções de SIP. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Validar se o SBC estiver na lista de SBCs emparelhado 

Depois de emparelhar o SBC, valide se o SBC está presente na lista de SBCs emparelhada executando o seguinte comando em uma sessão remota do PowerShell:`Get-CSOnlinePSTNGateway`

O gateway emparelhado deve aparecer na lista, conforme mostrado no exemplo abaixo, e verificar se o parâmetro **Enabled** exibe um valor de **true**. Dique

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Que retorna:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>Validar o fluxo de opções do SIP 

Para validar o emparelhamento usando as opções de SIP de saída, use a interface de gerenciamento do SBC e confirme se o SBC recebe as respostas de OK do 200 para suas mensagens de opções de saída.

Quando o roteamento direto vê as opções de entrada, ele começará a enviar mensagens de opções de SIP de saída para o FQDN do SBC configurado no campo de cabeçalho de contato na mensagem de opções de entrada. 

Para validar o emparelhamento usando as opções do SIP de entrada, use a interface de gerenciamento do SBC e veja se o SBC envia uma resposta às mensagens de opções que chegam do roteamento direto e que o código de resposta que ele envia é 200 OK.

## <a name="enable-users-for-direct-routing-service"></a>Habilitar usuários para o serviço de roteamento direto 

Quando estiver pronto para habilitar os usuários para o serviço de roteamento direto, siga estas etapas: 

1. Criar um usuário no Office 365 e atribuir uma licença do sistema telefônico. 
2. Certifique-se de que o usuário esteja hospedado no Skype for Business online. 
3. Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz. 
4. Configurar o roteamento de voz. A rota é validada automaticamente.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Criar um usuário no Office 365 e atribuir a licença 

Há duas opções para criar um novo usuário no Office 365. No entanto, recomendamos que sua organização selecione e use uma opção para evitar problemas de roteamento: 

- Crie o usuário no Active Directory local e sincronize o usuário com a nuvem. Confira [integrar seus diretórios locais com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Crie o usuário diretamente no portal do administrador do Office 365. Consulte [Adicionar usuários individualmente ou em massa ao Office 365-ajuda para administradores](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se sua implantação do Skype for Business Online for coexistente com o Skype for Business 2015 ou o Lync 2010/2013 local, a única opção compatível é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (opção 1). 

Licenças necessárias: 

- Office 365 Enterprise E3 (incluindo SfB Plan2, Exchange Plan2 e equipes) + sistema telefônico
- Office 365 Enterprise E5 (incluindo SfB Plan2, Exchange Plan2, equipes e sistema telefônico) 

Licenças opcionais: 

- Plano de chamada 
- Audioconferência 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Certifique-se de que o usuário esteja hospedado no Skype for Business Online 

O roteamento direto exige que o usuário seja hospedado no Skype for Business online. Você pode verificar isso examinando o parâmetro RegistrarPool. Ele precisa ter um valor no domínio infra.lync.com.

1. Conecte-se ao PowerShell remoto.
2. Execute o comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz 

Depois de criar o usuário e atribuir uma licença, a próxima etapa é configurar o número de telefone e o correio de voz. Isso pode ser feito em uma etapa. 

Para adicionar o número de telefone e habilitar o correio de voz:
 
1. Conectar-se a uma sessão remota do PowerShell. 
2. Digite o comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

Por exemplo, para adicionar um número de telefone para o usuário "Spencer baixo", você deve digitar o seguinte: 

```PowerShell
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

O número de telefone usado deve ser configurado como um número de telefone completo E. 164 com código de país. 

  > [!NOTE]
  > Se o número de telefone do usuário for gerenciado localmente, use o Shell de gerenciamento do Skype for Business local ou o painel de controle para configurar o número de telefone do usuário. 

### <a name="configure-voice-routing"></a>Configurar roteamento de voz 

O sistema telefônico da Microsoft tem um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC específico com base em: 

- Padrão de número chamado 
- Chamado de padrão de número + usuário específico que faz a chamada
 
A SBCs pode ser designada como ativa e de backup. Isso significa que, quando o SBC que é configurado como ativo para este padrão de número ou de número + usuário específico não está disponível, as chamadas são roteadas para um SBC de backup.
 
O encaminhamento de chamadas é composto pelos seguintes elementos: 
- Política de roteamento de voz – contêiner para usos de PSTN; pode ser atribuído a um usuário ou a vários usuários 
- Usos de PSTN – contêiner para roteiros de voz e usos de PSTN; pode ser compartilhado em diferentes políticas de roteamento de voz 
- Rotas de voz – o padrão de número e o conjunto de gateways PSTN online a serem usados para chamadas em que o número de chamada corresponde ao padrão 
- Gateway PSTN online-o ponteiro para um SBC também armazena a configuração aplicada quando a chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (PAI) ou codecs preferenciais; pode ser adicionado a roteiros de voz 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Criando uma política de roteamento de voz com um uso PSTN 

O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz no fluxo de chamadas.

**Fluxo de chamadas 1 (à esquerda):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada para o SBC sbc1.contoso.biz ou sbc2.contoso.biz. Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida. 

**Fluxo de chamadas 2 (à direita):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz. Se nenhum SBC estiver disponível, a rota com prioridade menor será tentada (sbc3.contoso.biz e sbc4.contoso.biz). Se nenhum dos SBCs estiver disponível, a chamada será interrompida. 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Nos dois exemplos, enquanto a rota de voz é atribuída às prioridades, o SBCs nos roteiros é tentado em ordem aleatória.

  > [!NOTE]
  > A menos que o usuário também tenha uma licença do plano de chamadas da Microsoft, as chamadas para qualquer número, exceto números que correspondam aos padrões + 1 425 XXX XX XX ou + 1 206 XXX XX XX no exemplo de configuração são descartados. Se o usuário tiver uma licença de plano de chamada, a chamada será roteada automaticamente de acordo com as políticas do plano de chamadas da Microsoft. 

O plano de chamadas da Microsoft aplica-se automaticamente como a última rota para todos os usuários com a licença do plano de chamadas da Microsoft e não requer configuração de roteamento de chamadas adicional.

No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números canadenses e números (chamadas que vão para o padrão de número chamado + 1 XXX XXX XX XX).

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada. Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, encaminhe pelo plano de chamadas da Microsoft.

Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.

  > [!NOTE]
  > O valor de prioridade para a rota "Other + 1" não importa nesse caso, pois há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX. Se um usuário fizer uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiverem indisponíveis, a chamada será interrompida.

A tabela a seguir resume a configuração usando três rotas de voz. Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN "EUA e Canadá".

|**Uso de PSTN**|**Rota de voz**|**Padrão de número**|**Prioridade**|**SBC**|**Descrição**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Somente EUA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|Somente EUA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|Somente EUA|"Outro + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|||||||

Todas as rotas são associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado apenas à política de roteamento de voz "apenas para os EUA". Neste exemplo, a política de roteamento de voz é atribuída ao usuário Spencer baixo.

#### <a name="examples-of-call-routes"></a>Exemplos de roteiros de chamada

No exemplo a seguir, demonstramos como configurar rotas, usos de PSTN e políticas de roteamento, e atribuímos a política ao usuário.

**Etapa 1:** Crie o uso de PSTN "EUA e Canadá".

Em uma sessão do PowerShell remoto do Skype for Business, digite:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Valide se o uso foi criado inserindo: 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
Que retorna uma lista de nomes que podem estar truncados:
```output
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
No exemplo abaixo, você pode ver o resultado do comando `(Get-CSOnlinePSTNUsage).usage` running the PowerShell para exibir nomes completos (não truncados).

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Etapa 2:** Em uma sessão do PowerShell no Skype for Business Online, crie três roteiros: 1, Redmond 2 e outros + 1, conforme detalhado na tabela anterior. 

Para criar a rota "Redmond 1", digite:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Que retorna:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Para criar a rota Redmond 2, digite:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Para criar a outra rota + 1, digite:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Certifique-se de que sua expressão regular no atributo NumberPattern é uma expressão válida. Você pode testá-lo usando este site:[https://www.regexpal.com](https://www.regexpal.com)

Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; Use-NumberPattern ". *"

Rotear todas as chamadas para o mesmo SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Valide se você configurou corretamente a rota executando o comando `Get-CSOnlineVoiceRoute` do PowerShell usando as opções, conforme mostrado:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Que deve retornar:
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

No exemplo, a rota "Other + 1" foi automaticamente atribuída à prioridade 4. 

**Etapa 3:** Crie uma política de roteamento de voz "apenas EUA" e adicione à política o uso de PSTN "EUA e Canadá".

Em uma sessão do PowerShell no Skype for Business Online, digite:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

O resultado é mostrado neste exemplo:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Etapa 4:** Conceder ao usuário Spencer uma política de roteamento de voz baixa usando o PowerShell.

Em uma sessão do PowerShell no Skype for Business Online, digite:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Valide a atribuição de política inserindo este comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Que retorna:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Criando uma política de roteamento de voz com vários usos de PSTN

A política de roteamento de voz criada anteriormente só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do plano de chamadas da Microsoft também seja atribuída ao usuário.

No exemplo a seguir, você pode criar a política de roteamento de voz "sem restrições". A política reutiliza o uso de PSTN "EUA e Canadá" criado no exemplo anterior, bem como o novo uso de PSTN "internacional". 

Isso roteia todas as outras chamadas para a SBCs sbc2.contoso.biz e sbc5.contoso.biz. Os exemplos mostrados atribuir apenas a política US para o usuário "Spencer baixo" e sem restrições ao usuário "John Woods".

Spencer baixo – chamadas permitidas somente para números canadenses e Estados Unidos. Ao ligar para o intervalo de números Redmond, o conjunto específico de SBC deve ser usado. Os números que não são dos EUA não serão roteados, a menos que a licença do plano de chamada seja atribuída ao usuário.

John Woods – chamadas permitidas para qualquer número. Ao ligar para o intervalo de números Redmond, o conjunto específico de SBC deve ser usado. Os números que não são dos EUA serão roteados via sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra a política de roteamento de voz atribuída ao usuário Spencer baixo](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada. Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, encaminhe pelo plano de chamadas da Microsoft.

Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

A tabela a seguir resume as designações de uso de política de roteamento "sem restrições" e rotas de voz. 

|**Uso de PSTN**|**Rota de voz**|**Padrão de número**|**Prioridade**|**SBC**|**Descrição**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Somente EUA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Roteiro ativo para números de chamada + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|Somente EUA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Rota de backup para números do chamado + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|Somente EUA|"Outro + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Rota para números de chamada + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Rota para qualquer padrão de número |


  > [!NOTE]
  > - A ordem dos usos de PSTN nas políticas de roteamento de voz é crítica. Os usos são aplicados em ordem e, se for encontrada uma coincidência no primeiro uso, outros usos nunca serão avaliados. O uso de PSTN "internacional" deve ser colocado após o uso de PSTN "somente EUA". Para alterar a ordem dos usos de PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "internacional" segundo a execução da ordem inversa:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - A prioridade para as rotas de voz "Other + 1" e "International" são atribuídas automaticamente. Não importa tão tempo que tenham prioridades menores do que "Redmond 1" e "Redmond 2".

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Exemplo de política de roteamento de voz para usuário John Woods

As etapas para criar o uso de PSTN "internacional", a rota de voz "internacional", a política de roteamento de voz "sem restrições" e, em seguida, atribuí-lo ao usuário "John Woods" são as seguintes.


**Etapa 1**: criar o uso de PSTN "internacional". 

Em uma sessão remota do PowerShell no Skype for Business Online, digite:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Etapa 2**: criar a nova rota de voz "internacional".

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Que retorna:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Etapa 3**: criar uma política de roteamento de voz "sem restrições". 

O uso de PSTN "Redmond 1" e "Redmond" é reutilizado nesta política de roteamento de voz para preservar a manipulação especial de chamadas para número "+ 1 425 XXX XX XX XX" e "+ 1 206 XXX XX XX" como chamadas locais ou locais.

   ```PowerShell
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

Tome nota da ordem dos usos de PSTN:

a. Se uma chamada feita ao número "+ 1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial for aplicada. Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como as rotas de backup.

b. Se o uso de PSTN "internacional" for anterior aos "EUA e Canadá", as chamadas para + 1 425 XXX XX XX são roteadas para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento. Digite o comando:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

Que retorna

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

**Etapa 4**: atribua a política de roteamento de voz ao usuário "John Woods" usando o comando a seguir.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

Em seguida, verifique a tarefa usando o comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Que retorna:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

O resultado é que a política de voz aplicada a chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para chamadas para os EUA, Canadá e internacional.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Atribuir o modo apenas Teams aos usuários para garantir chamadas no Microsoft Teams

O roteamento direto requer que os usuários estejam no modo somente Teams para garantir que as chamadas de entrada sejam feitas no cliente do teams. Para colocar usuários no modo somente Teams, atribua a eles a instância "UpgradeToTeams" de TeamsUpgradePolicy. Se a sua organização usa o Skype for Business Server ou o Skype for Business Online, consulte o artigo a seguir para interoperabilidade de informações entre o Skype e o Teams: [orientação de migração e interoperabilidade para organizações que usam o Skype for Business em equipe](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurar o envio de chamadas diretamente para o correio de voz

O roteamento direto permite encerrar a chamada para um usuário e enviá-la diretamente para a caixa postal dos usuários. Se você quiser enviar a chamada diretamente para o correio de voz, anexe o aplicativo opaco = App: correio de voz ao cabeçalho URI da solicitação. Por exemplo, "SIP: user@yourdomain. com; opaco = App: correio de voz".
Nesse caso, o usuário do Teams não receberá a notificação de chamada, a chamada será conectada diretamente ao correio de voz do usuário.

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>Traduza números de chamadas e de chamadas para chamadas de entrada e saída para um formato alternativo

Às vezes, os administradores de locatários podem querer alterar o chamador ou o número de chamada para chamadas de entrada e/ou de entrada com base nos padrões que criaram para garantir a interoperabilidade com SBCs. Você pode definir uma política de regras de tradução de números para traduzir chamadas para chamadas ou números de chamadas para um formato alternativo. Você pode usar a política para traduzir números para o seguinte:

- Chamadas recebidas: chamadas de um ponto de extremidade PSTN (chamador) para um cliente do Teams (chamado).
- Chamadas de saída: chamadas de um cliente do Teams (chamador) para um ponto de extremidade PSTN (chamado).

A política é aplicada no nível de SBC. Você pode atribuir várias regras de tradução a um SBC, que são aplicadas na ordem em que aparecem quando você as lista no PowerShell. Você também pode alterar a ordem das regras na política.

Para criar, modificar, exibir e excluir regras de manipulação de números, use os cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Para atribuir, configurar e listar as regras de manipulação de números no SBCS, use os cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) juntos ```InboundPSTNNumberTranslationRules```com ```OutboundTeamsNumberTranslationRules```os ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRules```parâmetros ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList```,,, ```OutboundPSTNNumberTranslationRulesList``` , e.

### <a name="examples"></a>Exemplos

#### <a name="example-sbc-configuration"></a>Exemplo de configuração do SBC

Para os cenários de exemplo, executamos ```New-CsOnlinePSTNGateway``` o cmdlet para criar a configuração do SBC a seguir.

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

As regras de tradução atribuídas ao SBC são resumidas na tabela a seguir.

|Nome  |Padrão |Conversão  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

Nestes cenários de exemplo, temos dois usuários, Alice e Bob. Alice é um usuário do Teams e seu número é + 1 206 555 0100. Bob é um usuário PSTN e seu número é + 1 425 555 0100.

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemplo 1: chamada de entrada para um número de 10 dígitos

Bob chama Alice usando um número que não seja E. 164 de dez dígitos. Bob disca 2065550100 para falar com Alice.
O SBC usa 2065550100 no RequestURI e em cabeçalhos e 4255550100 no cabeçalho de.

|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:2065550100@sbc.contoso.com|CONVIDAR sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|Para    |PARA: \<SIP:2065550100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemplo 2: chamada de entrada para um número de quatro dígitos

Bob chama Alice usando um número de quatro dígitos. Bob disca 0100 para falar com Alice.
O SBC usa 0100 no RequestURI e em cabeçalhos e 4255550100 no cabeçalho de.

|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:0100@sbc.contoso.com          |CONVIDAR sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|De   |DE: \<SIP:4255550100@sbc.contoso.com>|DE: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemplo 3: chamada de saída usando um número não-E de dez dígitos. 164

Alice chama Bob usando um número de dez dígitos. Ana discagem 425 555 0100 para falar com o Bob.
O SBC está configurado para usar números de dez dígitos que não são E. 164 para equipes e usuários de PSTN.

Nesse cenário, um plano de discagem converte o número antes de enviá-lo para a interface de roteamento direto. Quando Ana entra em 425 555 0100 no cliente do Teams, o número é convertido em + 14255550100 pelo plano de discagem do país. Os números resultantes são uma normalização cumulativa das regras do plano de discagem e das regras de tradução do teams. As regras de tradução do teams removem o "+ 1" que foi adicionado pelo plano de discagem.

|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:+14255550100@sbc.contoso.com          |CONVIDAR sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|Para    |PARA: \<SIP:+14255550100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemplo 4: chamada de saída usando um número de quatro dígitos que não é E. 164

Alice chama Bob usando um número de quatro dígitos. Alice usa 0100 para se comunicar com Bob em chamadas ou usando um contato.
O SBC está configurado para usar números de quatro dígitos que não são E. 164 para usuários do Teams e números de dez dígitos para usuários de PSTN. O plano de discagem não é aplicado nesse cenário.

|Cabeçalho  |Original |Cabeçalho traduzido |Parâmetro e regra aplicados  |
|---------|---------|---------|---------|
|RequestURI  |CONVIDAR sip:0100@sbc.contoso.com           |CONVIDAR sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|Para    |PARA: \<SIP:0100@sbc.contoso.com>|PARA: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |DE: \<SIP:+12065550100@sbc.contoso.com>|DE: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)
