---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 869adf9401e3704cc78de5f646b0b9e676e8efe9
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295482"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
=============================================================================

> [!Tip]
> Assista a sessão a seguir para saber como equipes interage com o Windows Azure Active Directory (AAD), grupos do Office 365, Exchange, SharePoint e OneDrive for Business: [Fundamentos das equipes da Microsoft](https://aka.ms/teams-foundations)

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.

Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365. Compartilhamento de arquivos continuarão a funcionar no canais, mas os usuários não poderão compartilhar arquivos em bate-papos sem OneDrive para armazenamento de negócios no Office 365.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. 

> [!NOTE]
> Integração com o Sharepoint local não é suportada for Microsoft Teams neste momento.

A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.

É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes. Todos os canais, inclusive o canal **Geral** (o canal padrão de cada equipe), têm uma pasta em **Documentos Compartilhados**.

![Diagrama das pastas de documentos selecionados no SharePoint Online para uma equipe e seus canais no Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros. Recebemos o feedback de que isso seria interessante e estamos considerando a ideia. Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.

> [!TIP]
> Para adicionar uma guia para a sua equipe que links para um SharePoint existente de site ou biblioteca de documentos no seu SharePoint existente:
> 1. Selecione o sinal de adição ao lado de guias.
> 2. Selecione o **site**.
> 3. Digite um nome e digite a URL do seu SharePoint site ou biblioteca de documentos.

Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.

![Diagrama da pasta do OneDrive, nomeada como Arquivos de Bate-papo do Microsoft Teams para o bate-papo de cada usuário.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
