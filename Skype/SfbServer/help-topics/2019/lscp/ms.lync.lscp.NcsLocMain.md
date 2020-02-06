---
title: Política de Local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: 64ca2bf2f450bcc6de882beddf78173a9f1ee6c4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795502"
---
# <a name="location-policy"></a>Política de Local

As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.

As políticas de local incluem a política global e, como opção, uma ou mais políticas de site e de usuário:

- **Política global:** A política global é criada por padrão. É possível editar a política global, mas não é possível excluí-la. Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.

- **Políticas de site (opcional):** Você pode criar uma ou mais políticas de localização de site, cada uma delas se aplica a um site específico. As políticas de site substituem a política global.

- **Políticas de usuário (opcional):** Você pode criar uma ou mais políticas de localização do usuário, cada uma se aplica a um usuário ou grupo de usuários específico. As políticas de usuário substituem a política global e as políticas de site.

> [!NOTE]
> Também é possível atribuir políticas de local a sites de rede, que são grupos de sub-redes. As políticas de local atribuídas a sites de rede têm precedência sobre todas as outras políticas de usuário. Para obter detalhes sobre como atribuir políticas de localização a sites de rede usando cmdlets, consulte [Adicionar uma política de localização a um site de rede no Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obter detalhes sobre como usar o painel de controle do Skype for Business Server para atribuir uma política de localização a um site de rede, consulte [Configurando sites de rede](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

A página  **Política de Local** exibe uma lista de todas as políticas de local definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página  **Política de Local**:

- Criar uma nova política de local de site ou uma política de local de usuário

- Alterar a política global ou uma política de site existente ou política de usuário

- Excluir uma política de site ou de usuário

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia uma nova política de localização de site ou política de localização de usuário.

- **Editar** Abre a política de localização selecionada para editá-la, seleciona todas as políticas de localização na lista ou exclui a política de site ou a política de usuário selecionada.

    > [!NOTE]
    > Para a política global, **Excluir** redefine as configurações para os valores padrão.

- **Atualização** Atualiza a lista de políticas de localização.

A lista a seguir descreve os campos na página.

- **Nome** Identifica a política de localização.

- **Escopo** Identifica o escopo da política de localização: global, site ou usuário.

- **E9-1-1** Verificado se os usuários atribuiram esta política de localização estão habilitadas para E9-1-1.

- **Local** Especifica se os usuários são solicitados a inserir informações de localização quando o cliente se registra no Skype for Business Server em um novo local e se ele vê uma isenção de isenção de responsabilidade quando ele dispensar o prompt sem inserir informações de localização.

- **Uso de PSTN** Especifica o uso da rede telefônica pública comutada (PSTN) que é usada para determinar a rota de voz usada para direcionar as chamadas de emergência dos clientes que usam esse perfil.

- **Número E9-1-1** Especifica o número discado para acessar serviços de emergência.

- **Máscara E9-1-1** Especifica um número que um usuário discará e que será traduzido para o número de discagem de emergência.

Para obter detalhes sobre os recursos e recursos do serviço de emergência do Enterprise Voice, consulte [visão geral do E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação Operações.


