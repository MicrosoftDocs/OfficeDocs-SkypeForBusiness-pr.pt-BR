---
title: Edição de configuração de Log de dispositivo
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Você pode adicionar uma configuração de log de dispositivo para a página Editar configuração de Log que determina o tamanho de cache máximo do log, tamanho do arquivo de log máximo ou período de tempo que um arquivo de log é mantido antes de ele será limpo. Você pode alterar essas configurações de acordo com requisitos da sua organização.
ms.openlocfilehash: 7e2e5091c662f105b47e2a3a8574c144457753dc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974435"
---
# <a name="device-log-configuration-edit"></a>Configuração de Log de dispositivo: Editar
 
Você pode adicionar uma configuração de log de dispositivo para a página **Editar configuração de Log** que determina o tamanho de cache máximo do log, tamanho do arquivo de log máximo ou período de tempo que um arquivo de log é mantido antes de ele será limpo. Você pode alterar essas configurações de acordo com requisitos da sua organização.
  
> [!CAUTION]
> A exclusão remove permanentemente os arquivos do sistema de arquivos. Depois de excluir um arquivo, ele não poderá ser recuperado. 
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página **Editar configuração de Log** :
  
- Adicione uma configuração de log de dispositivo globalmente ou para um site específico.
    
- Modificar as opções de um log de configuração de dispositivo existente.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Escopo** Identifica o escopo (Global ou Site) da configuração de log de dispositivo.
    
- **Nome** É possível adicionar ou modificar o nome da configuração de log de dispositivo.
    
- **Tamanho máximo do arquivo (bytes)** Você pode especificar o tamanho máximo de que um arquivo de log pode se tornar antes que ele será limpo. O padrão é 1.024.000 bytes (1 MB).
    
- **Tamanho de cache máximo (bytes)** Você pode especificar a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache deve estar desmarcada e os dados são gravados em um arquivo de log. O padrão é 512,000 bytes (0,5 MB).
    
- **Minutos para liberar o cache (1-60)** Você pode especificar com que frequência informações armazenadas no cache de arquivos de log são gravadas no arquivo de log atual. Depois que os dados são registrados, o cache está desmarcado. O padrão é cinco minutos.
    
- **Dias para manter os arquivos de log (1-365)** Você pode especificar o número de dias que os arquivos de log são mantidos antes de serem expurgados. O padrão é 10 dias.
    
## <a name="see-also"></a>Consulte também

[Configuração do Log de Dispositivos](ms.lync.lscp.ClientDeviceCfgMain.md)