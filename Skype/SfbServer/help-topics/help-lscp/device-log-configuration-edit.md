---
title: Editar configuração de log de dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Você pode adicionar uma configuração de log de dispositivo à página Editar configuração do log que determina o tamanho máximo do cache de log, o tamanho máximo do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização.
ms.openlocfilehash: 51804fb420c940494017cde86f3f8c62bd335424
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285957"
---
# <a name="device-log-configuration-edit"></a>Configuração de Log de Dispositivo: Editar
 
Você pode adicionar uma configuração de log de dispositivo à página **Editar configuração do log** que determina o tamanho máximo do cache de log, o tamanho máximo do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização.
  
> [!CAUTION]
> A exclusão remove permanentemente os arquivos do sistema de arquivos. Depois de excluir um arquivo, ele não poderá ser recuperado. 
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página **Editar configuração do log** :
  
- Adicione uma configuração de log de dispositivo globalmente ou para um site específico.
    
- Modificar as opções de um log de configuração de dispositivo existente.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Escopo** Identifica o escopo (global ou site) da configuração de log do dispositivo.
    
- **Nome** Você pode adicionar ou modificar o nome da configuração do log do dispositivo.
    
- **Tamanho máximo de arquivo (bytes)** Você pode especificar o tamanho máximo que um arquivo de log pode ficar antes de ser limpo. O padrão é 1.024.000 bytes (1 MB).
    
- **Tamanho máximo do cache (bytes)** Você pode especificar a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache deva ser limpo e os dados sejam gravados em um arquivo de log. O padrão é 512.000 bytes (0,5 MB).
    
- **Minutos para liberar o cache (1-60)** Você pode especificar com que frequência as informações armazenadas no cache do arquivo de log são gravadas no arquivo de log real. Depois que os dados são registrados, o cache é limpo. O padrão é cinco minutos.
    
- **Dias para manter os arquivos de log (1-365)** Você pode especificar o número de dias durante os quais os arquivos de log serão mantidos antes de serem limpos. O padrão é 10 dias.
    
## <a name="see-also"></a>Confira também

[Configuração do Log de Dispositivos](device-log-configuration.md)
