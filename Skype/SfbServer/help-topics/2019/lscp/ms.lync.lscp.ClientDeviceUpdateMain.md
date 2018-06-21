---
title: Atualização de Dispositivos
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: A Microsoft lança periodicamente um novo conjunto de atualizações de firmware do dispositivo para Skype para negócios Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. Você pode obter o mais recente conjunto de regras de atualização de dispositivo, indo para a página de Ajuda e suporte no site da Microsoft e pesquisando forPhone Edition.Download o pacote de atualização mais recente e extraia os arquivos para uma pasta no computador onde as atualizações devem ser carregadas. Depois que os arquivos foram extraídos, você pode, em seguida, usar o cmdlet Import-CsDeviceUpdate para importar as regras de atualização de dispositivo encontradas no extraídos. Arquivo CAB (que terá o nome UCUpdates.cab). Para obter detalhes, consulte Import-CsDeviceUpdate.
ms.openlocfilehash: 793f7328d3396f1e734e709f24f61bb802c26a47
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978066"
---
# <a name="device-update"></a>Atualização de dispositivo
 
A Microsoft lança periodicamente um novo conjunto de atualizações de firmware do dispositivo para Skype para negócios Phone Edition, que você pode importar para seus servidores e distribuir aos usuários. É possível obter o conjunto mais recente de regras de atualização de dispositivo acessando a página Ajuda e Suporte no site da Microsoft e pesquisando por "Phone Edition". Baixe o pacote de atualizações mais recente e extraia os arquivos para uma pasta no computador onde as atualizações deverão ser carregadas. Após a extração dos arquivos, você poderá usar o cmdlet **Import-CsDeviceUpdate** para importar as regras de atualização de dispositivo encontradas no arquivo .CAB extraído (que terá o nome UCUpdates.cab). Para obter detalhes, consulte [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).
  
Depois que as regras de atualização de dispositivo tenham sido importadas, você pode usar a página **Atualização do dispositivo** para exibir e gerenciar essas regras para os dispositivos da sua organização.
  
> [!TIP]
> É possível testar as atualizações de firmware e, supondo que os testes foram bem-sucedidos, disponibilizar as atualizações a todos os dispositivos relevantes usados na organização. 
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página  **Atualização de Dispositivo**:
  
- Aprovar as atualizações de dispositivo na lista.
    
- Cancelar ou restaurar atualizações de dispositivo pendentes.
    
- Excluir atualizações de dispositivo da lista.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Editar** Você pode usar essa opção para fazer o seguinte:
    
  - **Selecionar tudo** Essa opção seleciona todas as atualizações de dispositivo na lista.
    
  - **Excluir** Essa opção exclui todas as atualizações do dispositivo selecionado.
    
- **Ação** Você pode selecionar uma ou mais atualizações na lista e execute as seguintes ações:
    
  - **Cancelar atualizações pendentes** Essa opção impede que a atualização selecionada sendo implantada nos dispositivos da sua organização.
    
  - **Aprovar** Essa opção permite a atualização selecionada para serem implantados nos dispositivos da sua organização.
    
  - **Restaurar** Essa opção permite que uma atualização aprovada anteriormente a serem implantados nos dispositivos da sua organização
    
- **Atualizar** É possível atualizar a lista para verificar o status de todas as atualizações de dispositivo.
    
Para obter detalhes sobre o serviço Web de atualização de dispositivo, consulte [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) na documentação de planejamento.
## <a name="see-also"></a>Consulte também

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)