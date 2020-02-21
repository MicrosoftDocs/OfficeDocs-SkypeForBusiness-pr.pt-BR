---
title: Configurar o roteamento de voz para roteamento direto
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
description: Saiba como configurar o roteamento de voz com o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157923"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurar o roteamento de voz para roteamento direto

Este artigo descreve como configurar o roteamento de voz para o roteamento direto do sistema telefônico.  Esta é a etapa 3 das seguintes etapas para configurar o roteamento direto:

- Etapa 1. [Conectar o SBC com o sistema Microsoft Phone e validar a conexão](direct-routing-connect-the-sbc.md) 
- Etapa 2. [Habilite os usuários para roteamento direto, voz e correio de voz](direct-routing-enable-users.md)    
- **Etapa 3. Configurar roteamento de voz** (este artigo)
- Etapa 4. [Converter números em um formato alternativo](direct-routing-translate-numbers.md) 

Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Visão geral do roteamento de voz

O sistema telefônico da Microsoft tem um mecanismo de roteamento que permite que uma chamada seja enviada para um controlador de borda de sessão (SBC) específico com base em: 

- O padrão de número chamado 
- O padrão de número chamado mais o usuário específico que faz a chamada
 
A SBCs pode ser designada como ativa e de backup. Quando o SBC que está configurado como ativo não está disponível para uma rota de chamada específica, a chamada será roteada para um SBC de backup.
 
O roteamento de voz é composto pelos seguintes elementos: 

- **Política de roteamento de voz** – um contêiner para usos de PSTN que podem ser atribuídos a um usuário ou a vários usuários. 

- **Usos de PSTN** – um contêiner para rotas de voz e usos de PSTN, que podem ser compartilhados em diferentes políticas de roteamento de voz. 

- **Rotas de voz** – um padrão de número e um conjunto de gateways PSTN online a serem usados para chamadas onde o número de chamada corresponde ao padrão.

- **Gateway PSTN online** -um ponteiro para um SBC que também armazena a configuração aplicada quando uma chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (pai) ou codecs preferenciais; pode ser adicionado a roteiros de voz.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Exemplo 1: roteamento de voz com um uso PSTN

O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz em um fluxo de chamadas.

**Fluxo de chamadas 1 (à esquerda):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada para o SBC sbc1.contoso.biz ou sbc2.contoso.biz. Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida. 

**Fluxo de chamadas 2 (à direita):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz. Se nenhum SBC estiver disponível, a rota com prioridade menor será tentada (sbc3.contoso.biz e sbc4.contoso.biz). Se nenhum dos SBCs estiver disponível, a chamada será interrompida. 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Nos dois exemplos, enquanto a rota de voz é atribuída às prioridades, o SBCs nos roteiros é tentado em ordem aleatória.

  > [!NOTE]
  > A menos que o usuário também tenha uma licença do plano de chamadas da Microsoft, as chamadas para qualquer número, exceto números que correspondam aos padrões + 1 425 XXX XX XX ou + 1 206 XXX XX XX no exemplo de configuração são descartados. Se o usuário tiver uma licença de plano de chamada, a chamada será roteada automaticamente de acordo com as políticas do plano de chamadas da Microsoft. O plano de chamadas da Microsoft aplica-se automaticamente como a última rota para todos os usuários com a licença do plano de chamadas da Microsoft e não requer configuração de roteamento de chamadas adicional.

No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números canadenses e EUA (chamadas que vão para o padrão de número chamado + 1 XXX XXX XX XX).

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Para todas as outras chamadas:

- Se um usuário tiver licenças (sistema telefônico da Microsoft e Microsoft Calling plano), a rota automática será usada. 
- Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada pelo plano de chamadas da Microsoft.
- Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque nenhuma regra de correspondência estará disponível.

  > [!NOTE]
  > O valor de prioridade para a rota "Other + 1" não importa nesse caso porque há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX. Se um usuário fizer uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiverem indisponíveis, a chamada será interrompida.

A tabela a seguir resume a configuração usando três rotas de voz. Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN "EUA e Canadá".  Todas as rotas são associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado apenas à política de roteamento de voz "apenas para os EUA". 

|**Uso de PSTN**|**Rota de voz**|**Padrão de número**|**Prioridade**|**SBC**|**Descrição**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Somente EUA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|Somente EUA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|Somente EUA|"Outro + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|||||||


### <a name="example-1-configuration-steps"></a>Exemplo 1: etapas de configuração

O exemplo a seguir mostra como:

- Criar um único uso de PSTN 
- Configurar três rotas de voz
- Criar uma política de roteamento de voz
- Atribuir a política ao usuário Spencer-baixo

**Etapa 1:** Criar o uso de PSTN "EUA e Canadá"

Em uma sessão do PowerShell remoto do Skype for Business, digite:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Valide se o uso foi criado inserindo: 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
Que retorna uma lista de nomes que podem estar truncados:
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
O exemplo a seguir mostra o resultado da execução do comando `(Get-CSOnlinePSTNUsage).usage` do PowerShell para exibir nomes completos (não truncados):

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

**Etapa 2:** Em uma sessão do PowerShell no Skype for Business Online, crie três rotas: Redmond 1, Redmond 2 e outros + 1, conforme mostrado na tabela anterior.

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

**Etapa 4:** Ao usar o PowerShell, conceda a política de roteamento de voz ao usuário Spencer para baixo:

Em uma sessão do PowerShell no Skype for Business Online, digite:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Valide a atribuição de política inserindo este comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

O comando retorna o seguinte:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Exemplo 2: roteamento de voz com vários usos de PSTN

A política de roteamento de voz criada no exemplo 1 só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do plano de chamadas da Microsoft também seja atribuída ao usuário.

No exemplo a seguir, você pode criar a política de roteamento de voz "sem restrições". A política reutiliza o uso de PSTN "EUA e Canadá" criado no exemplo 1, bem como o novo uso de PSTN "internacional".  Esta política roteia todas as outras chamadas para o SBCs sbc2.contoso.biz e sbc5.contoso.biz. 

Os exemplos mostrados atribuem a política apenas EUA para o usuário Spencer baixo e a política sem restrições ao usuário John Woods para que o roteamento ocorra da seguinte maneira:

- Spencer baixo – política apenas para os EUA.  As chamadas são permitidas apenas para números canadenses e Estados Unidos. Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado. Os números que não são dos EUA não serão roteados, a menos que a licença do plano de chamada seja atribuída ao usuário.

- John Woods – política internacional.  As chamadas são permitidas para qualquer número. Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado. Os números que não são dos EUA serão encaminhados usando sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra a política de roteamento de voz atribuída ao usuário Spencer baixo](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada. Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada usando o plano de chamada da Microsoft.  Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.

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


### <a name="example-2-configuration-steps"></a>Exemplo 2: etapas de configuração

O exemplo a seguir mostra como:

- Criar um novo uso de PSTN chamado International
- Criar uma nova rota de voz chamada internacional
- Criar uma política de roteamento de voz chamada sem restrições
- Atribuir a política ao usuário John Woods


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

Que retorna:

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



## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
