---
title: Política de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Você usa políticas de arquivamento para habilitar e desabilitar o arquivamento para usuários hospedados no Skype for Business Server. Em cada política de Arquivamento, é possível habilitar ou desabilitar o arquivamento para uma das seguintes opções, ou para ambas:'
ms.openlocfilehash: c0bd80dcbe2c140d861829ff5bd1476d070423ba
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687014"
---
# <a name="archiving-policy"></a>Política de Arquivamento
 
Você usa políticas de arquivamento para habilitar e desabilitar o arquivamento para usuários hospedados no Skype for Business Server. Em cada política de Arquivamento, é possível habilitar ou desabilitar o arquivamento para uma das seguintes opções, ou para ambas:
  
- Comunicações internas
    
- Comunicações externas (comunicações que incluem pelo menos um usuário fora de sua rede interna)
    
As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de Arquivamento de site e de usuário:
  
- **Política global** A política global é criada por padrão em todas as implantações. É possível editar a política global, mas não é possível excluir essa política. Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.
    
- **Política do site (opcional)** Você pode especificar uma ou mais políticas de arquivamento de site, cada uma que pode ser configurada para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um único site. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de site de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Política de usuário (opcional)** Você pode especificar uma ou mais políticas de arquivamento do usuário, cada qual você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um usuário ou grupo de usuários específico. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários e grupos de usuário aos quais você atribui políticas de Arquivamento no nível do usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> As políticas de arquivamento aplicam-se somente aos usuários hospedados no Skype for Business Server. Se você usa a integração do Exchange para armazenar dados de arquivamento no Microsoft Exchange, as políticas do Exchange 2013 controlam o arquivamento para usuários hospedados no Exchange 2013. Para habilitar o arquivamento para esses usuários, a caixa de correio do usuário deve ser colocada no bloqueio in-loco. 
  
A página  **Política de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou usuário), e quais opções de arquivamento estão habilitadas para cada política de Arquivamento. Na página  **Política de Arquivamento**, você tem as seguintes opções:
- **Novo** Você pode adicionar uma ou mais das seguintes políticas de arquivamento opcionais:
    
  - Política de site
    
  - Política de usuário
    
- **Editar** Você pode alterar as opções de qualquer uma das políticas de arquivamento listadas na página. Com essa opção, é possível fazer o seguinte:
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual é possível alterar as opções de arquivamento de uma política de Arquivamento.
    
  - **Selecionar tudo**   Essa opção seleciona todas as políticas de Arquivamento na lista.
    
  - **Excluir**   Essa opção exclui todas as políticas de Arquivamento selecionadas.
    
- **Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de comunicações internas ou externas em qualquer política listada na página, em vez de editar a política. As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na política de Arquivamento. Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a política de Arquivamento. As opções incluem o seguinte:
    
  - **Habilitar arquivamento de comunicações internas**
    
  - **Desabilitar arquivamento de comunicações internas**
    
  - **Habilitar arquivamento de comunicações externas**
    
  - **Desabilitar arquivamento de comunicações externas**
    
- **Atualização** Você pode atualizar a página de **política de arquivamento** para verificar o status das opções de todas as políticas de arquivamento.
    
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração com o Exchange, consulte [planejar o arquivamento no Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [implantar o arquivamento para o Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [gerenciar o arquivamento no Skype for Business Server 2015](../../manage/archiving/archiving.md).

