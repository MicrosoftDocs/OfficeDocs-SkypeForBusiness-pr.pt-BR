---
title: Dispositivo de teste criar novo ou editar existente
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ela será exibida na lista na página Testar dispositivo do Skype para painel de controle do Business Server.
ms.openlocfilehash: 1bb61f99ceab29eb3915e7650e1a760b1798f0db
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882268"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo de Teste: Criar Novo ou Editar Existente

O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ela será exibida na lista na página **Testar dispositivo** do Skype para painel de controle do Business Server.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página  **Novo Dispositivo de Teste** ou **Editar Dispositivo de Teste**:

- Adicionar um novo dispositivo de teste.

- Modificar as propriedades de um dispositivo de teste existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Escopo** Identifica o escopo (Global ou Site) do dispositivo de teste.

- **Nome** É possível adicionar ou modificar o nome do dispositivo de teste.

- **Nome do dispositivo** É possível adicionar ou modificar o nome do dispositivo de teste.

- **Tipo de identificador** Você pode selecionar o método utilizado para identificar o dispositivo selecionando uma das seguintes opções:

  - **Endereço MAC**

  - **Número de série**

- **Identificador exclusivo** Você pode digitar o endereço MAC ou número de série do dispositivo.

Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.
## <a name="see-also"></a>Consulte Também

[Dispositivo de Teste](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de Software para dispositivos em sua organização](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
