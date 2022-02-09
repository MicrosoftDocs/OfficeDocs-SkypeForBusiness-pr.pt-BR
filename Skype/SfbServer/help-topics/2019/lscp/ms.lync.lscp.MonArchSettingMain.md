---
title: Configuração de Arquivamento
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você usa configurações de arquivamento para controlar as opções de arquivamento para sua implantação Skype for Business Server, incluindo habiligá-lo e desabilitar as seguintes opções:'
ms.openlocfilehash: 312a5722bd79952fe4f0674d6db7f93e64b1416b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402555"
---
# <a name="archiving-configuration"></a>Configuração de Arquivamento
 
Você usa configurações de arquivamento para controlar as opções de arquivamento para sua implantação Skype for Business Server, incluindo habiligá-lo e desabilitar as seguintes opções:
  
- Bloqueio de mensagens instantâneas (IM) ou sessões de conferência se o arquivamento falhar
    
- Integração com Exchange armazenamento, para usuários que estão no Exchange
    
- Limpeza de dados arquivados
    
As configurações de arquivamento incluem a configuração global e, como opção, uma ou mais configurações de Arquivamento de site e de pool:
  
- **Configuração global** A configuração global é criada por padrão em todas as Skype for Business Server implantações. É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração do site (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de site, cada uma das quais você pode configurar para controlar as opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração do pool (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de pool para controlar as opções de arquivamento de um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> As configurações de arquivamento se aplicam aos usuários que estão em casa no Skype for Business Server e, se você usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, aos usuários que estão no Exchange, mas são implementados de forma ligeiramente diferente para os usuários que estão no Exchange. As diferenças são descritas na próxima seção. 
  
A página **Configuração de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou pool), e quais opções de arquivamento estão habilitadas para cada configuração de Arquivamento. Na página **Configuração de Arquivamento**, você tem as seguintes opções:
- **Novo** Você pode adicionar uma ou mais das seguintes configurações opcionais de Arquivamento.
    
  - Configuração de site
    
  - Configuração de pool
    
- **Editar** Você pode alterar as opções de qualquer uma das configurações de Arquivamento listadas na página. Com essa opção, é possível fazer o seguinte:
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de arquivamento da configuração de Arquivamento selecionada. É possível mostrar apenas os detalhes de uma configuração de Arquivamento por vez.
    
  - **Selecionar todos** Essa opção seleciona todas as configurações de Arquivamento na lista.
    
  - **Excluir** Essa opção exclui todas as configurações de Arquivamento selecionadas.
    
- **Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de sessões de IM ou sessões de webconferência em qualquer configuração listada na página, em vez de editar a configuração. As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na configuração de Arquivamento. Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a configuração de Arquivamento. As opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e webconferências**
    
  - **Desabilitar arquivamento**
    
- **Atualizar** Você pode atualizar a página **Configuração de** Arquivamento para verificar o status das opções de todas as configurações de Arquivamento.
    
Para obter detalhes sobre o recurso e recursos de arquivamento, incluindo Exchange integração, consulte [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md) e [Manage archiving in Skype for Business Server ](../../../manage/archiving/archiving.md).

