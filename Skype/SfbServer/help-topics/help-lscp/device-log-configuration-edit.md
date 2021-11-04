---
title: Edição de Configuração de Log de Dispositivo
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Você pode adicionar uma configuração de log de dispositivo à página Editar Configuração de Log que determina o tamanho máximo do cache de log, o tamanho máximo do arquivo de log ou o período de tempo em que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização.
ms.openlocfilehash: b7f4dbd16ca9bbf03a74f84cfba15ca93e695743
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768969"
---
# <a name="device-log-configuration-edit"></a>Configuração de Log de Dispositivo: Editar
 
Você pode adicionar uma configuração de log de dispositivo à página Editar Configuração de **Log** que determina o tamanho máximo do cache de log, o tamanho máximo do arquivo de log ou o período de tempo em que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização.
  
> [!CAUTION]
> A exclusão permanente dos arquivos os remove do sistema de arquivos. Depois de excluir um arquivo, ele não pode ser recuperado. 
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página **Editar Configuração de Log:**
  
- Adicione uma configuração de log de dispositivo globalmente ou para um site específico.
    
- Modificar as opções de um log de configuração de dispositivo existente.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Escopo** Identifica o escopo (Global ou Site) da configuração de log do dispositivo.
    
- **Nome** Você pode adicionar ou modificar o nome da configuração de log do dispositivo.
    
- **Tamanho máximo do arquivo (bytes)** Você pode especificar o tamanho máximo que um arquivo de log pode se tornar antes de ser limpo. O padrão é 1.024.000 bytes (1 MB).
    
- **Tamanho máximo do cache (bytes)** Você pode especificar a quantidade máxima de informações (em bytes) que podem ser mantidas no cache do arquivo de log antes que esse cache seja limpo e os dados sejam gravados em um arquivo de log. O padrão é 512.000 bytes (0,5 MB).
    
- **Minutos para liberar o cache (1 a 60)** Você pode especificar com que frequência as informações armazenadas no cache do arquivo de log são gravadas no arquivo de log real. Depois que os dados são registrados, o cache é limpo. O padrão é cinco minutos.
    
- **Dias para manter arquivos de log (1-365)** Você pode especificar o número de dias em que os arquivos de log são mantidos antes que eles sejam limpos. O padrão é 10 dias.
    
## <a name="see-also"></a>Confira também

[Configuração do Log de Dispositivos](device-log-configuration.md)
