---
title: Configuração do Log de Dispositivos
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: O Serviço Web de Atualização de Dispositivo cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, convém definir limites sobre o tamanho do cache de dados de log, tamanho do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ele será limpo. Você pode alterar essas configurações de acordo com requisitos da sua organização. Se você não quiser que o Serviço Web de Atualização de Dispositivo exclua os arquivos de log automaticamente, será possível excluí-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
ms.openlocfilehash: e5a88c7437b654846fd464133b953465cd5d3e2a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="device-log-configuration"></a>Configuração do Log de Dispositivos
 
O Serviço Web de Atualização de Dispositivo cria automaticamente os arquivos de log que registram a atividade de atualização do dispositivo. Como parte da estratégia de gerenciamento de dados da sua organização, convém definir limites sobre o tamanho do cache de dados de log, tamanho do arquivo de log ou o período de tempo que um arquivo de log é mantido antes de ele será limpo. Você pode alterar essas configurações de acordo com requisitos da sua organização. Se você não quiser que o Serviço Web de Atualização de Dispositivo exclua os arquivos de log automaticamente, será possível excluí-los manualmente, conforme o necessário. As configurações de log podem ser alteradas globalmente ou de acordo com o site.
  
> [!NOTE]
> Também é possível configurar um horário do dia em que você deseja que o Serviço Web de Atualização de Dispositivo exclua automaticamente os arquivos de log mais antigos do que o número de dias configurado (por padrão, são os arquivos de log com mais de 10 dias). Essa configuração não pode ser modificada usando Skype para painel de controle do servidor de negócios. Em vez disso, você deve usar Skype do Shell de gerenciamento do servidor de negócios. Para especificar a hora do dia para excluir arquivos de log expirados, use o cmdlet **New-CsDeviceUpdateConfiguration** com o parâmetro - LogCleanUpTimeOfDay. Para obter detalhes, consulte [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps). 
  
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
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma configuração de log de dispositivo.
    
  - **Selecionar tudo** Essa opção seleciona todas as configuração de log de dispositivo na lista.
    
  - **Excluir** Essa opção exclui todas as configuração de log do dispositivo selecionado.
    
- **Atualizar** É possível atualizar a lista de configuração de log de dispositivo para verificar o status das opções de configuração de log de todos os dispositivos.
    
## <a name="see-also"></a>Consulte também

#### 

[Modificar as configurações para os arquivos de Log da atividade de atualização de dispositivo](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)

