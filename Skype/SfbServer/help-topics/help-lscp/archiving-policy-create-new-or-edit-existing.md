---
title: Política de arquivamento criar novo ou editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Você pode usar as políticas de arquivamento para controlar o arquivamento das comunicações internas e externas em sua implantação para usuários hospedados no Skype para Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:'
ms.openlocfilehash: af8038371cd421b0232ce2df0ba92aa5b079702e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Política de Arquivamento: Criar Nova ou Editar Existente
 
Você pode usar as políticas de arquivamento para controlar o arquivamento das comunicações internas e externas em sua implantação para usuários hospedados no Skype para Business Server. As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de site e de usuário:
  
- **Política global** A política global criada por padrão no Skype todas as implantações de servidor de negócios. É possível editar a política global, mas não é possível excluir essa política. Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.
    
- **Políticas de site (opcionais)** Você pode especificar um ou mais sites as políticas de arquivamento, que cada um dos quais você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um site específico. Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de Arquivamento. É possível editar ou excluir as políticas de site.
    
- **Políticas de usuário (opcionais)** Você pode especificar um ou mais usuários as políticas de arquivamento, que cada um dos quais você pode configurar para habilitar e desabilitar o arquivamento de comunicações internos ou externos para um usuário específico. Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários aos quais você atribui uma política de usuário. É possível editar ou excluir as políticas de usuário.
    
> [!NOTE]
> Se você usar a integração do Exchange para armazenar dados no Microsoft Exchange, em seguida, o Exchange 2013 políticas de arquivamento o controle de arquivamento para usuários hospedados no Exchange 2013. Para habilitar o arquivamento para os usuários, a caixa de correio do usuário deve ser colocada em retenção In-loco. 
  
Para definir as configurações de uma política de Arquivamento nova ou existente, especifique as seguintes opções:
- **Nome** Cada política de arquivamento requer um nome. O nome é determinado pelo tipo de política que você está adicionando ou editando:
    
  - **Política global** O nome padrão é Global. É possível alterá-lo para um nome mais descritivo. Por exemplo, Contoso North American Organization.
    
  - **Política de site** Os sites listados nesta caixa de diálogo incluem todos os sites disponíveis em sua implantação. Clique em um único site para selecioná-lo. Por exemplo, Data Center Redmond.
    
  - **Política de usuário** Especifique um nome apropriado, como o nome de um usuário específico ou o nome de um grupo de usuário ou a equipe em sua organização. Por exemplo, Departamento jurídico.
    
- **Descrição** Isto é opcional. Use para fornecer detalhes adicionais, como o escopo ou uso da política. Por exemplo, Coordenação com os departamentos jurídicos de outros sites.
    
- **Arquivar comunicações internas** Marque esta caixa de seleção para habilitar o arquivamento de comunicações em sua rede interna. Por padrão, isso não está habilitado em qualquer política.
    
- **Comunicações externas de arquivo morto** Marque esta caixa de seleção para habilitar o arquivamento de comunicações que incluem usuários externos, como os usuários remotos, (incluindo a usuários anônimos e configuração de PIC) e parceiros federados. Por padrão, isso não está habilitado em qualquer política.
    
Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração do Exchange, consulte [Planejar para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Gerenciar o arquivamento no Skype para Business 2015 de servidor](../../manage/archiving/archiving.md).

