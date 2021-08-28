---
title: Dispositivo de Teste
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele aparece na lista na página Dispositivo de Teste do painel Skype for Business Server Controle.
ms.openlocfilehash: 5e2d3be8ca9b010e97020004c3cb46c732d1ebc1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631705"
---
# <a name="test-device"></a>Dispositivo de Teste

É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele aparece na lista na página Dispositivo **de** Teste do painel Skype for Business Server Controle.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Dispositivo de Teste**:

- Adicionar um dispositivo de teste globalmente ou para um site específico.

- Modificar as opções de um dispositivo de teste existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Novo** Você pode adicionar um novo dispositivo de teste com o seguinte escopo:

  - Global

  - Site

- **Editar** Você pode alterar as opções de um dispositivo de teste na lista. Com essa opção, é possível fazer o seguinte:

  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de um dispositivo de teste.

  - **Selecionar Tudo** Essa opção seleciona todos os dispositivos de teste na lista.

  - **Excluir** Essa opção exclui todos os dispositivos de teste selecionados.

- **Atualizar** Você pode atualizar a lista de dispositivos de teste para verificar o status das opções de todos os dispositivos de teste.

Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) na documentação Operações.
## <a name="see-also"></a>Confira também

[Dispositivo de Teste: Criar Novo ou Editar Existente](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de software para dispositivos na sua organização](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)