---
title: Configuração do Log de Dispositivos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: O serviço Device Update Web cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados de log, no tamanho do arquivo de log ou no tempo em que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o serviço Device Update Web exclua os arquivos de log automaticamente, será possível exclui-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
ms.openlocfilehash: c9bd2c3077325540e6151fabd7bc4127b909a12a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120270"
---
# <a name="device-log-configuration"></a>Configuração do Log de Dispositivos

O serviço Device Update Web cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados de log, no tamanho do arquivo de log ou no tempo em que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o serviço Device Update Web exclua os arquivos de log automaticamente, será possível exclui-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.

> [!NOTE]
> Também é possível configurar um momento do dia em que você deseja que o serviço Device Update Web exclua automaticamente os arquivos de log mais antigos do que o número de dias configurado (por padrão, são os arquivos de log com mais de 10 dias). Essa configuração não pode ser modificada usando o Painel de Controle do Skype for Business Server. Em vez disso, você deve usar o Shell de Gerenciamento do Skype for Business Server. Para especificar a hora do dia para excluir arquivos de log expirados, use o cmdlet **New-CsDeviceUpdateConfiguration** com o parâmetro -LogCleanUpTimeOfDay. Para obter detalhes, [consulte New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

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

[Modificar configurações para arquivos de log da atividade de atualização de dispositivo](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)