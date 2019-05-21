---
title: Dispositivo de Teste
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: É possível adicionar um dispositivo de teste à página Dispositivo de Teste e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do dispositivo de teste do painel de controle do Skype for Business Server.
ms.openlocfilehash: fd38e168d1d58c0bf1e330d08ae1d74c8d781221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300424"
---
# <a name="test-device"></a>Dispositivo de Teste

É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. É possível testar um dispositivo globalmente (em todo seu ambiente) ou dentro de um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do **dispositivo de teste** do painel de controle do Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página **testar dispositivo** :

- Adicione um dispositivo de teste globalmente ou para um site específico.

- Modifique as opções de um dispositivo de teste existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Novo** Você pode adicionar um novo dispositivo de teste com o seguinte escopo:

  - Global

  - Site

- **Editar** Você pode alterar as opções de um dispositivo de teste na lista. Com essa opção, é possível fazer o seguinte:

  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de um dispositivo de teste.

  - **Selecionar tudo** Essa opção seleciona todos os dispositivos de teste na lista.

  - **Excluir** Esta opção exclui todos os dispositivos de teste selecionados.

- **Atualização** Você pode atualizar a lista de dispositivos de teste para verificar o status das opções de todos os dispositivos de teste.

Para obter detalhes sobre como testar os dispositivos, consulte [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) na documentação Operações.
## <a name="see-also"></a>Confira também

[Dispositivo de Teste: Criar Novo ou Editar Existente](ms.lync.lscp.ClientDeviceTestEdit.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Exibir atualizações de software para dispositivos em sua organização](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
