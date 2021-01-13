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
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele aparece na lista na página Dispositivo de Teste do Painel de Controle do Skype for Business Server.
ms.openlocfilehash: fd32fafd3b334344fe90c28e130e016dfbcf5043
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819041"
---
# <a name="test-device"></a>Dispositivo de Teste

É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele  aparece na lista na página Dispositivo de Teste do Painel de Controle do Skype for Business Server.

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

Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.
## <a name="see-also"></a>Confira também

[Dispositivo de Teste: Criar Novo ou Editar Existente](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de software para dispositivos na sua organização](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
