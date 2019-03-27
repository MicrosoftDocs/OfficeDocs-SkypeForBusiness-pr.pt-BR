---
title: Relatório de dispositivo no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Resumo: Saiba mais sobre o relatório de dispositivo no Skype para Business Server.'
ms.openlocfilehash: adb4293ec6d643d86f439e0458ae5352f1e49f3c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888413"
---
# <a name="device-report-in-skype-for-business-server"></a>Relatório de dispositivo no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de dispositivo no Skype para Business Server.
  
O Relatório de Dispositivos poderia trocar de nome para Relatório de Microfones e Alto-Falantes; isso porque o Relatório de Dispositivos recupera métricas relacionadas às chamadas (como o percentual de chamadas ruins, eco e tempo de troca de voz) agrupadas por microfone e alto-falante usados na chamada. Se você estiver interessado em telefones IP (também conhecidos como "dispositivos"), use o [Relatório de inventário de telefones IP no Skype para Business Server](ip-phone-inventory-report.md) .
  
O Relatório de Dispositivos é extremamente útil para os administradores ao determinar se um tipo específico de dispositivo está apresentando mais chamadas de baixa qualidade que outros. Por outro lado, pode influenciar decisões relacionadas à compra de novos dispositivos ou à substituição de dispositivos existentes.
  
Por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, vamos supor que você tenha vários usuários que utilizam os seguintes dispositivos de captura e renderização: por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, vamos supor que você tenha vários usuários que utilizam os seguintes dispositivos de captura e renderização:
  
- Dispositivo de captura -- Microfone (SoundMAX Integrated Digital HD Audio)
    
- Dispositivo de renderização -- Fone de ouvido com headset (Microsoft LifeChat LX-3000)
    
Se esses usuários fizerem um total de 254 chamadas, você verá uma entrada como esta no relatório:
  
|**Dispositivo de captura**|**Dispositivo de renderização**|**Volume da chamada**|
|:-----|:-----|:-----|
|Microfone (SoundMAX Integrated Digital HD Audio)  <br/> |Fone de ouvido com headset (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
Agora, suponha que você tem um número de usuários que usam esse mesmo dispositivo de captura, mas que usam um dispositivo de renderização diferente. Neste caso, você terá uma segunda linha no relatório, uma para essa combinação exclusiva de dispositivo de captura e dispositivo de renderização:
  
|**Dispositivo de captura**|**Dispositivo de renderização**|**Volume da chamada**|
|:-----|:-----|:-----|
|Microfone (SoundMAX Integrated Digital HD Audio)  <br/> |Fone de ouvido com headset (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Microfone (SoundMAX Integrated Digital HD Audio)  <br/> |Alto-falantes (SoundMAX Integrated Digital HD Audio)  <br/> |319  <br/> |
   
Se você preferir ver os totais combinados para um determinado dispositivo (por exemplo, para o dispositivo de captura SoundMAX, independente do dispositivo de renderização usado), selecione a opção apropriada na lista suspensa de tipo de dispositivo (dispositivo de captura ou dispositivo de renderização). Se você selecionar dispositivo de captura neste exemplo, terá algo parecido com isso:
  
|**Dispositivo de captura**|**Volume da chamada**|
|:-----|:-----|
|Microfone (SoundMAX Integrated Digital HD Audio)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Acessando o relatório de dispositivos

O Relatório de Dispositivos é geralmente acessado na página inicial dos Relatórios de Monitoramento. No entanto, se você estiver exibindo o [Relatório detalhado de chamadas no Skype para Business Server](call-detail-report.md) você pode analisar o relatório de dispositivo para um dispositivo específico clicando em uma das seguintes métricas:
  
- Dispositivo de captura
    
- Dispositivo de renderização
    
Do relatório de dispositivo, você pode analisar o [Call List Report no Skype para Business Server](call-list-report-0.md) clicando em uma das seguintes métricas:
  
- Volume da chamada
    
- Porcentagem de chamadas ruins
    
## <a name="making-the-best-use-of-the-device-report"></a>Como usar melhor o Relatório de Dispositivos

Tratando-se de nomes de dispositivos, o Relatório de Dispositivos é extremamente detalhado. Por exemplo, suponha que você tem os seguintes dispositivos de captura:
  
- Microfone Aastra 3002 (2- Aastra 3002)
    
- Microfone Aastra 3002 (3- Aastra 3002)
    
- Microfone Aastra 3002 (Aastra 3002)
    
- Aastra 6725ip
    
- Microfone Aastra 6725ip (10- Aastra 6725ip)
    
- Microfone Aastra 6725ip (10- Aastra 6725ip)-V0
    
- Microfone Aastra 6725ip (2- Aastra 6725ip)
    
- Microfone Aastra 6725ip (3- Aastra 6725ip)
    
- Microfone Aastra 6725ip (4- Aastra 6725ip)
    
- Microfone Aastra 6725ip (5- Aastra 6725ip)
    
- Microfone Aastra 6725ip (6- Aastra 6725ip)
    
- Microfone Aastra 6725ip (7- Aastra 6725ip)
    
- Microfone Aastra 6725ip (9- Aastra 6725ip)
    
- Microfone Aastra 6725ip (9- Aastra 6725ip)-V0
    
- Microfone Aastra 6725ip (Aastra 6725ip)
    
- Microfone Aastra 6725ip (Aastra 6725ip)-V0
    
- Microfone Aastra 6725ip (Dispositivo de áudio USB)
    
- Microfone Aastra 6725ip (Dispositivo de áudio USB)-V0
    
> [!NOTE]
> Tenha em mente que nomes de dispositivos de captura podem não ser o mesmo se você estiver executando versões localizadas do Skype para Business Server. Um dispositivo denominado Microfone Aastra 6725ip (Aastra 6725ip)-V0 em português pode ter um nome diferente em francês ou espanhol. 
  
Muitas vezes você precisará desse nível de detalhe; mas, em outros momentos, você só estará interessado na quantidade de chamadas que usam um microfone Aastra, independente do número do modelo. Uma forma de obter informações deste tipo é exportar os dados do Relatório de Dispositivos para o Microsoft Excel e salvar esses dados em um arquivo de valores separados por vírgulas (por exemplo, C:\Data\Devices_Report.csv). É possível usar um conjunto de comandos parecidos com esses para importar o arquivo .CSV no Windows PowerShell e relatar o número total de chamadas feitas usando um dispositivo de captura Aastra:
  
```
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Esse procedimento retornará um único valor que representa o número total de chamadas usando um dispositivo de captura Aastra. Por exemplo: 384

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. Por exemplo, o Relatório de Dispositivos permite filtrar coisas como o tipo de chamada (isto é, a chamada foi realizada pelo cliente), uma chamada de conferência ou chamada PSTN. É possível também escolher como os dados devem ser agrupados. Neste caso, os dispositivos são agrupados por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Dispositivos.
  
**Filtros do Relatório de Dispositivos**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Causa de troca de voz** <br/> |Motivo pelo qual uma chamada precisou ser colocada no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie. Selecione um dos seguintes:  <br/> [Todos] Nenhum eco de pós-AEC do estado da baixa complexidade para eco DNLP (processador não linear dinâmico) timestamp ruim dispositivo inválido (cancelamento de eco acústico) |
|**Causa do eco** <br/> |Motivo pelo qual o eco acima do aceitável foi detectado em uma chamada. (Em telecomunicações, o eco é um reflexo do som, o mesmo fenômeno que você ouvirá se gritar em um poço). Selecione um dos seguintes:  <br/> [Todos] Nenhum timestamp ruim pós-AEC eco distorção do microfone DNLP (processador não linear dinâmico) de ANLP (processador não linear adaptado) (cancelamento de eco acústico) |
|**Tipo de chamada** <br/> |Indica o tipo de chamada realizada. Selecione um dos seguintes:  <br/> [Todos] Chamada de cliente chamada PSTN chamada em conferência |
|**Tipo de acesso** <br/> |Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:  <br/> [Todos] Internos externos |
|**Tipo de rede** <br/> |Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:  <br/> [Todos] Sem fio com fio |
|**VPN** <br/> |Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:  <br/> [Todos] Não VPN VPN |
|**Tipo de dispositivo** <br/> |Indica o tipo de dispositivo. Selecione um dos seguintes:  <br/> Capturar um par de dispositivos de captura/renderização do dispositivo de renderização de dispositivo |
|**Nome do dispositivo** <br/> |Nome do dispositivo de captura ou renderização. É possível inserir o nome completo do dispositivo ou qualquer parte do nome. Por exemplo para encontrar o dispositivo Microfone (Microsoft LifeCam VX-1000.), é possível inserir o nome completo do dispositivo, como a seguir:  <br/> Microfone (Microsoft LifeCam VX-1000.)  <br/> Como alternativa, é possível inserir apenas uma parte do nome. Por exemplo:  <br/> LifeCam  <br/> Observe que o filtro anterior retorna qualquer dispositivo que contém a cadeia de caracteres "LifeCam" em qualquer local do seu nome.  <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista a informação apresentada no Relatório de Dispositivos.
  
**Métricas do Relatório de Dispositivos**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Dispositivo de captura** <br/> |Sim  <br/> |Dispositivo (por exemplo, um microfone ou webcam) usado para transmitir áudio.  <br/> |
|**Dispositivo de renderização** <br/> |Sim  <br/> |Dispositivo (por exemplo, um fone de ouvido ou alto falantes) usados para receber áudio.  <br/> |
|**Volume da chamada** <br/> |Sim  <br/> |Número total de chamadas realizadas.  <br/> |
|**Porcentagem de chamadas ruins** <br/> |Sim  <br/> |Porcentagem de chamadas classificadas como "inválidas". Uma chamada inválida é qualquer chamada na qual pelo menos uma métrica medida excede o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Usuários únicos** <br/> |Sim  <br/> |Usuários exclusivos que utilizaram o dispositivo. Se um usuário utilizou o dispositivo 13 vezes, ele ou ela deve contar como um usuário exclusivo, o mesmo que um usuário que utilizou o dispositivo uma única vez.  <br/> |
|**Tempo de troca da taxa de voz** <br/> |Sim  <br/> |Porcentagem da chamada que precisou ser conduzida no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.  <br/> |
|**Taxa de microfones não funcionando** <br/> |Sim  <br/> |Porcentagem da chamada na qual o dispositivo de captura não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de captura não estar funcionando conforme esperado.  <br/> |
|**Taxa de alto falantes não funcionando** <br/> |Sim  <br/> |Porcentagem da chamada na qual o dispositivo de renderização não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de renderização não estar funcionando conforme esperado.  <br/> |
|**Chamadas com troca de voz (%)** <br/> |Sim  <br/> |Porcentagem do total de chamadas que precisaram ser colocadas no modo half duplex. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.  <br/> |
|**Microfone com eco em (%)** <br/> |Sim  <br/> |Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou celulares e mais altos para viva voz e auto falante. Para dispositivos que suportam cancelamento de eco acústico na placa, os altos níveis indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser utilizada para avaliar a qualidade do dispositivo.  <br/> |
|**Envio de eco (%)** <br/> |Sim  <br/> |Porcentagem de eco transmitido para outros usuários.  <br/> |
|**Chamadas com eco (%)** <br/> |Sim  <br/> |Porcentagem do total de chamadas que tiveram eco excedendo o nível aceitável.  <br/> |
   

