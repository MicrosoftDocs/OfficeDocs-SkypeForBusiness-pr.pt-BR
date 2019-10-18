---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams, como arquivos de bate-papo provados são armazenados e a relação entre equipe, canal e biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567116"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams

> [!Tip]
> Assista à sessão a seguir para saber como as equipes interagem com o Azure Active Directory (AAD), o Office 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [bases do Microsoft Teams](https://aka.ms/teams-foundations)

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Os arquivos de bate-papo privado ficam armazenados na pasta do OneDrive for Business do remetente e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.

Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365. O compartilhamento de arquivos continuará a funcionar em canais, mas os usuários não poderão compartilhar arquivos em chats sem o armazenamento do OneDrive for Business no Office 365.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. 

> [!NOTE]
> A integração com o SharePoint local não é compatível com o Microsoft Teams no momento.

A seguir, um exemplo das relações entre equipe, canal e biblioteca de documentos.

É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes. Todos os canais, inclusive o canal **Geral** (o canal padrão de cada equipe), têm uma pasta em **Documentos Compartilhados**.

![Diagrama de pastas de documentos compartilhados no SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros. Recebemos o feedback de que isso seria interessante e estamos considerando a ideia. Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.

> [!TIP]
> Para adicionar uma guia à sua equipe que vincula a uma página de site do SharePoint existente ou à biblioteca de documentos do SharePoint existente:
> 1. Selecione o sinal de adição ao lado das guias.
> 2. Selecione o **SharePoint** para uma página de site ou uma **biblioteca de documentos** do SharePoint existente para uma biblioteca de documentos existente.
> 3. Selecione a página ou biblioteca de documentos apropriada.

Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.

![Diagrama da pasta OneDrive chamado arquivos de chat do Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Guia arquivos do canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

A guia **arquivos** em equipes é parecida com o modo de exibição documentos do SharePoint. Na guia **arquivos** , os usuários podem:

- Veja opções adicionais no menu **novo** arquivo.
- Sincronize arquivos com a unidade local.
- No menu **todos os documentos** , alternar do modo de exibição de **lista** para a **lista compacta** para o modo de exibição de **blocos** .
- Identifique os arquivos que precisam de atenção ou de malware.
- Veja imediatamente se um arquivo é somente leitura ou com check-out.
- Fazer check-out e check-in de arquivos.
- Fixar, Desafixar e alterar a ordem de classificação dos arquivos.
- Identificar quais arquivos precisam de metadados
- Escolha entre várias opções de filtro.
- Agrupar arquivos com base em títulos de coluna.
- Modifique as configurações de coluna (mover para a esquerda ou direita, ocultar) e largura da coluna.

## <a name="default-link-type-setting"></a>Configuração do tipo de link padrão

O SharePoint e o OneDrive têm uma configuração de administrador para especificar o tipo de link padrão para links que são criados para um arquivo. O Microsoft Teams está adotando essa mesma abordagem reutilizando as configurações que o administrador define para o SharePoint e o OneDrive. Mais detalhes sobre essa abordagem são descritos em [alterar o tipo de link padrão quando os usuários recebem links para compartilhamento](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Mais informações

Para obter mais informações sobre como o SharePoint funciona com o Microsoft Teams, consulte [SharePoint e Teams: melhor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Para saber mais sobre a experiência de convidado no Microsoft Teams, leia [o que a experiência de convidado é curtir](guest-experience.md).

