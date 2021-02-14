---
title: Configuração de Arquivamento Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use as configurações de Arquivamento para controlar as opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global e, opcionalmente, uma ou mais configurações de site e pool:'
ms.openlocfilehash: 77d1be61be3a1bad063bb7f32957937f182094e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812251"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuração de Arquivamento: Criar Novo ou Editar Existente
 
Use as configurações de Arquivamento para controlar as opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global e, opcionalmente, uma ou mais configurações de site e pool:
  
- **Configuração global** A configuração global é criada por padrão. Você pode editar a configuração global, mas não pode excluir essa configuração de Arquivamento. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração do site (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de site, sendo possível configurar cada uma delas para controlar as opções de arquivamento de um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração de pool (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de pool para controlar as opções de arquivamento para um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> As configurações de arquivamento se aplicam aos usuários que estão no Skype for Business Server e, se você habilitar a opção de integração do Microsoft Exchange para usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, para os usuários que estão no Exchange. No entanto, algumas opções são implementadas de maneira ligeiramente diferente para os usuários que estão no Exchange, conforme descrito na próxima seção. 
  
Para definir as configurações de uma configuração de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada configuração de Arquivamento exige um nome. O nome é determinado pelo tipo de configuração que você está adicionando ou editando:
    
  - **Configuração global** O nome padrão é Global. Por exemplo, Contoso North American Organization.
    
  - **Configuração do site** A lista contém os sites disponíveis em sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Redmond Data Center.
    
  - **Configuração de pool** Especifique um nome apropriado, que pode ser o nome de um pool de front-end específico ou servidor Standard Edition em sua implantação. Por exemplo, Divisão de Marketing.
    
- **Descrição** Isso é opcional. Use-o para fornecer detalhes adicionais, como o escopo ou o uso da configuração. Por exemplo, Coordenação com os Departamentos jurídicos de outros sites.
    
- **Configuração de arquivamento** As opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e webconferências**
    
  - **Desabilitar arquivamento**
    
- **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se o arquivamento falhar** As falhas incluem o seguinte:
    
  - **Uma falha de IM** pode ser um banco de dados completo ou um problema com o serviço de armazenamento. Neste caso, as mensagens instantâneas são bloqueadas para os usuários que estiverem habilitados para arquivamento.
    
  - **Conferência** Uma falha pode ser um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.
    
- **Integração com o Microsoft Exchange** Selecione essa opção se tiver usuários que estão no Exchange. Com essa opção, o Exchange é usado para armazenar dados para esses usuários, se suas caixas de correio foram colocadas em In-Place Espera. Se todos os seus usuários estão no Exchange, não é necessário configurar bancos de dados separados do SQL Server para armazenamento de dados de arquivamento.
    
- **Habilitar a purgação de dados de arquivamento** Selecione essa opção para habilitar a purga e especificar opções de purga, que incluem o seguinte:
    
  - Purging after a specific number of days that you specify.
    
  - Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).
    
    > [!NOTE]
    > Se você habilitar a integração com o Microsoft Exchange, a purgação para usuários que estão localizados no Exchange e com suas caixas de correio colocadas em In-Place De espera será controlada pelo Exchange. A única exceção é para arquivos de conferência, que são armazenados no Lync Server File Share. Esses arquivos são limpos do compartilhamento de arquivos somente depois que os arquivos foram exportados (carregados para o Exchange), se você selecionar a opção para limpar dados após os dados de arquivamento foram exportados ou após o número máximo especificado de dias, se você especificar um número máximo de dias para retenção. 
  
Para obter detalhes sobre os recursos de Arquivamento, incluindo a integração com o Exchange, consulte [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), Deploy [archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and Manage [archiving in Skype for Business Server](../../../manage/archiving/archiving.md).

