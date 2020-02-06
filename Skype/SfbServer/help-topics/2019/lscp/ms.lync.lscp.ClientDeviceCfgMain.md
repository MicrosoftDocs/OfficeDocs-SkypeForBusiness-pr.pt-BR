---
title: Configuração do Log de Dispositivos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: O Serviço Web de Atualização de Dispositivo cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados do log, no tamanho do arquivo de log ou na duração de tempo que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o Serviço Web de Atualização de Dispositivo exclua os arquivos de log automaticamente, será possível excluí-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
ms.openlocfilehash: 43fc784113a81038469099807770945ee2fbcc3b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794550"
---
# <a name="device-log-configuration"></a>Configuração do Log de Dispositivos

O Serviço Web de Atualização de Dispositivo cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, talvez você queira definir limites no tamanho do cache de dados do log, no tamanho do arquivo de log ou na duração de tempo que um arquivo de log é mantido antes de ser limpo. Você pode alterar essas configurações de acordo com os requisitos da sua organização. Se você não quiser que o Serviço Web de Atualização de Dispositivo exclua os arquivos de log automaticamente, será possível excluí-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.

> [!NOTE]
> Também é possível configurar um horário do dia em que você deseja que o Serviço Web de Atualização de Dispositivo exclua automaticamente os arquivos de log mais antigos do que o número de dias configurado (por padrão, são os arquivos de log com mais de 10 dias). Esta configuração não pode ser modificada usando o painel de controle do Skype for Business Server. Em vez disso, você deve usar o Shell de gerenciamento do Skype for Business Server. Para especificar a hora do dia para excluir os arquivos de log expirados, use o cmdlet **New-CsDeviceUpdateConfiguration** com o parâmetro-LogCleanUpTimeOfDay. Para obter detalhes, consulte [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> A exclusão remove permanentemente os arquivos do sistema de arquivos. Depois de excluir um arquivo, ele não poderá ser recuperado.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página  **Configuração do Log do Dispositivos**:

- Adicionar uma configuração de log de dispositivo globalmente ou para um site ou pool específico.

- Modificar as opções de um log de configuração de dispositivo existente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Novo** Você pode adicionar uma nova configuração de log de dispositivo com o seguinte escopo:

  - Global

  - Site

- **Editar** Você pode alterar as opções de uma configuração de log de dispositivo na lista. Com essa opção, é possível fazer o seguinte:

  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma configuração de log de dispositivo.

  - **Selecionar tudo** Essa opção seleciona toda a configuração do log do dispositivo na lista.

  - **Excluir** Esta opção exclui toda a configuração de log do dispositivo selecionada.

- **Atualização** Você pode atualizar a lista de configuração do log do dispositivo para verificar o status das opções de toda a configuração do log do dispositivo.

## <a name="see-also"></a>Confira também

[Modificar as configurações dos arquivos de log da atividade de atualização do dispositivo](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
