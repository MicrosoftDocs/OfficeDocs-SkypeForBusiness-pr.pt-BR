---
title: Configuração do Log de Dispositivos
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: O serviço Device Update Web cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados de log, no tamanho do arquivo de log ou no tempo em que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o serviço Device Update Web exclua os arquivos de log automaticamente, será possível exclui-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
ms.openlocfilehash: cd9227d16e06d221a0c997787d906001d57c2f33
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757387"
---
# <a name="device-log-configuration"></a>Configuração do Log de Dispositivos

O serviço Device Update Web cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados de log, no tamanho do arquivo de log ou no tempo em que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o serviço Device Update Web exclua os arquivos de log automaticamente, será possível exclui-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.

> [!NOTE]
> Também é possível configurar um momento do dia em que você deseja que o serviço Device Update Web exclua automaticamente os arquivos de log mais antigos do que o número de dias configurado (por padrão, são os arquivos de log com mais de 10 dias). Essa configuração não pode ser modificada usando Skype for Business Server Painel de Controle. Em vez disso, você deve usar Skype for Business Server Shell de Gerenciamento. Para especificar a hora do dia para excluir arquivos de log expirados, use o cmdlet **New-CsDeviceUpdateConfiguration** com o parâmetro -LogCleanUpTimeOfDay. Para obter detalhes, [consulte New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> A exclusão permanente dos arquivos os remove do sistema de arquivos. Depois de excluir um arquivo, ele não pode ser recuperado.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Configuração do Log do Dispositivo**:

- Adicionar uma configuração de log de dispositivo globalmente ou para um site ou pool específico.

- Modificar as opções de um log de configuração de dispositivo existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Novo** Você pode adicionar uma nova configuração de log de dispositivo com o seguinte escopo:

  - Global

  - Site

- **Editar** Você pode alterar as opções de uma configuração de log de dispositivo na lista. Com essa opção, é possível fazer o seguinte:

  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma configuração de log de dispositivo.

  - **Selecionar Tudo** Essa opção seleciona todas as configurações de log de dispositivo na lista.

  - **Excluir** Essa opção exclui toda a configuração de log de dispositivo selecionada.

- **Atualizar** Você pode atualizar a lista de configurações de log do dispositivo para verificar o status das opções de todas as configurações de log de dispositivo.

## <a name="see-also"></a>Confira também

[Modificar Configurações arquivos de log da atividade de atualização de dispositivo](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)