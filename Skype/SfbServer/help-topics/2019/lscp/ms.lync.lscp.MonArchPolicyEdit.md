---
title: Política de arquivamento criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você usa políticas de arquivamento para controlar o arquivamento de comunicações internas e externas em sua implantação para os usuários que estão hospedados no Skype for Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:'
ms.openlocfilehash: 87dc7764f80f722108189fb99209d8a9388f5d8b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291968"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Política de Arquivamento: Criar Nova ou Editar Existente
 
Você usa políticas de arquivamento para controlar o arquivamento de comunicações internas e externas em sua implantação para os usuários que estão hospedados no Skype for Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:
  
- **Política global** A política global é criada por padrão em todas as implantações do Skype for Business Server. É possível editar a política global, mas não é possível excluir essa política. Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.
    
- **Políticas de site (opcional)** Você pode especificar uma ou mais políticas de arquivamento de site, cada qual você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um site específico. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Políticas de usuário (opcional)** Você pode especificar uma ou mais políticas de arquivamento do usuário, cada qual você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um usuário específico. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários aos quais você atribui uma política de usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> Se você usa a integração do Exchange para armazenar dados de arquivamento no Microsoft Exchange, o Exchange Policies controla o arquivamento para usuários hospedados no Exchange. Para habilitar o arquivamento para esses usuários, a caixa de correio do usuário deve ser colocada no bloqueio in-loco. 
  
Para definir as configurações de uma política de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada política de arquivamento exige um nome. O nome é determinado pelo tipo de política que você está adicionando ou editando:
    
  - **Política global** O nome padrão é global. É possível alterá-lo para um nome mais descritivo. Por exemplo, Contoso North American Organization.
    
  - **Política do site** Os sites listados nesta caixa de diálogo incluem todos os sites disponíveis na sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Data Center Redmond.
    
  - **Política de usuário** Especifique um nome apropriado, como o nome de um usuário específico ou o nome de um grupo de usuários ou equipe em sua organização. Por exemplo, Departamento jurídico.
    
- **Descrição** Isso é opcional. Use para fornecer detalhes adicionais, como o escopo ou uso da política. Por exemplo, Coordenação com os departamentos jurídicos de outros sites.
    
- **Arquivar comunicações internas** Marque esta caixa de seleção para habilitar o arquivamento de comunicações em sua rede interna. Por padrão, isso não está habilitado em qualquer política.
    
- **Arquivar comunicações externas** Marque esta caixa de seleção para habilitar o arquivamento de comunicações que incluem usuários externos, como usuários remotos (incluindo usuários anônimos e de PIC) e parceiros federados. Por padrão, isso não está habilitado em qualquer política.
    
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração com o Exchange, consulte [planejar o arquivamento no Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [implantar o arquivamento para o Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [gerenciar o arquivamento no Skype for Business Servidor](../../../manage/archiving/archiving.md).

