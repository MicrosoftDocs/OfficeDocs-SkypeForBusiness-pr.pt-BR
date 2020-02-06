---
title: Dispositivo de teste criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do dispositivo de teste do painel de controle do Skype for Business Server.
ms.openlocfilehash: 2101fb712d1084506de617ab234e3e8e0a03a961
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794540"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo de Teste: Criar Novo ou Editar Existente

O recurso Dispositivo de Teste funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do **dispositivo de teste** do painel de controle do Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página  **Novo Dispositivo de Teste** ou **Editar Dispositivo de Teste**:

- Adicionar um novo dispositivo de teste.

- Modificar as propriedades de um dispositivo de teste existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Escopo** Identifica o escopo (global ou site) do dispositivo de teste.

- **Nome** Você pode adicionar ou modificar o nome do dispositivo de teste.

- **Nome do dispositivo** Você pode adicionar ou modificar o nome do dispositivo de teste.

- **Tipo de identificador** Você pode selecionar o método a ser usado para identificar o dispositivo selecionando um dos seguintes procedimentos:

  - **Endereço MAC**

  - **Número de série**

- **Identificador exclusivo** Você pode digitar o endereço MAC ou o número de série do dispositivo.

Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.
## <a name="see-also"></a>Confira também

[Dispositivo de Teste](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de software para dispositivos em sua organização](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
