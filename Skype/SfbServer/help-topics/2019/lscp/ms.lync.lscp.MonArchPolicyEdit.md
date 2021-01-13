---
title: Política de Arquivamento Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use as políticas de Arquivamento para controlar o arquivamento de comunicações internas e externas em sua implantação para usuários que estão no Skype for Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:'
ms.openlocfilehash: 71ffa03d0d3af8ea98fcc9ded17d4e3498e1705e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820311"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Política de Arquivamento: Criar Nova ou Editar Existente
 
Use as políticas de Arquivamento para controlar o arquivamento de comunicações internas e externas em sua implantação para usuários que estão no Skype for Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:
  
- **Política global** A política global é criada por padrão em todas as implantações do Skype for Business Server. É possível editar a política global, mas não é possível excluir essa política. Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.
    
- **Políticas de site (opcional)** Você pode especificar uma ou mais políticas de Arquivamento de site, sendo possível configurar cada uma delas para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um site específico. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Políticas de usuário (opcional)** Você pode especificar uma ou mais políticas de Arquivamento de usuário, sendo possível configurar cada uma delas para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um usuário específico. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários aos quais você atribui uma política de usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> Se você usar a integração com o Exchange para armazenar dados de arquivamento no Microsoft Exchange, as políticas do Exchange controlarão o arquivamento de usuários que estão no Exchange. Para habilitar o arquivamento para esses usuários, a caixa de correio do usuário deve ser colocada In-Place Espera. 
  
Para definir as configurações de uma política de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada política de Arquivamento exige um nome. O nome é determinado pelo tipo de política que você está adicionando ou editando:
    
  - **Política global** O nome padrão é Global. É possível alterá-lo para um nome mais descritivo. Por exemplo, Contoso North American Organization.
    
  - **Política de site** Os sites listados nesta caixa de diálogo incluem todos os sites disponíveis em sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Redmond Data Center.
    
  - **Política de usuário** Especifique um nome apropriado, como o nome de um usuário específico ou o nome de um grupo de usuários ou equipe em sua organização. Por exemplo, Departamento jurídico.
    
- **Descrição** Isso é opcional. Use para fornecer detalhes adicionais, como o escopo ou uso da política. Por exemplo, Coordenação com os Departamentos jurídicos de outros sites.
    
- **Arquivar comunicações internas** Marque essa caixa de seleção para habilitar o arquivamento de comunicações em sua rede interna. Por padrão, isso não está habilitado em qualquer política.
    
- **Arquivar comunicações externas** Marque essa caixa de seleção para habilitar o arquivamento de comunicações que incluem usuários externos, como usuários remotos (incluindo usuários anônimos e configurações de PIC) e parceiros federados. Por padrão, isso não está habilitado em qualquer política.
    
Para obter detalhes sobre os recursos de Arquivamento, incluindo a integração com o Exchange, consulte [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), Deploy [archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and Manage [archiving in Skype for Business Server](../../../manage/archiving/archiving.md).

