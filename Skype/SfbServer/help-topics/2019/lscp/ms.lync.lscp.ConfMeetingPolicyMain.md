---
title: Política de Conferência
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: A política de conferência define os recursos e capacidades disponíveis aos usuários durante uma conferência (também conhecida como reunião).
ms.openlocfilehash: 885efa5a8f172106939517d44431ded71fbc5e24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767069"
---
# <a name="conferencing-policy"></a>Política de Conferência

A política de conferência define os recursos disponibilizados aos usuários durante uma conferência (também conhecida como reunião).

As políticas de conferência incluem a política global e, como opção, uma ou mais políticas de site e de usuário:

- **Política global:** A política global é criada por padrão. É possível editar a política global, mas não é possível exclui-la. Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.

- **Políticas de site (opcional):** Você pode criar uma ou mais políticas de conferência de site, cada uma delas se aplica a um site específico. As políticas de site substituem a política global.

- **Políticas de usuário (opcional):** Você pode criar uma ou mais políticas de conferência de usuário, cada uma delas se aplica a um usuário ou grupo específico de usuários. As políticas de usuário substituem a política global e as políticas de site.

A página **Política de Conferência** exibe uma lista de todas as políticas de conferência definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Política de Local**:

- Criar uma nova política de conferência de site ou uma política de conferência de usuário

- Alterar a política global ou uma política de site existente ou política de usuário

- Excluir uma política de site ou de usuário

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia uma nova política de conferência de site ou política de conferência do usuário.

- **Editar** Abre a política de conferência selecionada para editá-la, seleciona todas as políticas de conferência na lista ou exclui a política de site ou política de usuário selecionada.

    > [!NOTE]
    > Para a política global, **Excluir** redefine as configurações para os valores padrão.

- **Atualizar** Atualiza a lista de políticas de conferência.

A lista a seguir descreve os campos na página.

- **Nome** Identifica a política de conferência.

- **Escopo** Identifica o escopo da política de conferência: global, site ou usuário.

- **Colaboração de dados** Verificado se a política de conferência especifica que a colaboração de dados é permitida em conferências.

- **Compartilhamento de aplicativos** Verificado se a política de conferência especifica que o compartilhamento de aplicativos é permitido em conferências.

- **Áudio** Verificado se a política de conferência especifica que o áudio é permitido em conferências.

- **Vídeo** Verificado se a política de conferência especifica que o vídeo é permitido em conferências.

- **PSTN** Verificado se a política de conferência especifica que a conferência discagem PSTN é permitida.

- **Gravação** Verificado se a política de conferência especifica que a gravação é permitida em conferências.

Para obter detalhes sobre recursos de conferência, consulte [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) na documentação Planejamento. Para obter detalhes sobre como trabalhar com políticas de conferência, consulte [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) na documentação Operações.