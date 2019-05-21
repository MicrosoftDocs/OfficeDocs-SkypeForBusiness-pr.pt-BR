---
title: Configuração do arquivamento criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use as configurações de Arquivamento para controlar as opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global, e, como opção, uma ou mais configurações de site e de pool:'
ms.openlocfilehash: 68d5de88fc56441989e8ffc9ceabfd3236179d1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291975"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configuração de Arquivamento: Criar Novo ou Editar Existente
 
Use as configurações de Arquivamento para controlar as opções de arquivamento para sua implantação. As configurações de arquivamento incluem a configuração global, e, como opção, uma ou mais configurações de site e de pool:
  
- **Configuração global** A configuração global é criada por padrão. É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração de site (opcional)** Você pode especificar uma ou mais configurações de arquivamento de site, cada uma que pode ser configurada para controlar as opções de arquivamento de um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração de pool (opcional)** Você pode especificar uma ou mais configurações de arquivamento de pool para controlar as opções de arquivamento de um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> As configurações de arquivamento se aplicam aos usuários hospedados no Skype for Business Server e, se você habilitar a opção de integração do Microsoft Exchange para usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, para os usuários hospedados no Exchange. No entanto, algumas opções são implementadas de modo ligeiramente diferente para os usuários hospedados no Exchange, conforme descrito na próxima seção. 
  
Para definir as configurações de uma configuração de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada configuração de arquivamento exige um nome. O nome é determinado pelo tipo de configuração que você está adicionando ou editando:
    
  - **Configuração global** O nome padrão é global. Por exemplo, Organização Norte Americana Contoso.
    
  - **Configuração do site** A lista contém os sites disponíveis na sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Data Center Redmond.
    
  - **Configuração de pool** Especifique um nome apropriado, que pode ser o nome de um pool de front-end específico ou um servidor Standard Edition na sua implantação. Por exemplo, Divisão de Marketing.
    
- **Descrição** Isso é opcional. Use para fornecer detalhes adicionais, como o escopo ou uso da configuração. Por exemplo, Coordenação com os departamentos jurídicos de outros sites.
    
- **Configuração** de arquivamento As opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e conferência da Web**
    
  - **Desativar arquivamento**
    
- **Bloquear sessões de mensagens instantâneas (IM) ou Web Webconferência se o arquivamento falhar** Falhas incluem o seguinte:
    
  - **Mensagem instantânea** uma falha pode ser um banco de dados completo ou um problema com o serviço de armazenamento. Nesse caso, IM fica bloqueado por usuários habilitados para Arquivamento.
    
  - **Conferência** Uma falha pode ser um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.
    
- **Integração com o Microsoft Exchange** Selecione essa opção se você tiver usuários que são hospedados no Exchange. Com essa opção, o Exchange é usado para armazenar dados para esses usuários, se as suas caixas de correio tiverem sido colocadas no bloqueio in-loco. Se todos os usuários estiverem hospedados no Exchange, você não precisará configurar bancos de dados individuais do SQL Server para armazenamento de dados de arquivamento.
    
- **Habilitar a limpeza de dados de arquivamento** Selecione esta opção para habilitar a limpeza e especificar opções de limpeza, que incluem o seguinte:
    
  - Limpeza após um número específico de dias definido por você.
    
  - Descarte após a exportação dos dados de arquivamento (que inclui dados que foram carregados no Exchange, se você habilitar a integração com o Microsoft Exchange).
    
    > [!NOTE]
    > Se você habilitar a integração do Microsoft Exchange, a limpeza para os usuários hospedados no Exchange e nas caixas de correio contidas no bloqueio in-loco será controlada pelo Exchange. A única exceção é para arquivos de conferência, que são armazenados no compartilhamento de arquivos do Lync Server. Esses arquivos são excluídos do compartilhamento de arquivo somente após serem exportados (carregados no Exchange), se você selecionar a opção para limpar os dados após a exportação dos dados de arquivamento ou após o número máximo de dias especificado, se você especificar um número máximo de dias para retenção. 
  
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração com o Exchange, consulte [planejar o arquivamento no Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [implantar o arquivamento para o Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [gerenciar o arquivamento no Skype for Business Servidor](../../../manage/archiving/archiving.md).

