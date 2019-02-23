---
title: Gerenciar políticas de mensagens
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Saiba mais sobre as políticas de mensagens e como eles podem ser usados para controlar as equipes de mensagens de chat.
ms.openlocfilehash: f1dd0fdae137e0a2a5f0baeb5b7bed08067833bf
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205751"
---
# <a name="what-are-messaging-policies-in-teams"></a>Quais são as políticas de mensagens no Microsoft Teams?

Políticas de mensagens são usadas para controlar quais recursos de mensagens de canal e de bate-papo estão disponíveis para usuários no Microsoft Teams. Você pode usar a política padrão que é criada ou crie uma ou mais políticas de mensagens personalizadas para pessoas da sua organização. Depois de criar uma política, você vai atribuí-lo um usuário ou grupos de usuários em sua organização.

As políticas podem ser facilmente gerenciadas no Centro de administração do Microsoft Teams (http://admin.teams.microsoft.com) log com credenciais de administrador e escolhendo **Políticas de mensagens** no painel de navegação à esquerda. 

![Políticas de mensagens em equipes](media/messaging-policies-image1.png)

Para editar a política existente de mensagens padrão para sua organização, clique na linha **Global (padrão de toda a organização)** e faça suas alterações. Para criar uma nova política personalizada de mensagens, clique em **nova diretiva** e selecione suas configurações. Escolha **Salvar** quando terminar.

![Configurações de diretiva em equipes de mensagens](media/messaging-policies-image2.png)

<!--- Add zone marker here--->

Use as configurações a seguir para alterar a política global de mensagens ou criar uma nova política personalizada:

- **Os proprietários podem excluir as mensagens enviadas**  Use esta configuração para permitir que os proprietários excluir mensagens que os usuários enviada em bate-papo.
- **Os usuários podem excluir as mensagens enviadas** Use esta configuração para permitir que usuários excluir mensagens enviados por eles no bate-papo.
- **Os usuários podem editar as mensagens enviadas** Use esta configuração para permitir aos usuários editar as mensagens enviados por eles no bate-papo.
- **Confirmações de leitura** Use esta configuração para especificar se a notificação de leitura estão usuário controlados, habilitado para todas as pessoas ou desabilitado.
<a name="bkchat"> </a>

- **Bate-papo**  Ative esta configuração se quiser que os usuários em sua organização possam usar o aplicativo de equipes para conversar com outras pessoas.
- **Uso Giphys em conversas**  Se você ativar isso, os usuários podem incluir Giphys em conversas de bate-papo com outras pessoas. Giphy é um banco de dados online e o mecanismo de pesquisa que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy é atribuída uma classificação de conteúdo.
- **Classificação de conteúdo Giphy** 
    - **Sem restrição** Isso significa que os usuários poderão inserir qualquer Giphy em bate-papos independentemente a classificação de conteúdo.
    - **Moderada**  Isso significa que os usuários serão capazes de inserir Giphys em bate-papos, mas serão restritos relativamente de conteúdo para adultos.
    - **Estrito**  Isso significa que os usuários serão capazes de inserir Giphys em bate-papos, mas serão restritos estritamente de conteúdo para adultos.
- **Uso Memes em conversas** Se você ativar isso, os usuários podem incluir Memes em conversas de bate-papo com outras pessoas. 
- **Adesivos de uso em conversas** Se você ativar isso, os usuários podem incluir adesivos em conversas de bate-papo com outras pessoas.
- **Visualizações de URL permitir** Use esta configuração para ativar automática URL pré-visualizar ativada ou desativada nas mensagens.
- **Permitir que os usuários para traduzir mensagens** Ative esta configuração para permitir que os usuários automaticamente traduzir mensagens de equipes para o idioma especificado por suas configurações de idioma pessoal para o Office 365.

Se você tiver criado uma política personalizada de mensagens, ele só será ativo para um usuário se essa diretiva é atribuída a um usuário. Para atribuir uma política personalizada a um usuário no Centro de administração do Microsoft Teams, escolha **usuários** no painel de navegação esquerdo e selecione o usuário que você deseja atribuir a política. Na página do usuário, escolha **Editar** ao lado de **Políticas atribuídas**.

<!--- End zone marker here--->

### <a name="related-topics"></a>Tópicos relacionados
[Políticas de reunião no Teams](meeting-policies-in-teams.md)
