---
title: Configuração de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use as configurações de arquivamento para controlar as opções de arquivamento para a implantação do Skype for Business Server, incluindo a ativação e a desativação das seguintes opções:'
ms.openlocfilehash: 1222e5e4c848f7ce0f3ca05943aa5b5acf4d365a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704696"
---
# <a name="archiving-configuration"></a>Configuração de Arquivamento
 
Use as configurações de arquivamento para controlar as opções de arquivamento para a implantação do Skype for Business Server, incluindo a ativação e a desativação das seguintes opções:
  
- Bloqueio de mensagens instantâneas (IM) ou sessões de conferência se o arquivamento falhar
    
- Integração com o armazenamento do Exchange para usuários hospedados no Exchange
    
- Limpeza de dados arquivados
    
As configurações de arquivamento incluem a configuração global e, como opção, uma ou mais configurações de Arquivamento de site e de pool:
  
- **Configuração global** A configuração global é criada por padrão em todas as implantações do Skype for Business Server. É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento. Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração de site (opcional)** Você pode especificar uma ou mais configurações de arquivamento de site, cada uma que pode ser configurada para controlar as opções de arquivamento de um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração de pool (opcional)** Você pode especificar uma ou mais configurações de arquivamento de pool para controlar as opções de arquivamento de um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> As configurações de arquivamento aplicam-se aos usuários hospedados no Skype for Business Server e, se você usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, para os usuários hospedados no Exchange, mas serão implementadas de forma ligeiramente diferente para os usuários hospedados no Exchange. As diferenças são descritas na próxima seção. 
  
A página **Configuração de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou pool), e quais opções de arquivamento estão habilitadas para cada configuração de Arquivamento. Na página  **Configuração de Arquivamento**, você tem as seguintes opções:
- **Novo** Você pode adicionar uma ou mais de cada uma das configurações de arquivamento opcionais a seguir.
    
  - Configuração de site
    
  - Configuração de pool
    
- **Editar** Você pode alterar as opções de qualquer uma das configurações de arquivamento listadas na página. Com essa opção, é possível fazer o seguinte:
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de arquivamento para a configuração de arquivamento selecionada. É possível mostrar apenas os detalhes de uma configuração de Arquivamento por vez.
    
  - **Selecionar tudo** Essa opção seleciona todas as configurações de arquivamento na lista.
    
  - **Excluir** Esta opção exclui todas as configurações de arquivamento selecionadas.
    
- **Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de sessões de mensagens instantâneas ou de sessões de Webconferência em qualquer configuração listada na página, em vez de editar a configuração. As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na configuração de Arquivamento. Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a configuração de Arquivamento. As opções incluem o seguinte:
    
  - **Arquivar sessões de IM**
    
  - **Arquivar sessões de IM e conferência da Web**
    
  - **Desativar arquivamento**
    
- **Atualização** Você pode atualizar a página de **configuração de arquivamento** para verificar o status das opções de todas as configurações de arquivamento.
    
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração com o Exchange, consulte [planejar o arquivamento no Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [implantar o arquivamento para o Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [gerenciar o arquivamento no Skype for Business Server](../../../manage/archiving/archiving.md).

