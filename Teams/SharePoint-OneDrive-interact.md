---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: "Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef80cf3f52e9a661bca8694bd679ba18dd4cf04e
ms.sourcegitcommit: 9094c87dec3f8d7d05c7e879d357a6ed428d7cdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
=============================================================================

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.

Se o SharePoint Online não está habilitado em seu locatário, os usuários do Microsoft Teams não podem compartilhar arquivos em equipes. Os usuários no chat privado também não podem compartilhar arquivos, pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.

A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.

É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes. Todos os canais, inclusive o canal **Geral** (o canal padrão de cada equipe), têm uma pasta em **Documentos Compartilhados**.

![Diagrama das pastas de documentos selecionados no SharePoint Online para uma equipe e seus canais no Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros. Recebemos o feedback de que isso seria interessante e estamos considerando a ideia. Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.

Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.

![Diagrama da pasta do OneDrive, nomeada como Arquivos de Bate-papo do Microsoft Teams para o bate-papo de cada usuário.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
