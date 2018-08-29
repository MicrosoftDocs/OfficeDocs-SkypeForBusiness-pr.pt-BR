---
title: Dispositivo de teste
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ela será exibida na lista na página Testar dispositivo do Skype para painel de controle do Business Server.
ms.openlocfilehash: 4a410a5f82c346d88520e7e56f5bf6bf5150480c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257105"
---
# <a name="test-device"></a>Dispositivo de teste

É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ela será exibida na lista na página **Testar dispositivo** do Skype para painel de controle do Business Server.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página **Dispositivo de teste** :

- Adicione um dispositivo de teste globalmente ou para um site específico.

- Modificar as opções de um dispositivo de teste existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Novo** Você pode adicionar um novo dispositivo de teste com o seguinte escopo:

  - Global

  - Site

- **Editar** Você pode alterar as opções de um dispositivo de teste na lista. Com essa opção, é possível fazer o seguinte:

  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para um dispositivo de teste.

  - **Selecionar tudo** Essa opção seleciona todos os dispositivos de teste na lista.

  - **Excluir** Essa opção exclui todos os dispositivos de teste selecionados.

- **Atualizar** É possível atualizar a lista de dispositivo de teste para verificar o status das opções de todos os dispositivos de teste.

Para obter detalhes sobre dispositivos de teste, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação operações.
## <a name="see-also"></a>Consulte também

[Dispositivo de Teste: Criar Novo ou Editar Existente](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de Software para dispositivos em sua organização](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)