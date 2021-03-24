---
title: Gerenciar políticas de mensagens no Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre políticas de Mensagens e como elas podem ser usadas para controlar mensagens de chat no Teams.
ms.openlocfilehash: f760fdf196bdeecf14e432445e619c968f66c081
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096115"
---
# <a name="manage-messaging-policies-in-teams"></a>Gerenciar políticas de mensagens no Teams

<!--- Add zone marker here--->

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e canal estão disponíveis para usuários [(proprietários](assign-roles-permissions.md) e membros) no Microsoft Teams. Você pode usar a política global (padrão em toda a organização) criada automaticamente ou criar e atribuir políticas de mensagens personalizadas.

Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Você pode editar as configurações na política global ou criar e atribuir uma ou mais políticas personalizadas para ativar ou desativar os recursos que você deseja.

## <a name="create-a-custom-messaging-policy"></a>Criar uma política de mensagens personalizada

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **Políticas de mensagens.**
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Escolha as configurações que deseja.
5. Clique em **Salvar**.

Por exemplo, digamos que você queira garantir que as mensagens enviadas não sejam excluídas ou alteradas. Crie uma nova política personalizada chamada "Reter mensagens enviadas" e desativar as seguintes configurações:

- Os proprietários podem excluir as mensagens enviadas
- Os usuários podem excluir as mensagens enviadas
- Os usuários podem editar as mensagens enviadas

Em seguida, atribua a política aos usuários.

## <a name="edit-a-messaging-policy"></a>Editar uma política de mensagens

Você pode editar a política global e as políticas personalizadas que criar. 

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **Políticas de mensagens.**
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. A partir daqui, faça as alterações desejadas.
4. Clique em **Salvar**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Atribuir uma política de mensagens personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Um usuário só pode ter uma política de mensagem atribuída por vez.

> [!NOTE]
> Você não pode excluir uma política se usuários estiverem atribuídos a ela. Primeiro, você deve atribuir uma política diferente a todos os usuários afetados. em seguida, é possível excluir a política original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configurações da política de mensagens

Aqui estão as configurações de política de mensagens que você pode configurar.

- **Os proprietários podem excluir as mensagens enviadas**  Use essa configuração para permitir que os proprietários excluam mensagens que os usuários enviaram por chat.
- **Os usuários podem excluir as mensagens enviadas** Use essa configuração para permitir que os usuários excluam mensagens que eles enviaram por chat.
- **Os usuários podem editar as mensagens enviadas** Use essa configuração para permitir que os usuários editem mensagens que eles enviaram por chat.
- **Confirmações de leitura** Os recibos de leitura permitem que o remetente de uma mensagem de chat seja notificado quando a mensagem foi lida pelo destinatário em chats individuais e em grupo de 20 pessoas ou menos. Os recibos de leitura de mensagens realizam a remoção sem ter a certeza se uma mensagem foi lida e melhoram a comunicação da equipe. Observe que as confirmações de leitura não são capturadas nos relatórios de descoberta eletrônica.  
    - **Controlado pelo usuário** Isso significa que os usuários decidem se desejam ATIVAR ou DESATIVAR os recibos de leitura. A configuração padrão dentro do aplicativo está ATIVA. Os usuários podem DESATIVÁ-LA.
    - **Ativado para todos** Isso significa que todos os locatários terão o recurso ATIVADO, sem opção para desativá-lo. Lembre-se de que, ao usar a configuração **Ativado para todos**, a única maneira de definir recibos para todos os locatários é ter apenas uma política de mensagens para todos os locatários (a política padrão denominada "Global - para toda a organização padrão") ou fazer com que todas as políticas de mensagens no locatário usem as mesmas configurações para recibos. O recurso de confirmações de leitura é mais eficaz quando o recurso está habilitado como **Ativado para todos**.
    - **Desativado para todos** Isso significa que o recurso está desabilitado e ninguém no locatário tem confirmações de leitura, nem pode habilitá-lo.
<a name="bkchat"> </a>

- **Chat**  Habilite essa configuração se quiser que os usuários da organização possam usar o aplicativo do Teams para conversar com outras pessoas.
- **Usar Giphys em conversas**  Se você habilitar essa opção, os usuários poderão incluir Giphys em conversas de chat com outras pessoas. O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy recebe uma classificação de conteúdo. Observe que, além de ativar essa configuração, [](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) você também precisa habilitar Experiências Conectadas Opcionais para permitir Giphys em conversas.
- **Classificação de conteúdo Giphy**
    - **Sem restrições** Isso significa que os usuários poderão inserir qualquer Giphy em chats independentemente da classificação de conteúdo.
    - **Moderado**  Isso significa que seus usuários poderão inserir Giphys em chats, mas o conteúdo adulto será moderadamente restringido.
    - **Estrito**  Isso significa que seus usuários poderão inserir Giphys em chats, mas o conteúdo adulto será estritamente restringido.
- **Usar memes em conversas** Se você habilitar essa opção, os usuários poderão incluir Memes em conversas de chat com outras pessoas.
- **Usar Figurinhas em conversas** Se você habilitar essa opção, os usuários poderão incluir Figurinhas em conversas de chat com outras pessoas.
- **Permitir visualizações de URLs** Use essa configuração para ativar ou desativar a visualização automática de URLs nas mensagens.
- **Permitir que os usuários traduzam mensagens** Ativar essa configuração para permitir que os usuários traduzam automaticamente as mensagens do Teams no idioma especificado pelas configurações de idioma pessoal do Microsoft 365 ou do Office 365.
- **Permitir leitura avançada na exibição de mensagens** Ative essa configuração para permitir que os usuários exibam mensagens na Leitura Avançada da Microsoft. A Leitura Avançada é uma ferramenta de aprendizagem que fornece uma experiência de leitura em tela inteira para aumentar a legibilidade do texto.
- **Enviar mensagens urgentes usando notificações de prioridade** Se você ativar isso, os usuários poderão enviar mensagens usando [notificações de prioridade](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). As notificações de prioridade notificam os usuários a cada 2 minutos  por um período de 20 minutos ou até que as mensagens marcadas como urgentes sejam escolhidas e lidas pelo destinatário, maximizando a probabilidade de que a mensagem seja acionada em tempo hábil.
- **Criação de mensagens de áudio** 
  > [!Important]
  > As mensagens de áudio não são capturadas no relatório de Descobertas E.
    - **Permitido em chats e canais** Isso significa que os usuários podem deixar mensagens de áudio nos chats e nos canais.
    - **Permitido em apenas chats** Isso significa que os usuários podem deixar mensagens de áudio nos chats, mas nos canais.
    - **Desabilitado** Isso significa que os usuários não podem criar mensagens de áudio em chats ou canais.  
- **Em dispositivos móveis, exibir canais favoritos acima dos chats recentes** Habilite essa configuração para mover canais favoritos para a parte superior da tela de um dispositivo móvel de modo que o usuário não precise rolar para encontrá-los.
- **Permitir que um usuário remova usuários de um chat em grupo** Habilite essa configuração para permitir que um usuário remova outros usuários de um chat em grupo. Esse recurso permite que você continue um chat com um grupo menor de pessoas sem perder o histórico do chat.
- **Habilitar respostas sugeridas**  Ative essa configuração para habilitar respostas sugeridas para mensagens de chat.

> [!NOTE]
> Algumas dessas configurações, como o Giphys, também podem ser configuradas no nível da equipe pelos proprietários da equipe e no nível do canal privado pelos proprietários do canal privado.

### <a name="related-topics"></a>Tópicos relacionados

- [Atribua políticas a seus usuários no Teams](assign-policies.md)
- [Atribuir proprietários de equipe e membros no Microsoft Teams](assign-roles-permissions.md)