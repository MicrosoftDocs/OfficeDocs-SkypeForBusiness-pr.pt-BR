---
title: Configuração de Arquivamento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Você usa configurações de arquivamento para controlar as opções de arquivamento para sua implantação Skype for Business Server, incluindo habiligá-lo e desabilitar as seguintes opções:'
ms.openlocfilehash: 117e77b61e68c0af012ad23abd4757b571c63300e54b66b3385872edf9060d10
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338439"
---
# <a name="archiving-configuration"></a>Configuração de Arquivamento
 
Você usa configurações de arquivamento para controlar as opções de arquivamento para sua implantação Skype for Business Server, incluindo habiligá-lo e desabilitar as seguintes opções:
  
- Bloqueio de mensagens instantâneas (IM) ou sessões de conferência se o arquivamento falhar
    
- Integração com Exchange 2013, para usuários que estão no Exchange 2013
    
- Limpeza de dados arquivados
    
As configurações de arquivamento incluem a configuração global e, como opção, uma ou mais configurações de Arquivamento de site e de pool:
  
- **Configuração global** A configuração global é criada por padrão em todas as Skype for Business Server implantações. É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Configuração do site (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de site, cada uma das quais você pode configurar para controlar as opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento. É possível editar ou excluir as configurações de site.
    
- **Configuração do pool (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de pool para controlar as opções de arquivamento de um pool específico. Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento. É possível editar ou excluir as configurações de pool.
    
> [!NOTE]
> As configurações de arquivamento se aplicam aos usuários que estão em casa no Skype for Business Server e, se você usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, aos usuários que estão em casa no Exchange 2013, mas são implementados de forma ligeiramente diferente para usuários que estão no Exchange 2013. As diferenças são descritas na próxima seção. 
  
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
    
Para obter detalhes sobre o recurso e os recursos de arquivamento, incluindo Exchange integração, consulte [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

