---
title: Configuração de arquivamento criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use as configurações de Arquivamento para controlar as opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global, e, como opção, uma ou mais configurações de site e de pool:'
ms.openlocfilehash: 0e6985fa40c82b1b958df99c332cb4ec5fe23b07
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891114"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuração de Arquivamento: Criar Novo ou Editar Existente
 
Use as configurações de Arquivamento para controlar as opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global, e, como opção, uma ou mais configurações de site e de pool:
  
- **Configuração global** A configuração global criada por padrão. É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração de site (opcional)** Você pode especificar um ou mais sites as configurações de arquivamento, que cada um dos quais você pode configurar para controlar opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração de pool (opcional)** Você pode especificar um ou mais pool as configurações de arquivamento, para controlar opções de arquivamento para um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> Configurações de arquivamento se aplicam a usuários hospedados no Skype para Business Server e, se você habilitar a opção de integração do Microsoft Exchange para usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, para usuários hospedados no Exchange. No entanto, algumas opções são implementadas ligeiramente diferente para usuários hospedados no Exchange, conforme descrito na próxima seção. 
  
Para definir as configurações de uma configuração de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada configuração de arquivamento requer um nome. O nome é determinado pelo tipo de configuração que você está adicionando ou editando:
    
  - **Configuração global** O nome padrão é Global. Por exemplo, Organização Norte Americana Contoso.
    
  - **Configuração de site** A lista contém os sites disponíveis na sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Data Center Redmond.
    
  - **Configuração de pool** Especifique um nome apropriado, que pode ser o nome de um determinado pool de Front-End ou servidor Standard Edition em sua implantação. Por exemplo, Divisão de Marketing.
    
- **Descrição** Isto é opcional. Use para fornecer detalhes adicionais, como o escopo ou uso da configuração. Por exemplo, Coordenação com os departamentos jurídicos de outros sites.
    
- **Configuração de arquivamento** Opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e conferência da Web**
    
  - **Desativar arquivamento**
    
- **Bloquear mensagens instantâneas (IM) ou sessões de conferência da web se o arquivamento falhar** Falhas incluem o seguinte:
    
  - **Mensagens Instantâneas** uma falha poderia ser um banco de dados completo ou um problema com o serviço de armazenamento. Nesse caso, IM fica bloqueado por usuários habilitados para Arquivamento.
    
  - **Conferência** Uma falha poderia ser um compartilhamento de arquivos não está disponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.
    
- **Integração com o Microsoft Exchange** Selecione essa opção se você tiver usuários hospedados no Exchange. Com essa opção, o Exchange é usado para armazenar dados para os usuários, se suas caixas de correio tiverem sido colocadas em retenção In-loco. Se todos os usuários hospedados no Exchange, você não precisará configurar bancos de dados do SQL Server separados para armazenamento de dados de arquivamento.
    
- **Habilitar a limpeza de dados de arquivamento** Selecione essa opção para habilitar a limpeza e especificar as opções de limpeza, que incluem o seguinte:
    
  - Limpeza após um número específico de dias definido por você.
    
  - Limpeza após os dados de arquivamento terem sido exportado (que contém os dados que foram carregados para o Exchange, se você habilitar a integração com o Microsoft Exchange).
    
    > [!NOTE]
    > Se você habilitar a integração do Microsoft Exchange, limpeza para usuários hospedados no Exchange e com suas caixas de correio colocadas em retenção In-loco é controlado pelo Exchange. A única exceção é para arquivos de conferência, que são armazenados no compartilhamento de arquivos do Lync Server. Esses arquivos são excluídos do compartilhamento de arquivo somente após serem exportados (carregados no Exchange), se você selecionar a opção para limpar os dados após a exportação dos dados de arquivamento ou após o número máximo de dias especificado, se você especificar um número máximo de dias para retenção. 
  
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração do Exchange, consulte [planejamento para arquivamento no Skype para Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy arquivamento para Skype para Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [Gerenciar o arquivamento no Skype para negócios Servidor](../../../manage/archiving/archiving.md).

