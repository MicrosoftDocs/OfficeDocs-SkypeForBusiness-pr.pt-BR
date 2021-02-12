---
title: Política de Local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: 948fb5cb6a5457b512af3fc7d230adf27c304bd2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803951"
---
# <a name="location-policy"></a>Política de Local

As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.

As políticas de local incluem a política global e, como opção, uma ou mais políticas de site e de usuário:

- **Política global:** A política global é criada por padrão. É possível editar a política global, mas não é possível exclui-la. Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.

- **Políticas de site (opcional):** Você pode criar uma ou mais políticas de local de site, cada uma delas se aplicando a um site específico. As políticas de site substituem a política global.

- **Políticas de usuário (opcional):** Você pode criar uma ou mais políticas de local de usuário, cada uma delas se aplicando a um usuário ou grupo de usuários específico. As políticas de usuário substituem a política global e as políticas de site.

> [!NOTE]
> Também é possível atribuir políticas de local a sites de rede, que são grupos de sub-redes. As políticas de local atribuídas a sites de rede têm precedência sobre todas as outras políticas de usuário. Para obter detalhes sobre como atribuir políticas de local a sites de rede usando cmdlets, consulte Adicionar uma política de local a um site de rede no [Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md) Para obter detalhes sobre como usar o Painel de Controle do Skype for Business Server para atribuir uma política de local a um site de rede, consulte [Configurando sites de rede.](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)

A página **Política de Local** exibe uma lista de todas as políticas de local definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Política de Local**:

- Criar uma nova política de local de site ou uma política de local de usuário

- Alterar a política global ou uma política de site existente ou política de usuário

- Excluir uma política de site ou de usuário

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia uma nova política de local de site ou uma política de local de usuário.

- **Editar** Abre a política de local selecionada para editá-la, seleciona todas as políticas de local na lista ou exclui a política de site ou política de usuário selecionada.

    > [!NOTE]
    > Para a política global, **Excluir** redefine as configurações para os valores padrão.

- **Atualizar** Atualiza a lista de políticas de local.

A lista a seguir descreve os campos na página.

- **Nome** Identifica a política de local.

- **Escopo** Identifica o escopo da política de local: global, site ou usuário.

- **E9-1-1** Verifica se os usuários atribuídos a essa política de local estão habilitados para E9-1-1.

- **Localização** Especifica se os usuários serão solicitados ou não a inserir informações de local quando seus clientes se registram no Skype for Business Server em um novo local e se veem um aviso de isenção de responsabilidade se descartarem a solicitação sem inserir informações de local.

- **Uso de PSTN** Especifica o uso da PSTN (Rede Telefônica Pública Comutado) usada para determinar a rota de voz usada para rotear chamadas de emergência de clientes que usam esse perfil.

- **Número de E9-1-1** Especifica o número discado para alcançar os serviços de emergência.

- **Máscara de E9-1-1** Especifica um número que um usuário disca e que é convertido no número de discagem de emergência.

Para obter detalhes sobre os recursos do serviço de emergência do Enterprise Voice, consulte [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de Planejamento. Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação Operações.


