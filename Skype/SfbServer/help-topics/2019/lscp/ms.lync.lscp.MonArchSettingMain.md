---
title: Configuração de Arquivamento
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Você usa as configurações de arquivamento para controlar opções de arquivamento para sua Skype para implantação de servidor de negócios, incluindo habilitando e desabilitando as seguintes opções:'
ms.openlocfilehash: e32c42d5ef945b360ce4992ea9a33658bcc4068a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="archiving-configuration"></a>Configuração de Arquivamento
 
Você usa as configurações de arquivamento para controlar opções de arquivamento para sua Skype para implantação de servidor de negócios, incluindo habilitando e desabilitando as seguintes opções:
  
- Bloqueio de mensagens instantâneas (IM) ou sessões de conferência se o arquivamento falhar
    
- Integração com o armazenamento do Exchange 2013, para usuários hospedados no Exchange 2013
    
- Limpeza de dados arquivados
    
As configurações de arquivamento incluem a configuração global e, como opção, uma ou mais configurações de Arquivamento de site e de pool:
  
- **Configuração global** A configuração global criada por padrão no Skype todas as implantações de servidor de negócios. É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento. Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração de site (opcional)** Você pode especificar um ou mais sites as configurações de arquivamento, que cada um dos quais você pode configurar para controlar opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração de pool (opcional)** Você pode especificar um ou mais pool configuração de arquivamento, para controlar opções de arquivamento para um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> Configurações de arquivamento se aplicam a usuários hospedados no Skype para Business Server e, se você usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, para usuários hospedados no Exchange 2013, mas são implementadas de forma ligeiramente diferente para usuários hospedados no Exchange 2013. As diferenças são descritas na próxima seção. 
  
A página **Configuração de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou pool), e quais opções de arquivamento estão habilitadas para cada configuração de Arquivamento. Na página  **Configuração de Arquivamento**, você tem as seguintes opções:
- **Novo** Você pode adicionar um ou mais de cada uma das seguintes configurações de arquivamento opcionais.
    
  - Configuração de site
    
  - Configuração de pool
    
- **Editar** Você pode alterar as opções de qualquer uma das configurações de arquivamento listadas na página. Com essa opção, é possível fazer o seguinte:
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de arquivamento para a configuração de arquivamento selecionada. É possível mostrar apenas os detalhes de uma configuração de Arquivamento por vez.
    
  - **Selecionar tudo** Essa opção seleciona todas as configurações de arquivamento na lista.
    
  - **Excluir** Essa opção exclui todas as configurações de arquivamento selecionadas.
    
- **Ação** Você pode usar essa opção para habilitar ou desabilitar o arquivamento de sessões IM ou sessões de conferência da web em qualquer configuração listado na página, em vez de editar a configuração rapidamente. As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na configuração de Arquivamento. Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a configuração de Arquivamento. As opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e conferência da Web**
    
  - **Desativar arquivamento**
    
- **Atualizar** É possível atualizar a página de **Configuração de arquivamento** para verificar o status das opções de todas as configurações de arquivamento.
    
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração do Exchange, consulte [Planejar para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Gerenciar o arquivamento no Skype para Business 2015 de servidor](../../manage/archiving/archiving.md).

