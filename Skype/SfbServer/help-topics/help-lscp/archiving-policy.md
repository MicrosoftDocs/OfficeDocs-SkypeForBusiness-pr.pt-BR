---
title: Política de Arquivamento
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Use as políticas de arquivamento para habilitar e desabilitar arquivamento para usuários hospedados no Skype para Business Server. Em cada política de Arquivamento, é possível habilitar ou desabilitar o arquivamento para uma das seguintes opções, ou para ambas:'
ms.openlocfilehash: eea3f7eb71bcf3928e2976b9468cea6bf94b4ab1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy"></a>Política de Arquivamento
 
Use as políticas de arquivamento para habilitar e desabilitar arquivamento para usuários hospedados no Skype para Business Server. Em cada política de Arquivamento, é possível habilitar ou desabilitar o arquivamento para uma das seguintes opções, ou para ambas:
  
- Comunicações internas
    
- Comunicações externas (comunicações que incluem pelo menos um usuário fora de sua rede interna)
    
As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de Arquivamento de site e de usuário:
  
- **Política global** A política global criada por padrão em todas as implantações. É possível editar a política global, mas não é possível excluir essa política. Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.
    
- **Política de site (opcional)** Você pode especificar um ou mais sites as políticas de arquivamento, que cada um dos quais você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um único site. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de site de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Política de usuário (opcional)** Você pode especificar um ou mais usuários as políticas de arquivamento, que cada um dos quais você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um usuário específico ou grupo de usuários. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários e grupos de usuário aos quais você atribui políticas de Arquivamento no nível do usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> Políticas de arquivamento aplicam-se somente a usuários hospedados no Skype para Business Server. Se você usar a integração do Exchange para armazenar dados no Microsoft Exchange, em seguida, o Exchange 2013 políticas de arquivamento o controle de arquivamento para usuários hospedados no Exchange 2013. Para habilitar o arquivamento para os usuários, a caixa de correio do usuário deve ser colocada em retenção In-loco. 
  
A página  **Política de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou usuário), e quais opções de arquivamento estão habilitadas para cada política de Arquivamento. Na página  **Política de Arquivamento**, você tem as seguintes opções:
- **Novo** Você pode adicionar um ou mais de cada uma das seguintes políticas de arquivamento opcionais:
    
  - Política de site
    
  - Política de usuário
    
- **Editar** Você pode alterar as opções de qualquer uma das políticas de arquivamento listadas na página. Com essa opção, é possível fazer o seguinte:
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual é possível alterar as opções de arquivamento de uma política de Arquivamento.
    
  - **Selecionar tudo**   Essa opção seleciona todas as políticas de Arquivamento na lista.
    
  - **Excluir**   Essa opção exclui todas as políticas de Arquivamento selecionadas.
    
- **Ação** Você pode usar essa opção para habilitar ou desabilitar o arquivamento de comunicações internos ou externos em qualquer política listada na página, em vez de edição da política de rapidamente. As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na política de Arquivamento. Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a política de Arquivamento. As opções incluem o seguinte:
    
  - **Habilitar arquivamento de comunicações internas**
    
  - **Desabilitar arquivamento de comunicações internas**
    
  - **Habilitar arquivamento de comunicações externas**
    
  - **Desabilitar arquivamento de comunicações externas**
    
- **Atualizar** É possível atualizar a página **Política** de arquivamento para verificar o status das opções de todas as políticas de arquivamento.
    
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração do Exchange, consulte [Planejar para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Gerenciar o arquivamento no Skype para Business 2015 de servidor](../../manage/archiving/archiving.md).

