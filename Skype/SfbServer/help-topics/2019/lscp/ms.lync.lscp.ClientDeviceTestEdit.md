---
title: Test Device Create New or Edit Existing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: O recurso Test Device funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele aparece na lista na página Dispositivo de Teste do Painel de Controle do Skype for Business Server.
ms.openlocfilehash: 959abca17e208a397cbdd9ad6a69ba241aad4362
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100627"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo de Teste: Criar Novo ou Editar Existente

O recurso Test Device funciona em conjunto com o recurso Atualização de Dispositivo. É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele aparece na lista na página Dispositivo **de** Teste do Painel de Controle do Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página Novo Dispositivo **de Teste** ou Editar **Dispositivo de** Teste:

- Adicione um novo dispositivo de teste.

- Modifique as propriedades de um dispositivo de teste existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Escopo** Identifica o escopo (Global ou Site) do dispositivo de teste.

- **Nome** Você pode adicionar ou modificar o nome do dispositivo de teste.

- **Nome do dispositivo** Você pode adicionar ou modificar o nome do dispositivo de teste.

- **Tipo de identificador** Você pode selecionar o método a ser usado para identificar o dispositivo selecionando um dos seguintes:

  - **Endereço MAC**

  - **Número de série**

- **Identificador exclusivo** Você pode digitar o endereço MAC ou o número de série do dispositivo.

Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) na documentação Operações.
## <a name="see-also"></a>Confira também

[Dispositivo de Teste](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de software para dispositivos na sua organização](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)