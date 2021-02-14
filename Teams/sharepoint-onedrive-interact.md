---
title: Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Interação do SharePoint Online & OneDrive for Business com o Teams; armazenamento de arquivos de chat particular & interação entre equipe, canal padrão, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff18a0645f81d1892e246ee7432d58a1c728f3ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757776"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams

> [!Tip]
> Assista à seguinte sessão para saber como as equipes interagem com o Azure Active Directory (AAD), o Microsoft 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [Fundamentos do Microsoft Teams](https://aka.ms/teams-foundations)

Cada equipe no Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal padrão em uma equipe obtém uma pasta dentro da biblioteca de documentos do site de equipe padrão. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams. Para ver o impacto da alteração de um endereço de site no SharePoint, leia [Alterar um endereço de site.](https://docs.microsoft.com/sharepoint/change-site-address)

> [!NOTE]
> Este artigo se aplica somente aos canais padrão. A arquitetura para canais privados é diferente dos canais padrão. Cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai. Para saber mais, consulte [Canais privados no Microsoft Teams.](private-channels.md)

Arquivos de chat particular são armazenados na pasta do OneDrive for Business do remetente, e as permissões são concedidas automaticamente a todos os participantes como parte do processo de compartilhamento de arquivos.

Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Microsoft 365 ou Office 365. O compartilhamento de arquivos continuará a funcionar em canais padrão, mas os usuários não poderão compartilhar arquivos em chats sem o armazenamento do OneDrive for Business no Microsoft 365 ou no Office 365.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. 

> [!NOTE]
> A integração com o SharePoint local não tem suporte no momento para o Microsoft Teams.

A seguir, é possível ver o exemplo de relações entre equipe, canal padrão e biblioteca de documentos.

É criado um site SharePoint para cada equipe e a pasta **Documentos compartilhados** é a pasta padrão criada para cada uma das equipes. Cada canal padrão, incluindo **o canal Geral** (o canal padrão para cada equipe) tem uma pasta em Documentos **Compartilhados.**

![Diagrama de pastas documentos compartilhados no SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> No momento, não é possível substituir o site e a biblioteca de documentos padrão do SharePoint por outros. Recebemos o feedback de que isso seria interessante e estamos considerando a ideia. Confira o [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap) ou o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar sempre informado sobre os recursos futuros.

> [!TIP]
> Para adicionar uma guia à sua equipe que vincula a uma página de site existente do SharePoint ou à biblioteca de documentos existente do SharePoint:
> 1. Selecione o sinal de mais ao lado das guias.
> 2. Selecione o **SharePoint para** uma página de site existente do SharePoint **ou** Biblioteca de Documentos para uma biblioteca de documentos existente.
> 3. Selecione a página ou biblioteca de documentos apropriada.

Para cada usuário, a pasta **Arquivos de bate-papo do Microsoft Teams** do OneDrive é utilizada para armazenar todos os arquivos compartilhados em bate-papos privados com outros usuários (1:1 ou 1:muitos), com as permissões configuradas automaticamente para restringir o acesso somente para o usuário pretendido.

![Diagrama da pasta do OneDrive chamada Arquivos de Chat do Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Observe que, para equipes públicas, o site de equipe do SharePoint é provisionado com acesso "Todos exceto usuários externos". A equipe pública não é exibida no Teams para pessoas que não são membros dessa equipe. No entanto, eles podem acessar o conteúdo no site de equipe do SharePoint usando a URL do site de equipe do SharePoint. 

## <a name="channel-files-tab"></a>Guia Arquivos de Canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

A **guia** Arquivos no Teams se assemelha muito ao exibição de documentos do SharePoint. Na guia **Arquivos,** os usuários podem:

- Veja opções adicionais no menu **Novo** arquivo.
- Sincronize arquivos com a unidade local.
- No menu **Todos os Documentos,** alternar do **exibição** lista para **a lista Compacta** para o **exibição Blocos.**
- Identifique arquivos que precisam de atenção ou que tenham malware.
- Veja imediatamente se um arquivo é somente leitura ou check-out.
- Fazer check-out e check-in de arquivos.
- Fixe,pine e altere a ordem de classificação dos arquivos.
- Identificar quais arquivos precisam de metadados
- Escolha entre muitas outras opções de filtro.
- Agrupar arquivos com base nos títulos de colunas.
- Modifique as configurações de coluna (mover para a esquerda ou para a direita, ocultar) e a largura da coluna.

## <a name="default-link-type-setting"></a>Configuração de tipo de link padrão

O SharePoint e o OneDrive têm uma configuração de administrador para especificar o tipo de link padrão para links criados para um arquivo. O Teams está adotando essa mesma abordagem reutilando as configurações que o administrador define para o SharePoint e o OneDrive. Mais detalhes sobre essa abordagem são descritos em Alterar o tipo de link padrão [quando os usuários receberem links para compartilhamento.](https://docs.microsoft.com/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>Mais informações

Para saber mais sobre como o SharePoint funciona com o Teams, confira o SharePoint e o [Teams: melhor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Para saber mais sobre a experiência de convidado no Teams, leia como é a [experiência do convidado.](guest-experience.md)

