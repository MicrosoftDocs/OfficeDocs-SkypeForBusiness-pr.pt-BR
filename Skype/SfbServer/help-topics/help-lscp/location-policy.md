---
title: Política de Local
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: cfdff82c16aa4a9430bf8923cddd28bf26dad85a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840293"
---
# <a name="location-policy"></a>Política de Local

As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.

As políticas de local incluem a política global e, como opção, uma ou mais políticas de site e de usuário:

- **Política global:** A política global é criada por padrão. É possível editar a política global, mas não é possível exclui-la. Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.

- **Políticas de site (opcional):** Você pode criar uma ou mais políticas de local de site, cada uma delas se aplica a um site específico. As políticas de site substituem a política global.

- **Políticas de usuário (opcional):** Você pode criar uma ou mais políticas de localização de usuário, cada uma delas se aplica a um usuário ou grupo específico de usuários. As políticas de usuário substituem a política global e as políticas de site.

> [!NOTE]
> Também é possível atribuir políticas de local a sites de rede, que são grupos de sub-redes. As políticas de local atribuídas a sites de rede têm precedência sobre todas as outras políticas de usuário. Para obter detalhes sobre como atribuir políticas de local a sites de rede usando cmdlets, consulte [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obter detalhes sobre como usar Skype for Business Server Painel de Controle para atribuir uma política de local a um site de rede, consulte [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).

A página **Política de Local** exibe uma lista de todas as políticas de local definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Política de Local**:

- Criar uma nova política de local de site ou uma política de local de usuário

- Alterar a política global ou uma política de site existente ou política de usuário

- Excluir uma política de site ou de usuário

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia uma nova política de local do site ou uma política de localização do usuário.

- **Editar** Abre a política de local selecionada para editá-la, seleciona todas as políticas de local na lista ou exclui a política de site ou política de usuário selecionada.

    > [!NOTE]
    > Para a política global, **Excluir** redefine as configurações para os valores padrão.

- **Atualizar** Atualiza a lista de políticas de local.

A lista a seguir descreve os campos na página.

- **Nome** Identifica a política de local.

- **Escopo** Identifica o escopo da política de local: global, site ou usuário.

- **E9-1-1** Verificado se os usuários atribuídos a essa política de local estão habilitados para E9-1-1.

- **Local** Especifica se os usuários serão ou não solicitados a inserir informações de local quando seu cliente se registrar com o Skype for Business Server em um novo local e se eles verão um aviso de isenção de responsabilidade se descartarem o prompt sem inserir informações de local.

- **Uso de PSTN** Especifica o uso de PSTN (rede telefônica pública comutado) que é usado para determinar a rota de voz usada para rotear chamadas de emergência de clientes que usam esse perfil.

- **Número E9-1-1** Especifica o número discado para chegar aos serviços de emergência.

- **Máscara E9-1-1** Especifica um número que um usuário disca que é convertido no número de discagem de emergência.

Para obter detalhes Enterprise Voice recursos e recursos de serviço de emergência, consulte [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) na documentação planejamento. Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) na documentação Operações.