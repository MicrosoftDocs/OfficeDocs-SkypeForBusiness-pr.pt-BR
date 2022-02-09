---
title: Configuração de Reunião
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: As configurações de reunião definem o tipo de conferências (também chamadas de reuniões) que os usuários podem criar e controlar como (ou se) usuários anônimos e usuários de conferência discada podem ingressar nessas conferências. Essas configurações se aplicam apenas às reuniões agendadas. Eles não se aplicam a reuniões ad hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: bdb2dddf5d510ed3024897bc621a4d7def0d88af
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399325"
---
# <a name="meeting-configuration"></a>Configuração de Reunião

As definições de configuração de reunião definem os tipos de conferências (também chamadas de "reuniões") criados pelos usuários e controlam como (ou se) os usuários anônimos e os usuários de conferência discada podem ingressar nessas conferências. Essas configurações se aplicam apenas às reuniões agendadas. Eles não se aplicam a reuniões ad hoc criadas clicando na opção Reunir Agora no cliente.

As configurações de reunião se aplicam no nível global, do site ou do pool:

- **Configuração de reunião global:** A configuração de reunião global é criada por padrão. É possível editar a configuração de reunião global, mas não é possível excluí-la. Se você tentar remover a configuração de reunião global, todas as configurações serão redefinidas para os valores padrão.

- **Configuração de reunião do site (opcional):** Você pode criar uma ou mais configurações de reunião de site, cada uma delas se aplica a um site específico. As configurações de site substituem a configuração global.

- **Configuração de reunião do pool (opcional):** Você pode criar uma ou mais configurações de reunião de pool, cada uma delas se aplica a um pool específico. As configurações de pool substituem a configuração global e as configurações de site.

A página **Configuração de Reunião** exibe uma lista de todas as configurações de reunião definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Configuração de Reunião**:

- Criar uma nova configuração de reunião de site ou configuração de reunião de pool

- Alterar a configuração global ou uma configuração de site ou de pool existente

- Excluir uma configuração de site ou configuração de pool

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia uma nova configuração de reunião de site ou configuração de reunião de pool.

- **Editar** Abre a configuração de reunião selecionada para editá-la, seleciona todas as configurações de reunião na lista ou exclui a configuração de site ou pool selecionado.

    > [!NOTE]
    > Para a configuração de reunião global, **Excluir** redefine as configurações para os valores padrão.

- **Atualizar** Atualiza a lista de configurações de reunião.

A lista a seguir descreve os campos na página.

- **Nome** Identifica a configuração da reunião.

- **Escopo** Identifica o escopo da configuração da reunião: global, site ou pool.

Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) na documentação Operações.