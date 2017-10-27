---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: cf971714c1ad3b797c181f982ea8688bf8c73977
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
=============================================================================

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do **remetente** e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.

Se você não possui o SharePoint Online habilitado no seu tenant, os usuários do Microsoft Teams nem sempre poderão compartilhar arquivos no Teams. Os usuários de bate-papo privado também não poderão compartilhar arquivos pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas.

A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.

É criado um site SharePoint para cada equipe e a pasta *Documentos compartilhados* é a pasta padrão criada para cada uma das equipes. Todos os canais, inclusive o canal **Geral**, o canal padrão de cada equipe, têm uma pasta dentro da pasta *Documentos compartilhados*.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Para cada usuário, a pasta *Arquivos de bate-papo do Microsoft Teams* do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
