---
title: Política de Local
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: a7528ea173d03714a8dc20c474d4e1f3d74a5bc2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245080"
---
# <a name="location-policy"></a>Política de Local

As políticas de local determinam se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.

As políticas de local incluem a política global e, como opção, uma ou mais políticas de site e de usuário:

- **Política global:** A política global criada por padrão. É possível editar a política global, mas não é possível excluí-la. Se você tentar remover a política global, todas as configurações serão redefinidas para os valores padrão.

- **(Opcionais) de políticas de site:** Você pode criar políticas de local site um ou mais, cada um deles se aplica a um site específico. As políticas de site substituem a política global.

- **Políticas de usuário (opcionais):** Você pode criar políticas de local usuário um ou mais, cada um deles se aplica a um usuário específico ou grupo de usuários. As políticas de usuário substituem a política global e as políticas de site.

> [!NOTE]
> Também é possível atribuir políticas de local a sites de rede, que são grupos de sub-redes. As políticas de local atribuídas a sites de rede têm precedência sobre todas as outras políticas de usuário. Para obter detalhes sobre como atribuir políticas de local aos sites de rede usando cmdlets, consulte [Adicionar uma política de local em um site de rede no Skype para Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obter detalhes sobre como usar o Skype para painel de controle do Business Server para atribuir uma política de local a um site de rede, consulte [Configurando Sites de rede](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

A página  **Política de Local** exibe uma lista de todas as políticas de local definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página  **Política de Local**:

- Criar uma nova política de local de site ou uma política de local de usuário

- Alterar a política global ou uma política de site existente ou política de usuário

- Excluir uma política de site ou de usuário

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia uma nova política de local de site ou política de local do usuário.

- **Editar** Abre a política de localização selecionada para editá-la, seleciona todas as políticas de local na lista ou exclui a política de site selecionado ou usuário.

    > [!NOTE]
    > Para a política global, **Excluir** redefine as configurações para os valores padrão.

- **Atualizar** Atualiza a lista de políticas de local.

A lista a seguir descreve os campos na página.

- **Nome** Identifica a diretiva de local.

- **Escopo** Identifica o escopo da política de local: global, site ou usuário.

- **E9-1-1** Verificado se os usuários atribuídos a essa política de local estão habilitados para E9-1-1.

- **Local** Especifica se é ou não os usuários são solicitados a digitar informações de localização quando seu cliente registra com Skype para Business Server em um novo local e se eles verão um aviso de isenção se recusar o aviso, sem digitar informações de local.

- **Uso da PSTN** Especifica o uso PSTN (rede) telefônica comutada pública que é usado para determinar a rota de voz usada para rotear chamadas de emergência de clientes usando esse perfil.

- **Número de E9-1-1** Especifica o número discado para acessar os serviços de emergências.

- **Máscara de E9-1-1** Especifica um número discado pelo usuário que é convertido no número de discagem de emergência.

Para obter detalhes sobre os recursos de serviço de emergência do Enterprise Voice e recursos, consulte [Visão geral do E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com políticas de localização, consulte [Configurando a política de local](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação operações.


