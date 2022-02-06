---
title: Política de Arquivamento
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Você usa políticas de arquivamento para habilitar e desabilitar o arquivamento para usuários que estão em Skype for Business Server. Em cada política de Arquivamento, você pode habilitar ou desabilitar o arquivamento para ambos os seguintes:'
---

# <a name="archiving-policy"></a>Política de Arquivamento
 
Você usa políticas de arquivamento para habilitar e desabilitar o arquivamento para usuários que estão em Skype for Business Server. Em cada política de Arquivamento, você pode habilitar ou desabilitar o arquivamento para ambos os seguintes:
  
- Comunicações internas
    
- Comunicações externas (comunicações que incluem pelo menos um usuário fora da rede interna)
    
As políticas de arquivamento incluem a política global e, opcionalmente, uma ou mais políticas de arquivamento de sites e usuários:
  
- **Política global** A política global é criada por padrão em todas as implantações. É possível editar a política global, mas não é possível excluir essa política. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Política de site (opcional)** Você pode especificar uma ou mais políticas de Arquivamento de site, cada uma das quais você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um único site. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de site de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Política de usuário (opcional)** Você pode especificar uma ou mais políticas de Arquivamento de usuários, cada uma delas pode ser configurada para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um usuário ou grupo de usuários específico. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários e grupos de usuários aos quais você atribui políticas de Arquivamento no nível do usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> As políticas de arquivamento aplicam-se somente aos usuários que estão no Skype for Business Server. Se você usar Exchange integração para armazenar dados de arquivamento no Microsoft Exchange, as políticas do Exchange 2013 controlam o arquivamento para usuários que estão no Exchange 2013. Para habilitar o arquivamento para esses usuários, a caixa de correio do usuário deve ser colocada In-Place Espera. 
  
A **página Política de Arquivamento lista** cada política de Arquivamento configurada para sua implantação. Ele também mostra o nome da política, o escopo (global, site ou usuário) e quais opções de arquivamento estão habilitadas para cada política de Arquivamento. Na página **Política de Arquivamento** , você tem as seguintes opções:
- **Novo** Você pode adicionar uma ou mais de cada uma das seguintes políticas opcionais de Arquivamento:
    
  - Política de site
    
  - Política de usuário
    
- **Editar** Você pode alterar as opções de qualquer uma das políticas de Arquivamento listadas na página. Com essa opção, é possível fazer o seguinte:
    
  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de arquivamento de uma política de Arquivamento.
    
  - **Selecionar todos** Essa opção seleciona todas as políticas de Arquivamento na lista.
    
  - **Excluir** Essa opção exclui todas as políticas de Arquivamento selecionadas.
    
- **Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de comunicações internas ou externas em qualquer política listada na página, em vez de editar a política. As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na política de Arquivamento. Todas as opções estão disponíveis, exceto a opção atualmente em vigor para a política de Arquivamento. As opções incluem o seguinte:
    
  - **Habilitar o arquivamento de comunicações internas**
    
  - **Desabilitar o arquivamento de comunicações internas**
    
  - **Habilitar o arquivamento de comunicações externas**
    
  - **Desabilitar o arquivamento de comunicações externas**
    
- **Atualizar** Você pode atualizar a página **Política de** Arquivamento para verificar o status das opções de todas as políticas de Arquivamento.
    
Para obter detalhes sobre o recurso e recursos de arquivamento, incluindo Exchange integração, consulte [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md) e [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

