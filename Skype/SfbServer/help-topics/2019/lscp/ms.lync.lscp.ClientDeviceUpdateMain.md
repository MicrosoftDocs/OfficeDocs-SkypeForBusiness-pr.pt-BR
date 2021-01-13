---
title: Atualização de Dispositivo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: A Microsoft periodicamente lança um novo conjunto de atualizações de firmware do dispositivo para o Skype for Business Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. Você pode obter o conjunto mais recente de regras de atualização de dispositivos indo para a página Ajuda e Suporte no site da Microsoft e procurando porPhone Edition.Baixe o pacote de atualização mais recente e extraia os arquivos para uma pasta no computador onde as atualizações devem ser carregadas. Após a extração dos arquivos, você poderá usar o cmdlet Import-CsDeviceUpdate para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab). Para obter detalhes, consulte Import-CsDeviceUpdate.
ms.openlocfilehash: cd8b983990ff3bc5843c252a153eafaa47cd9a1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830281"
---
# <a name="device-update"></a>Atualização de Dispositivo

A Microsoft periodicamente lança um novo conjunto de atualizações de firmware do dispositivo para o Skype for Business Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. É possível obter o conjunto mais recente de regras de atualização de dispositivo acessando a página Ajuda e Suporte no site da Microsoft e pesquisando por "Phone Edition". Baixe o pacote de atualizações mais recente e extraia os arquivos para uma pasta no computador onde as atualizações deverão ser carregadas. Após a extração dos arquivos, você poderá usar o cmdlet **Import-CsDeviceUpdate** para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab). Para obter detalhes, [consulte Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Depois que as regras de atualização de  dispositivos foram importadas, você pode usar a página Atualização de Dispositivo para exibir e gerenciar essas regras para os dispositivos da sua organização.

> [!TIP]
> É possível testar as atualizações de firmware e, supondo que os testes foram bem-sucedidos, disponibilizar as atualizações a todos os dispositivos relevantes usados na organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Atualização de Dispositivo**:

- Aprovar as atualizações de dispositivo na lista.

- Cancelar ou restaurar atualizações de dispositivo pendentes.

- Excluir atualizações de dispositivo da lista.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Editar** Você pode usar essa opção para fazer o seguinte:

  - **Selecionar Tudo** Essa opção seleciona todas as atualizações de dispositivo na lista.

  - **Excluir** Essa opção exclui todas as atualizações de dispositivo selecionadas.

- **Ação** Você pode selecionar uma ou mais atualizações na lista e tomar as seguintes ações:

  - **Cancelar atualizações pendentes** Essa opção impede que a atualização selecionada seja implantada nos dispositivos da sua organização.

  - **Aprovar** Essa opção permite que a atualização selecionada seja implantada nos dispositivos da sua organização.

  - **Restaurar** Essa opção permite que uma atualização aprovada anteriormente seja implantada nos dispositivos da sua organização

- **Atualizar** Você pode atualizar a lista para verificar o status de todas as atualizações de dispositivo.

Para obter detalhes sobre o serviço Device Update Web, consulte [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) na documentação Planejamento.
## <a name="see-also"></a>Confira também

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
