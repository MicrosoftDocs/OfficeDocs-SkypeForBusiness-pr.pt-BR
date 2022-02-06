---
title: Política de Arquivamento Criar Novo ou Editar Existente
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
  - ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Você usa políticas de arquivamento para controlar o arquivamento de comunicações internas e externas em sua implantação para usuários que estão no Skype for Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:'
---

# <a name="archiving-policy-create-new-or-edit-existing"></a>Política de Arquivamento: Criar Nova ou Editar Existente
 
Você usa políticas de arquivamento para controlar o arquivamento de comunicações internas e externas em sua implantação para usuários que estão no Skype for Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:
  
- **Política global** A política global é criada por padrão em todas as Skype for Business Server implantações. É possível editar a política global, mas não é possível excluir essa política. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Políticas de site (opcional)** Você pode especificar uma ou mais políticas de Arquivamento de site, cada uma das quais você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um site específico. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Políticas de usuário (opcional)** Você pode especificar uma ou mais políticas de Arquivamento de usuários, cada uma das quais você pode configurar para habilitar e desabilitar o arquivamento para comunicações internas ou externas para um usuário específico. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários aos quais você atribui uma política de usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> Se você usar Exchange integração para armazenar dados de arquivamento no Microsoft Exchange, as políticas do Exchange 2013 controlam o arquivamento para usuários que estão no Exchange 2013. Para habilitar o arquivamento para esses usuários, a caixa de correio do usuário deve ser colocada In-Place Espera. 
  
Para definir as configurações de uma política de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada política de Arquivamento requer um nome. O nome é determinado pelo tipo de política que você está adicionando ou editando:
    
  - **Política global** O nome padrão é Global. É possível alterá-lo para um nome mais descritivo. Por exemplo, Contoso North American Organization.
    
  - **Política de site** Os sites listados nesta caixa de diálogo incluem todos os sites disponíveis em sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Redmond Data Center.
    
  - **Política de usuário** Especifique um nome apropriado, como o nome de um usuário específico ou o nome de um grupo de usuários ou equipe em sua organização. Por exemplo, Departamento jurídico.
    
- **Descrição** Isso é opcional. Use para fornecer detalhes adicionais, como o escopo ou uso da política. Por exemplo, Coordenação com os Departamentos jurídicos de outros sites.
    
- **Arquivar comunicações internas** Marque essa caixa de seleção para habilitar o arquivamento de comunicações em sua rede interna. Por padrão, isso não está habilitado em qualquer política.
    
- **Arquivar comunicações externas** Marque essa caixa de seleção para habilitar o arquivamento de comunicações que incluem usuários externos, como usuários remotos, (incluindo usuários anônimos e de configuração de PIC) e parceiros federados. Por padrão, isso não está habilitado em qualquer política.
    
Para obter detalhes sobre o recurso e recursos de arquivamento, incluindo Exchange integração, consulte [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md) e [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

