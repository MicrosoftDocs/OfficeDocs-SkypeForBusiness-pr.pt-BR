---
title: Configurar roteamento de chamadas para Roteamento Direto
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
description: Saiba como configurar o roteamento de chamadas com o Roteamento Direto da Microsoft.
ms.openlocfilehash: cb8f33d8e5e2ea3e3e14ac47b57d9b5920f2bb2a
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60635040"
---
# <a name="configure-call-routing-for-direct-routing"></a>Configurar roteamento de chamadas para Roteamento Direto

Este artigo descreve como configurar o roteamento de chamadas para Roteamento Direto. Esta é a etapa 3 das seguintes etapas para configurar o Roteamento Direto:

- Etapa 1. [Conexão SBC com Telefone Microsoft System e validar a conexão](direct-routing-connect-the-sbc.md) 
- Etapa 2. [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)
- **Etapa 3. Configurar roteamento de** chamadas (Este artigo)
- Etapa 4. [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 

Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).

## <a name="call-routing-overview"></a>Visão geral do roteamento de chamadas

Telefone Microsoft O sistema tem um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC (Controlador de Borda de Sessão) específico com base em: 

- O padrão de número chamado 
- O padrão de número chamado mais o usuário específico que faz a chamada
 
Os SBCs podem ser designados como ativos e de backup. Quando o SBC configurado como ativo não estiver disponível para uma rota de chamada específica, a chamada será roteada para um SBC de backup.
 
O roteamento de chamadas é feito dos seguintes elementos: 

- **Política de roteamento de** chamadas – Também chamada de política de roteamento de voz. Um contêiner para usos PSTN, que pode ser atribuído a um usuário ou a vários usuários. 

- **Usos de PSTN** – um contêiner para rotas de voz e usos PSTN, que podem ser compartilhados em diferentes políticas de roteamento de voz. 

- **Rotas de** voz – um padrão de número e um conjunto de gateways PSTN online a ser usado para chamadas em que o número de chamada corresponde ao padrão.

- **Gateway PSTN** Online - Um ponteiro para um SBC que também armazena a configuração aplicada quando uma chamada é feita por meio do SBC, como encaminhar P-Asserted-Identity (PAI) ou Codecs Preferenciais; pode ser adicionado a rotas de voz.

## <a name="voice-routing-policy-considerations"></a>Considerações sobre a política de roteamento de voz

Se um usuário tiver uma licença de Plano de Chamadas, as chamadas de saída desse usuário serão roteados automaticamente pela infraestrutura PSTN do Plano de Chamadas da Microsoft. Se você configurar e atribuir uma política de roteamento de voz online a um usuário do Plano de Chamadas, as chamadas de saída desse usuário serão verificadas para determinar se o número discado corresponde a um padrão de número definido na política de roteamento de voz online. Se houver uma combinação, a chamada será roteada pelo tronco de Roteamento Direto. Se não houver nenhuma combinação, a chamada será roteada pela infraestrutura PSTN do Plano de Chamada.

> [!CAUTION]
> Se você configurar e aplicar a política de roteamento de voz online global (padrão em toda a organização), todos os usuários habilitados para voz em sua organização herdarão essa política, o que pode resultar em chamadas PSTN de usuários do Plano de Chamadas sendo roteados inadvertidamente para um tronco de Roteamento Direto. Se você não quiser que todos os usuários usem a política global de roteamento de voz online, configure uma política de roteamento de voz online personalizada e atribua-a a usuários individuais habilitados para voz.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Exemplo 1: roteamento de voz com um uso PSTN

O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz em um fluxo de chamadas.

**Chame Flow 1 (à esquerda):** Se um usuário fizer uma chamada para +1 425 XXX XX XX ou +1 206 XXX XX, a chamada será roteada para SBC sbc1.contoso.biz ou sbc2.contoso.biz. Se nem sbc1.contoso.biz nem sbc2.contoso.biz estão disponíveis, a chamada será retirada. 

**Chame Flow 2 (à direita):** Se um usuário fizer uma chamada para +1 425 XXX XX XX ou +1 206 XXX XX, a chamada será roteada pela primeira vez para SBC sbc1.contoso.biz ou sbc2.contoso.biz. Se nenhum SBC estiver disponível, a rota com prioridade mais baixa será tentada (sbc3.contoso.biz e sbc4.contoso.biz). Se nenhum dos SBCs estiver disponível, a chamada será retirada. 

![Mostra exemplos de política de roteamento de voz.](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Em ambos os exemplos, enquanto a rota de voz é atribuída prioridades, os SBCs nas rotas são tentados em ordem aleatória.

  > [!NOTE]
  > A menos que o usuário também tenha uma licença do Plano de Chamadas da Microsoft, as chamadas para qualquer número, exceto números que coincidem com os padrões +1 425 XXX XX ou +1 206 XXX XX na configuração de exemplo, serão descartados. Se o usuário tiver uma licença de Plano de Chamada, a chamada será roteada automaticamente de acordo com as políticas do Plano de Chamada da Microsoft. O Plano de Chamadas da Microsoft se aplica automaticamente como a última rota para todos os usuários com a licença do Plano de Chamadas da Microsoft e não exige configuração adicional de roteamento de chamadas.

No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números dos EUA e do Canadá (chamadas que vão para o padrão de número chamado +1 XXX XXX XX XX).

![Mostra a política de roteamento de voz com uma terceira rota.](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Para todas as outras chamadas, se um usuário tiver ambas as licenças (Telefone Microsoft System e Plano de Chamadas da Microsoft), a rota automática será usada. Se nada corresponde aos padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada por meio do Plano de Chamadas da Microsoft. Se o usuário tiver apenas Telefone Microsoft System, a chamada será descartada porque não há regras correspondentes disponíveis.

  > [!NOTE]
  > O valor priority para a rota "Other +1" não importa nesse caso porque há apenas uma rota que corresponde ao padrão +1 XXX XXX XX. Se um usuário fizer uma chamada para +1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiver indisponível, a chamada será retirada.

A tabela a seguir resume a configuração usando três rotas de voz. Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN, "EUA e Canadá".  Todas as rotas estão associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado à política de roteamento de voz "Somente EUA".

|**Uso de PSTN**|**Rota de voz**|**Padrão de número**|**Prioridade**|**SBC**|**Descrição**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|EUA e Canadá|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Rota ativa para números chamados +1 425 XXX XX XX ou +1 206 XXX XX|
|EUA e Canadá|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Rota de backup para números chamados +1 425 XXX XX XX ou +1 206 XXX XX|
|EUA e Canadá|"Outros +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Rote para números chamados +1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Exemplo 1: Etapas de configuração

O exemplo a seguir mostra como:

1. Crie um único uso PSTN.
2. Configure três rotas de voz.
3. Crie uma política de roteamento de voz.
4. Atribua a política a um usuário chamado Spencer Low.

Você pode usar o Microsoft Teams [de administração ou](#admincenterexample1) o [PowerShell](#powershellexample1) para executar essas etapas.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Etapa 1: Criar o uso de PSTN "EUA e Canadá"

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Roteamento Direto de Voz e, no canto superior direito, selecione Gerenciar registros de uso  >   **PSTN.**
2. Clique **em Adicionar**, digite EUA e **Canadá** e clique em **Aplicar**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Etapa 2: Criar três rotas de voz (Redmond 1, Redmond 2 e Other +1)

As etapas a seguir descrevem como criar uma rota de voz. Use estas etapas para criar as três rotas de voz chamadas Redmond 1, Redmond 2 e Other +1 para este exemplo usando as configurações descritas na tabela anterior.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Roteamento** Direto de Voz e selecione a  >  guia **Rotas de** voz.
2. Clique **em Adicionar** e insira um nome e uma descrição para a rota de voz.
3. De definir a prioridade e especificar o padrão de número discado.
4. Para registrar um SBC com a rota de voz, em **SBCs inscritos (opcional),** clique em Adicionar **SBCs,** selecione os SBCs que você deseja registrar e clique em **Aplicar**.
5. Para adicionar registros de uso PSTN, em Registros de uso **PSTN (opcional),** clique em Adicionar uso **PSTN,** selecione os registros PSTN que você deseja adicionar e clique em **Aplicar**.
6. Clique em **Salvar**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Etapa 3: criar uma política de roteamento de voz chamada "Somente EUA" e adicionar o uso de PSTN "EUA e Canadá" à política

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de roteamento **do Voice** Voice e clique  >  em **Adicionar**.
2. Digite **US Only** como o nome e adicione uma descrição.
3. Em **Registros de uso PSTN,** clique em Adicionar uso de **PSTN,** selecione o registro de uso PSTN "EUA e Canadá" e clique em **Aplicar**.
4. Clique em **Salvar**.

Para saber mais, confira [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Etapa 4: Atribuir a política de roteamento de voz a um usuário chamado Spencer Low

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Clique **em Políticas** e, ao lado de Políticas **Atribuídas,** clique em **Editar**.
3. Em **Política de roteamento de** voz, selecione a política "Somente EUA" e clique em **Salvar**.

Para saber mais, confira [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Etapa 1: Criar o uso de PSTN "EUA e Canadá"

Em uma sessão remota do PowerShell no Skype for Business Online, digite:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Verifique se o uso foi criado inserindo:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Que retorna uma lista de nomes que podem ser truncados:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

O exemplo a seguir mostra o resultado da execução do `(Get-CSOnlinePSTNUsage).usage` comando do PowerShell para exibir nomes completos (não truncados):

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Etapa 2: Criar três rotas de voz (Redmond 1, Redmond 2 e Other +1)

Para criar a rota "Redmond 1", em uma sessão do PowerShell no Skype for Business Online, digite:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Que retorna:

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

Para criar a rota Redmond 2, digite:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Para criar a outra rota +1, digite:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Certifique-se de que sua expressão regular no atributo NumberPattern seja uma expressão válida. Você pode testá-lo usando este site: [https://www.regexpal.com](https://www.regexpal.com)

Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; use -NumberPattern ".*"

Rotee todas as chamadas para o mesmo SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Verifique se você configurou corretamente a rota executando o `Get-CSOnlineVoiceRoute` comando do PowerShell usando opções conforme mostrado:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Que deve retornar:

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

No exemplo, a rota "Outros +1" foi atribuída automaticamente à prioridade 4. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Etapa 3: criar uma política de roteamento de voz chamada "Somente EUA" e adicionar o uso de PSTN "EUA e Canadá" à política

Em uma sessão do PowerShell no Skype for Business Online, digite:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

O resultado é mostrado neste exemplo:

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Etapa 4: Atribuir a política de roteamento de voz a um usuário chamado Spencer Low

Em uma sessão do PowerShell no Skype for Business Online, digite:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Valide a atribuição de política inserindo este comando:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

O comando retorna o seguinte:

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Exemplo 2: roteamento de voz com vários usos PSTN

A política de roteamento de voz criada no Exemplo 1 só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do Plano de Chamadas da Microsoft também seja atribuída ao usuário.

No exemplo a seguir, você pode criar a política de roteamento de voz "Sem Restrições". A política reutiliza o uso de PSTN "EUA e Canadá" criado no Exemplo 1, bem como o novo uso de PSTN "Internacional". Essa política encaminha todas as outras chamadas para os SBCs sbc2.contoso.biz e sbc5.contoso.biz.

Os exemplos mostrados atribuem a política Somente EUA ao usuário Spencer Low e a política Sem Restrições ao usuário John Woods para que o roteamento ocorra da seguinte maneira:

- Spencer Low – Política somente eua.  As chamadas só são permitidas para números dos EUA e do Canadá. Ao chamar para o intervalo de números redmond, o conjunto específico de SBCs deve ser usado. Os números que não são dos EUA não serão roteados, a menos que a licença do Plano de Chamada seja atribuída ao usuário.

- John Woods – Política internacional.  As chamadas têm permissão para qualquer número. Ao chamar para o intervalo de números redmond, o conjunto específico de SBCs deve ser usado. Os números que não são dos EUA serão roteados usando sbc2.contoso.biz e sbc5.contoso.biz.

![Mostra a política de roteamento de voz atribuída ao usuário Spencer Low.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Para todas as outras chamadas, se um usuário tiver ambas as licenças (Telefone Microsoft System e Plano de Chamadas da Microsoft), a rota automática será usada. Se nada corresponde aos padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada usando o Plano de Chamadas da Microsoft.  Se o usuário tiver apenas Telefone Microsoft System, a chamada será descartada porque não há regras correspondentes disponíveis.

![Mostra a política de roteamento de voz atribuída ao usuário John Woods.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

A tabela a seguir resume as designações de uso e as rotas de voz da política de roteamento "Sem Restrições". 

| Uso de PSTN | Rota de voz | Padrão do número | Prioridade | SBC | Descrição |
|:-----|:-----|:-----|:-----|:-----|:-----|
|EUA e Canadá|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Rota ativa para números de chamador +1 425 XXX XX XX ou +1 206 XXX XX|
|EUA e Canadá|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Rota de backup para números de chamador +1 425 XXX XX XX ou +1 206 XXX XX|
|EUA e Canadá|"Outros +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Rote para números de chamador +1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Rote para qualquer padrão de número |

  > [!NOTE]
  > - A ordem dos usos de PSTN em políticas de roteamento de voz é crítica. Os usos são aplicados em ordem e, se uma combinação for encontrada no primeiro uso, outros usos nunca serão avaliados. O uso de PSTN "Internacional" deve ser colocado após o uso de PSTN "EUA e Canadá". Para alterar a ordem dos usos PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando. <br/>Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "Internacional" segundo para a ordem inversa executar:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - A prioridade para "Outras rotas de voz +1" e "Internacional" é atribuída automaticamente. Eles não importam desde que tenham prioridades inferiores que "Redmond 1" e "Redmond 2".

## <a name="example-2-configuration-steps"></a>Exemplo 2: Etapas de configuração

O exemplo a seguir mostra como:

1. Crie um novo uso PSTN chamado Internacional.
2. Crie uma nova rota de voz chamada Internacional.
3. Crie uma política de roteamento de voz chamada Sem Restrições.
4. Atribua a política ao usuário John Woods.

Você pode usar o Microsoft Teams [de administração ou](#admincenterexample2) o [PowerShell](#powershellexample2) para executar essas etapas.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Etapa 1: Criar o uso de PSTN "Internacional"

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Roteamento Direto de Voz e, no canto superior direito, selecione Gerenciar registros de uso  >   **PSTN.**
2. Clique **em Adicionar**, digite **Internacional** e clique em **Aplicar**.

#### <a name="step-2-create-the-international-voice-route"></a>Etapa 2: Criar a rota de voz "Internacional"

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Roteamento** Direto de Voz e selecione a  >  guia **Rotas de** voz.
2. Clique **em** Adicionar , insira "Internacional" como o nome e adicione a descrição.
3. De definir a prioridade como 4 e, em seguida, definir o padrão de número discado como \d+.
4. Em **SBCs inscritos (opcional),** clique em **Adicionar SBCs,** selecione sbc2.contoso.biz e sbc5.contoso.biz e clique em **Aplicar**.
5. Em **Registros de uso PSTN (opcional),** clique em Adicionar uso de **PSTN,** selecione o registro de uso de PSTN "Internacional" e clique em **Aplicar**.
6. Clique em **Salvar**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Etapa 3: criar uma política de roteamento de voz chamada "Sem Restrições" e adicionar os usos de PSTN "EUA e Canadá" e "Internacional" à política

O uso de PSTN "EUA e Canadá" é reutilizado nesta política de roteamento de voz para preservar o tratamento especial para chamadas para o número "+1 425 XXX XX XX" e "+1 206 XXX XX XX" como chamadas locais ou locais.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de roteamento **do Voice** Voice e clique  >  em **Adicionar**.
2. Digite **Sem Restrições** como o nome e adicione uma descrição.
3. Em **Registros de uso PSTN,** clique em Adicionar uso de **PSTN,** selecione o registro de uso PSTN "EUA e Canadá" e selecione o registro de uso de PSTN "Internacional". Clique em **Aplicar**.

    Anote a ordem de usos PSTN:

    - Se uma chamada feita para o número "+1 425 XXX XX XX" com os usos configurados como neste exemplo, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada. Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como rotas de backup.

    - Se o uso de PSTN "Internacional" for antes de "EUA e Canadá", as chamadas para +1 425 XXX XX serão roteados para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.

4. Clique em **Salvar**.

Para saber mais, confira [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Etapa 4: Atribuir a política de roteamento de voz a um usuário chamado John Woods

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Clique **em Políticas** e, ao lado de Políticas **Atribuídas,** clique em **Editar**.
3. Em **Política de roteamento de** voz, selecione a política "Sem restrições" e clique em **Salvar**.

O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponíveis para chamadas dos EUA, Canadá e Internacional.

### <a name="using-powershell"></a>Usando o Windows PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Etapa 1: Criar o uso de PSTN "Internacional"

Em uma sessão remota do PowerShell no Skype for Business Online, digite:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Etapa 2: Criar uma nova rota de voz chamada "Internacional"

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

Que retorna:

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Etapa 3: Criar uma política de roteamento de voz chamada "Sem Restrições"

O uso de PSTN "Redmond 1" e "Redmond" são reutilizados nesta política de roteamento de voz para preservar o tratamento especial para chamadas para o número "+1 425 XXX XX XX" e "+1 206 XXX XX XX" como chamadas locais ou locais.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Anote a ordem de usos PSTN:

  - Se uma chamada feita para o número "+1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada. Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como rotas de backup.

  - Se o uso de PSTN "Internacional" for antes de "EUA e Canadá", as chamadas para +1 425 XXX XX serão roteados para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento. Insira o comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Que retorna:

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Etapa 4: Atribuir a política de roteamento de voz ao usuário chamado John Woods

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Em seguida, verifique a atribuição usando o comando: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Que retorna:

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponíveis para chamadas dos EUA, canadá e internacional.

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
