---
title: Configuração de Arquivamento Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Você usa configurações de arquivamento para controlar opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global e, opcionalmente, uma ou mais configurações de site e pool:'
ms.openlocfilehash: 3dfeace1bf5f8243e1ee82c76021864ec51182fb
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384789"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuração de Arquivamento: Criar Novo ou Editar Existente
 
Você usa configurações de arquivamento para controlar opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global e, opcionalmente, uma ou mais configurações de site e pool:
  
- **Configuração global** A configuração global é criada por padrão. Você pode editar a configuração global, mas não pode excluir essa configuração de Arquivamento. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração do site (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de site, cada uma das quais você pode configurar para controlar as opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração do pool (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de pool para controlar as opções de arquivamento de um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> As configurações de arquivamento se aplicam aos usuários que estão em casa no Skype for Business Server e, se você habilitar a opção de integração do Microsoft Exchange para usar o Exchange 2013 para armazenar dados de arquivamento no Microsoft Exchange, aos usuários que estão no Exchange 2013. No entanto, algumas opções são implementadas de forma ligeiramente diferente para usuários Exchange 2013, conforme descrito na próxima seção. 
  
Para definir as configurações para uma configuração de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada configuração de Arquivamento requer um nome. O nome é determinado pelo tipo de configuração que você está adicionando ou editando:
    
  - **Configuração global** O nome padrão é Global. Por exemplo, Contoso North American Organization.
    
  - **Configuração do site** A lista contém os sites disponíveis em sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Redmond Data Center.
    
  - **Configuração do pool** Especifique um nome apropriado, que pode ser o nome de um pool front-end específico ou Edição Standard Server em sua implantação. Por exemplo, Divisão de Marketing.
    
- **Descrição** Isso é opcional. Use-o para fornecer detalhes adicionais, como o escopo ou o uso da configuração. Por exemplo, Coordenação com os Departamentos jurídicos de outros sites.
    
- **Configuração de arquivamento** As opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e webconferências**
    
  - **Desabilitar arquivamento**
    
- **Bloquear sessões de mensagens instantâneas (IM) ou webconferência se o arquivamento falhar** As falhas incluem o seguinte:
    
  - **IM** Uma falha pode ser um banco de dados completo ou um problema com o serviço de armazenamento. Neste caso, as mensagens instantâneas são bloqueadas para os usuários que estiverem habilitados para arquivamento.
    
  - **Conferência** Uma falha pode ser um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.
    
- **Integração Exchange Microsoft** Selecione essa opção se você tiver usuários que estão Exchange 2013. Com essa opção, Exchange 2013 é usado para armazenar dados para esses usuários, se suas caixas de correio foram colocadas em In-Place Hold. Se todos os seus usuários estão no Exchange 2013, você não precisa configurar bancos de dados SQL Server separados para armazenamento de dados de arquivamento.
    
- **Habilitar a purgação de dados de arquivamento** Selecione essa opção para habilitar a purga e especificar opções de purga, que incluem o seguinte:
    
  - Purging after a specific number of days that you specify.
    
  - Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).
    
    > [!NOTE]
    > Se você habilitar Exchange integração do Microsoft Exchange, a purgação para usuários localizados no Exchange 2013 e com suas caixas de correio colocadas no In-Place Hold será controlada por Exchange. A única exceção é para arquivos de conferência, que são armazenados no Lync Server file share. Esses arquivos serão limpos do compartilhamento de arquivos somente depois que os arquivos foram exportados (carregados para Exchange), se você selecionar a opção para limpar dados após a exportação dos dados de arquivamento ou após o número máximo especificado de dias, se você especificar um número máximo de dias para retenção. 
  
Para obter detalhes sobre o recurso e recursos de arquivamento, incluindo Exchange integração, consulte [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md) e [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

