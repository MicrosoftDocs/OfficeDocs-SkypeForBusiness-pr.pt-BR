---
title: Número de Telefone Não Atribuído
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: fa7fd55f0c0fae22643d0dde66cae32c2610bdcd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834519"
---
# <a name="unassigned-phone-number"></a>Número de Telefone Não Atribuído

> [!NOTE]
> Exchange A UM permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com Exchange 2013 ou Exchange 2016. Devido às alterações no suporte no Exchange 2019, Exchange integração de UM está sendo desalmada em favor dos recursos Caixa postal na Nuvem e Cloud Atendedor Automático.

Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.

O modo como você configura a tabela de números não atribuídos depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação dos dois tipos de números. A tabela de números não atribuídos pode incluir números atribuídos e não atribuídos, mas é invocada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuídos, será possível especificar a ação que ocorre quando alguém deixa sua organização, sem precisar reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao consumidor, poderá incluir o número antigo do serviço de atendimento ao consumidor na tabela e atribuí-lo a um anúncio que fornece o novo número.

> [!IMPORTANT]
> Antes de configurar a tabela de números atribuídos, você já precisa ter definido um ou mais anúncios ou configurar um Atendedor Automático do UM do Exchange.

A página **Número Não Atribuído** exibe uma lista de números não atribuídos definidos para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Número Não Atribuído**:

- Criar um novo intervalo de números não atribuídos

- Alterar um intervalo de números não atribuídos existente

- Excluir um intervalo de números não atribuídos

- Alterar a ordem dos intervalos de números não atribuídos a fim de determinar qual ação deve ser aplicada primeiro a uma chamada de entrada que corresponde a um número não atribuído.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia um novo intervalo de números não atribuídos.

- **Editar** Abre o intervalo de números não atribuídos selecionado para edição, seleciona todos os intervalos de números não atribuídos na lista ou exclui o intervalo de números não atribuídos selecionado.

- **Mover para cima** Move o intervalo de números não atribuídos selecionado para cima na lista para que Skype for Business Server encontre-o mais cedo e aplique a ação especificada antes de aplicar ações especificadas para outros intervalos na lista.

    > [!NOTE]
    > Skype for Business Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído. Por exemplo, se você tiver um intervalo que especifica uma ação de última instância, certifique-se de que o intervalo esteja no final da lista.

- **Mover para baixo** Move o intervalo de números não atribuídos selecionado para baixo na lista.

- **Commit all** Salva todas as alterações feitas em intervalos de números não atribuídos.

    > [!IMPORTANT]
    > Esse comando salva todas as alterações feitas na página **Novo Número Não Atribuído** e na página **Editar Número Não Atribuído**.

- **Atualizar** Atualiza a lista de intervalos de números não atribuídos.

A lista a seguir descreve os campos na página.

- **Nome** O nome exclusivo que identifica o intervalo de números não atribuídos.

- **Estado** Mostra quais intervalos de números foram salvos no banco de dados e quais não foram.

- **Intervalo inicial** O número inicial do intervalo de números não atribuídos.

- **Intervalo final** O número final do intervalo de números não atribuídos.

- **Destination** A ID de serviço do serviço application que hospeda o aplicativo Comunicado que tratará de chamadas de entrada para esse intervalo de números não atribuídos.

- **Comunicado** O comunicado que será tocado para esse intervalo de números não atribuídos.

Para obter detalhes sobre recursos e recursos do Comunicado, consulte [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação Planejamento. Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) na documentação Operações.