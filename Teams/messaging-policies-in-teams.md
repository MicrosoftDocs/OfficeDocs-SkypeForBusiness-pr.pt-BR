---
title: Gerenciar políticas de mensagens no Teams
ms.author: mabond
author: mkbond007
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Saiba mais sobre as políticas de mensagens e como elas podem ser usadas para controlar as mensagens de chat no Teams.
ms.openlocfilehash: 1975262b6fdd404d9314c3644ebba79b6cb5bd9a
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396512"
---
# <a name="manage-messaging-policies-in-teams"></a>Gerenciar políticas de mensagens no Teams

<!--- Add zone marker here--->

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e canal estão disponíveis para os usuários (proprietários e membros [)](assign-roles-permissions.md) no Microsoft Teams. Você pode usar a política global (padrão de toda a organização) criada automaticamente ou criar e atribuir políticas de mensagens personalizadas.

Os usuários em sua organização receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Edite as configurações na política global ou crie e atribua uma ou mais políticas personalizadas para ativar ou desativar os recursos desejados.

> [!NOTE]
> Para garantir a sincronização após uma alteração de política, uma reinicialização pode ser necessária para determinadas instâncias. 

## <a name="create-a-custom-messaging-policy"></a>Criar uma política de mensagens personalizada

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para **políticas de mensagens**.
2. Selecione **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Escolha as configurações que deseja.
5. Selecione **Salvar**.

Por exemplo, você deseja garantir que as mensagens enviadas não sejam excluídas ou alteradas. Crie uma nova política personalizada chamada "Reter mensagens enviadas" e desative as seguintes configurações:

- Os proprietários podem excluir as mensagens enviadas
- Os usuários podem excluir as mensagens enviadas
- Os usuários podem editar as mensagens enviadas

Em seguida, atribua a política aos usuários.

## <a name="edit-a-messaging-policy"></a>Editar uma política de mensagens

Você pode editar a política global e as políticas personalizadas que criar.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para **políticas de mensagens**.
2. Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.
3. A partir daqui, faça as alterações desejadas.
4. Selecione **Salvar**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Atribuir uma política de mensagens personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Um usuário só pode ter uma política de mensagem atribuída por vez.

> [!NOTE]
> Você não pode excluir uma política se usuários estiverem atribuídos a ela. Primeiro, você deve atribuir uma política diferente a todos os usuários afetados. em seguida, é possível excluir a política original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configurações da política de mensagens

Aqui estão as configurações de política de mensagens que você pode definir.

- **Os proprietários podem excluir mensagens enviadas**  Use essa configuração para permitir que os proprietários excluam mensagens de canal ou postagens que os usuários enviaram.
- **Excluir mensagens enviadas** Use essa configuração para permitir que os usuários excluam mensagens enviadas no chat.
- **Excluir chat** Use essa configuração para permitir que os usuários excluam mensagens enviadas no chat.
- **Editar mensagens enviadas** Use essa configuração para permitir que os usuários editem as mensagens enviadas no chat.
- **Confirmações de leitura** As confirmações de leitura permitem que o remetente de uma mensagem de chat seja notificado quando sua mensagem foi lida pelo destinatário em 1:1 e chats em grupo de 20 pessoas ou menos. Os recibos de leitura de mensagens realizam a remoção sem ter a certeza se uma mensagem foi lida e melhoram a comunicação da equipe. Os recibos de leitura não são capturados nos relatórios de Descoberta Eletrônica.  
    - **Controlado pelo usuário** Isso significa que os usuários decidem se desejam ATIVAR ou DESATIVAR os recibos de leitura. A configuração padrão dentro do aplicativo está ATIVA. Os usuários podem DESATIVÁ-LA.
    - **Ativado para todos** Isso significa que todos no locatário terão o recurso ATIVADO sem opção para desativá-lo. Ao usar a  configuração Ativado para todos, a única maneira de definir recibos para todo o locatário é ter apenas uma política de mensagens para todo o locatário (a política padrão chamada "Global (Padrão em toda a organização)") ou fazer com que todas as políticas de mensagens no locatário usem as mesmas configurações para recibos. O recurso de confirmação de leitura é mais eficaz quando o recurso está habilitado como **Ativado para todos**.
    - **Desativado para todos** Isso significa que o recurso está desabilitado e ninguém no locatário tem recibos de leitura nem pode ativá-lo.
<a name="bkchat"> </a>

- **Chat**  Habilite essa configuração se quiser que os usuários da organização possam usar o aplicativo do Teams para conversar com outras pessoas.
- *Usar Giphy em conversas* Se* você ativar o Giphys, os usuários poderão incluir Giphys em conversas de chat com outras pessoas. O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy recebe uma classificação de conteúdo. Além de ativar essa configuração, você precisa habilitar [Experiências](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) Conectadas Opcionais para permitir Giphys em conversas.
- **Classificação de conteúdo Giphy**
  - **Sem restrições** Isso significa que os usuários poderão inserir qualquer Giphy em chats independentemente da classificação de conteúdo.
  - **Moderado**  Isso significa que seus usuários poderão inserir Giphys em chats, mas o conteúdo adulto será moderadamente restringido.
  - **Estrito**  Isso significa que seus usuários poderão inserir Giphys em chats, mas o conteúdo adulto será estritamente restringido.
- **Memes em conversas** Se você ativar o Memes, os usuários poderão incluir Memes em conversas de chat com outras pessoas.
- **Adesivos em conversas** Se você ativar isso, os usuários poderão incluir Adesivos em conversas de chat com outras pessoas.
- **Visualizações de URL** Use essa configuração para ativar ou desativar a visualização automática de URL em mensagens.
- **Traduzir mensagens** Ative essa configuração para permitir que os usuários traduzam automaticamente as mensagens do Teams para o idioma especificado pelas configurações de idioma pessoal do Microsoft 365 ou Office 365.
- **Leitura avançada para mensagens** Ative essa configuração para permitir que os usuários exibam mensagens no Microsoft Leitura Avançada. A Leitura Avançada é uma ferramenta de aprendizagem que fornece uma experiência de leitura em tela inteira para aumentar a legibilidade do texto.
- **Enviar mensagens urgentes usando notificações de prioridade** Se você ativar isso, os usuários poderão enviar mensagens usando [notificações de prioridade](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). As notificações de prioridade notificam os usuários a cada 2 minutos por 20 minutos ou até que as  mensagens marcadas como urgentes sejam coletadas e lidas pelo destinatário. Esse recurso aumenta a probabilidade de que a mensagem seja acionada em tempo hábil. Não é possível editar uma mensagem urgente depois de enviá-la.
- **Criar mensagens de voz**
  > [!Important]
  > As mensagens de áudio não são capturadas nos relatórios de Descoberta Eletrônica.
  - **Permitido em chats e canais** Isso significa que os usuários podem deixar mensagens de áudio nos chats e nos canais.
  - **Permitido em apenas chats** Isso significa que os usuários podem deixar mensagens de áudio nos chats, mas nos canais.
  - **Não habilitado** Isso significa que os usuários não podem criar mensagens de áudio em chats ou canais.  
- **Em dispositivos móveis, exibir canais favoritos acima dos chats recentes** Habilite essa configuração para mover canais favoritos para a parte superior da tela de um dispositivo móvel de modo que o usuário não precise rolar para encontrá-los.
- **Remover usuários de chats em grupo** Ative essa configuração para permitir que um usuário remova outros usuários de um chat em grupo. Esse recurso permite que você continue um chat com um grupo menor de pessoas sem perder o histórico do chat.
- **Previsões de texto** Ative essa configuração para permitir que um usuário obtenha previsões de texto para mensagens de chat.
- **Respostas sugeridas**  Ative essa configuração para habilitar respostas sugeridas para mensagens de chat.
- **Função de permissão de chat** Use essa configuração para definir a função de chat supervisionada do usuário. Saiba mais sobre [conversas no](supervise-chats-edu.md).
- **Os usuários com permissões completas de chat podem excluir qualquer mensagem** Use essa configuração para permitir que os usuários com permissões completas excluam qualquer mensagem de chat de grupo ou reunião.
- **Mensagens de vídeo** Ative essa configuração se quiser que os usuários em sua organização possam usar o aplicativo Teams para enviar mensagens de vídeo para outras pessoas no Chat.

> [!NOTE]
> Algumas dessas configurações, como o uso do Giphys, também podem ser definidas no nível da equipe pelos proprietários da equipe e no nível do canal privado ou compartilhado pelos proprietários do canal.

### <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas a usuários e grupos no Teams](assign-policies-users-and-groups.md)
- [Atribuir proprietários e membros da equipe no Microsoft Teams](assign-roles-permissions.md)
