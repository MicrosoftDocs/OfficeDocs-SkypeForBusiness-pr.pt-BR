---
title: Experiência do teams em um ambiente compatível com várias regiões do Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Neste artigo, você aprenderá a usar o Microsoft Teams em um ambiente compatível com várias regiões do Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122241"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Experiência do teams em uma locação habilitada para várias regiões do Microsoft 365

O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Microsoft 365 e do Office 365. Ele é oferecido pelo serviço Microsoft 365 groups juntamente com o SharePoint Online e o OneDrive for Business para a experiência de seus arquivos. Em uma locação de várias regiões do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, para que a experiência das equipes com colaboração de arquivos também seja compatível com várias regiões. Essa funcionalidade é uma importante funcionalidade de ponta para as equipes que hospedam arquivos que são hospedados em vários GEOS em sua experiência com arquivos nativos. Isso também inclui arquivos do OneNote e wiki.

Por exemplo, em um aluguel da contoso com Europa como uma região satélite satélite e na América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia **arquivos** no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e os Estados Unidos seja o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição **recente** . Os arquivos recentes podem incluir arquivos compartilhados de usuários em outros locais geográficos. 

Um site do SharePoint da equipe específico também é compatível com várias regiões. Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site do SharePoint correspondente será criado no local da Europa. Os arquivos associados a essa equipe serão mantidos em repouso nesse local. Qualquer experiência subsequente, como carregar um novo arquivo ou editar o arquivo, será armazenada nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.

Como uma locação de várias regiões é um único locatário global, durante a @ menção, os usuários de satélite poderão ver seus colegas em todo o mundo, onde quer que estejam.

Conversas em chats, mensagens de canais e notas de chat/chats da reunião dentro da experiência do Teams não são compatíveis com várias regiões e são mantidas apenas dentro do local central do locatário. Geralmente, as conversas de chat não são aplicadas às necessidades de residência de dados. Para obter mais informações, consulte [localização de dados no Microsoft Teams](location-of-data-in-teams.md).

Para obter mais informações sobre a região geográfica, consulte a [página recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).
