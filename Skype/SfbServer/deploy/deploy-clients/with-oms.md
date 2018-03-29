---
title: Implantar o gerenciamento do Skype Room Systems v2 com OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de sistemas de sala Skype v2 dispositivos de forma integrada e de ponta a ponta, usando o pacote de gerenciamento de operações do Microsoft.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Implantar o gerenciamento do Skype Room Systems v2 com OMS
 
Este artigo discute como implantar o gerenciamento de sistemas de sala Skype v2 dispositivos de forma integrada e de ponta a ponta, usando o pacote de gerenciamento de operações do Microsoft. 
  
Você pode configurar o Microsoft Operations Management Suite (OMS) para fornecer telemetria básica que ajudará você a gerenciar os dispositivos de sala de reunião do Skype. Com o passar do tempo, você pode comprar recursos de gerenciamento e dados adicionais para sua solução a fim de criar um modo de exibição mais detalhado do desempenho do dispositivo.
  
Em um nível superior, é necessário executar as seguintes tarefas:
  
1. [Configurar os dispositivos para o Gerenciamento do OMS ](with-oms.md#config_devices)
    
2. [Mapear os campos personalizados](with-oms.md#Custom_fields)
    
3. [Definir os modos de exibição do SRS v2 no OMS](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>Localizar e registrar os locais, os recursos e as configurações do dispositivo
<a name="find_devices"> </a>

A primeira etapa é criar um banco de dados detalhado de todos os equipamentos do sistema, os detalhes de seus recursos e da configuração, bem como sua localização. No caso de organizações de pequeno e médio portes, uma planilha pode ser adequada para esta tarefa. Se você trabalhar em uma organização de grande porte, deverá considerar ferramentas de gerenciamento de ativos e serviços de terceiros. O importante é você registrar a localização e todos os detalhes relevantes de cada dispositivo.
  
Depois de concluir o trabalho, você pode usar essas informações para enviar técnicos e gerenciar patches e atualizações de dispositivos.
  
## <a name="configure-devices-for-oms-management"></a>Configurar os dispositivos para o Gerenciamento do OMS 
<a name="config_devices"> </a>

Para cada dispositivo SRS, siga as instruções encontradas em [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).
  
## <a name="configure-oms-to-collect-device-event-logs"></a>Configurar o OMS para obter logs de eventos do dispositivo
<a name="config_devices"> </a>

Você precisará configurar especificamente OMS para coletar logs de eventos de dispositivos SRS usando as etapas em [fontes de dados de log de eventos do Windows na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events). O log de eventos SRS para selecionar é "Skype sistema de sala" e você deve verificar as caixas de opção para todos os tipos: erro, aviso e informações.
  
## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Antes que os blocos criados nas [exibições de definir o v2 SRS no OMS](with-oms.md#Views) podem ser usados, você precisará criar campos personalizados para sua exibição. consulte [campos personalizados na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) para obter detalhes sobre como criar campos personalizados.
  
Use os mapeamentos mostrados abaixo, OMS adicionará automaticamente o _CF ao definir o novo campo. 
  
> [!IMPORTANT]
> Lembre-se de que os campos JSON e OMS diferenciam maiúsculas de minúsculas. 
  
**Mapeamento de campos personalizados**

|**Campo JSON**|**Campo personalizado de OMS**|
|:-----|:-----|
|Descrição  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|Nomedaoperação  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|Sistema operacional  <br/> |SRSOSVersion_CF  <br/> |
|Versão do sistema operacional  <br/> |SRSOSLongVersion_CF  <br/> |
|Alias  <br/> |SRSAlias_CF  <br/> |
|DisplayName  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4Address  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6Address  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>Definir os modos de exibição do SRS v2 no OMS
<a name="Views"> </a>

Depois que os dados forem coletados e os campos personalizados forem mapeados, você poderá usar o Designer de exibição do OMS para desenvolver um painel contendo blocos para monitorar os eventos SRS v2. Use o Designer de modo de exibição para criar os seguintes blocos, consulte [Use o Designer de modo de exibição para criar exibições personalizadas na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) , conforme necessário.
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>Criar um bloco que mostre os dispositivos íntegros

1. Definir o caso: 
    
    Este bloco exibe todos os dispositivos de integridade que enviaram uma mensagem de pulsação nos últimos 10 minutos.
    
2. Atribuir bloco de grupo  
    
   ```
   SRS v2
   ```

3. Marcar a caixa de novo grupo
    
4. Adicionar texto de legenda de bloco
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. Inserir a consulta de bloco
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. Inserir a consulta de lista
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. Definir o nome dos títulos da coluna
    
   ```
   Display Name
   ```

8. Definir o valor dos títulos da coluna
    
   ```
   Last HB
   ```

9. Inserir a consulta de navegação
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>Criar o bloco que mostra os dispositivos com problemas de conectividade

1. Definir o caso: 
    
    Este bloco exibe todos os dispositivos que não enviaram uma mensagem de pulsação nos últimos 10 minutos. Esses dispositivos podem estar com problemas de conectividade com a rede, com o Exchange ou com o Skype for Business.
    
2. Atribuir bloco de grupo  
    
   ```
   SRS v2
   ```

3. Não marcar caixa de novo grupo. Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.
    
4. Adicionar texto de legenda de bloco
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. Inserir a consulta de bloco
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. Inserir a consulta de lista
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. Definir o nome dos títulos da coluna
    
   ```
   Device Name
   ```

8. Definir o valor dos títulos da coluna 
    
   ```
   Last HB
   ```

9. Inserir a consulta de navegação
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>Listar dispositivos com erro de hardware 

1. Definir o caso: 
    
   Este elemento exibe todos os dispositivos que enviaram uma mensagem indicando uma problemas de componente de hardware de um ou mais nos últimos 10 minutos. 
    
2. Atribuir bloco de grupo  
    
   ```
   SRS v2
   ```

3. Não marcar caixa de novo grupo. Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.
    
4. Legenda do bloco:  
    
   ```
   Devices with a Hardware Error
   ```

5. Consulta de bloco
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. Consulta de lista:
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. Nome dos títulos da coluna:  
    
   ```
   Display Name
   ```

8. Valor dos títulos da coluna:  
    
   ```
   Last Error
   ```

9. Consulta de navegação:  
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>Listar dispositivos com erro de aplicativo 

1. Definir o caso: 
    
   Este bloco exibe todos os dispositivos de SRS que reportaram um ou mais erros de componente de aplicativo nos últimos 10 minutos.
    
2. Atribuir bloco de grupo  
    
   ```
   SRS v2
   ```

3. Não marcar caixa de novo grupo. Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.
    
4. Legenda do bloco:  
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. Consulta de bloco:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. Consulta de lista:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. Nome dos títulos da coluna:  
    
   ```
   Device Name
   ```

8. Valor dos títulos da coluna:  
    
   ```
   Last Error
   ```

9. Consulta de navegação:
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>Listar dispositivos que exigem reinicialização

1. Definir o caso: 
    
   Este bloco exibe todos os dispositivos de SRS que foram reinicializados nas últimas 24 horas e a quantidade de reinicializações
    
2. Atribuir bloco de grupo  
    
  ```
  SRS v2
  ```

3. Não marcar caixa de novo grupo. Você já fez isso ao criar o bloco 1 e não precisa fazer isso novamente.
    
4. Legenda do bloco:  
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. Consulta de bloco:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. Consulta de lista:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. Nome dos títulos da coluna:  
    
   ```
   Display Name
   ```

8. Valor dos títulos da coluna:  
    
   ```
   Number of restarts
   ```

9. Consulta de navegação:  
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

Isso conclui a criação do modo de exibição. Os alertas atualmente disponíveis são todos refletidos em um ou mais desses blocos.
## <a name="see-also"></a>Ver também
<a name="Views"> </a>

#### 

[Planejar o gerenciamento de v2 Skype sala sistemas com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Gerencia dispositivos de v2 de sistemas de sala Skype com OMS](../../manage/skype-room-systems-v2/oms.md)

