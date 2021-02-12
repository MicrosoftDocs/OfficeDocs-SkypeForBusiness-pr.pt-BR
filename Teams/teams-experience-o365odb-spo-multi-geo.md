---
title: Experiência do Teams em um ambiente habilitado para vários geomos do Microsoft 365
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
description: Neste artigo, você aprenderá a usar o Teams em um ambiente habilitado para Várias Geos do Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122241"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Experiência do Teams em uma navegação multi-geo habilitada para o Microsoft 365

O Microsoft Teams é um software de chat em grupo, o hub para trabalho em equipe no Microsoft 365 e no Office 365. Ele é desenvolvido pelo serviço Grupos do Microsoft 365 juntamente com o SharePoint Online e o OneDrive for Business para sua experiência de arquivos. Em uma locação multi-geográfica do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é de ciências geográficas multi-geográficas, portanto, a experiência do Teams com colaboração de arquivos também é multi-geográfica. Essa funcionalidade é um recurso de ponta-chave para o Teams superfícier arquivos hospedados em vários Geos em sua experiência de arquivos nativos. Isso também inclui arquivos Do OneNote e Wiki.

Por exemplo, em uma locação da Contoso com a Europa como um satélite Geo e América do  Norte como a Geo central, um usuário de satélite europeu verá seus arquivos do OneDrive sob a guia Arquivos no painel esquerdo, embora os arquivos sejam hospedados no local de dados da Europa e os Estados Unidos sejam o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob **a folha de exibição** Recentes. Arquivos recentes podem incluir arquivos compartilhados de usuários em outros locais geo. 

Um determinado site do SharePoint da equipe também está ciente de vários pontos. Ou seja, se um usuário de satélite europeu estiver criando uma Equipe, o site do SharePoint correspondente será criado no local da Europa. Os arquivos associados a essa Equipe serão mantidos em repouso nesse local. Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão armazenadas nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.

Como uma locação Multi-Geo é um locatário global único, durante @menções usuários de satélite poderão ver seus colegas de todo o mundo, independentemente de onde eles estão.

As conversas em chats, mensagens de canais e anotações de mensagens de chat de reunião dentro da experiência do Teams não são multi-geográficas e são mantidas somente dentro do local central do locatário. Normalmente, as conversas de chat não são aplicadas às necessidades de residência de dados. Para saber mais, confira [a localização dos dados no Microsoft Teams.](location-of-data-in-teams.md)

Para obter mais informações sobre a Multi-Geo, consulte a página recursos [multi-geo da Microsoft.](https://aka.ms/multi-geo)
