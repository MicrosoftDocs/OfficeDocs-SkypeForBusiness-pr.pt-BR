---
title: Experiência do Teams em um ambiente habilitado para Multi-Geo do Microsoft 365
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
description: Neste artigo, você aprenderá sobre como usar o Teams em um ambiente habilitado para Multi-Geo do Microsoft 365.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760534"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Experiência do Teams em uma área de trabalho do Microsoft 365 Multi-Geo-enabled

O Microsoft Teams é um software de chat em grupo, o hub para trabalho em equipe no Microsoft 365 e no Office 365. Ele é alimentado pelo serviço grupos do Microsoft 365 juntamente com o SharePoint Online e o OneDrive for Business para sua experiência de arquivos. Em uma locação multi-geográfica do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é multi-geo-ciente, portanto, a experiência do Teams com colaboração de arquivos também é multi-geográfica. Essa funcionalidade é um recurso de ponta-chave para o Teams para superfícier arquivos hospedados em vários Geos em sua experiência de arquivos nativos. Isso também inclui arquivos do OneNote e Wiki.

Por exemplo, em uma locação contoso com a Europa como satélite Geo e América do Norte como  o Geo central, um usuário de satélite europeu verá seus arquivos do OneDrive na guia Arquivos no painel esquerdo, embora os arquivos sejam hospedados no local de dados da Europa e os Estados Unidos sejam o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente na **folha de exibição** Recente. Arquivos recentes podem incluir arquivos compartilhados de usuários em outras localizações geográficas. 

Um determinado site do SharePoint da equipe também é multi-geo-ciente. Ou seja, se um usuário de satélite europeu estiver criando uma Equipe, o site do SharePoint correspondente será criado no local da Europa. Os arquivos associados a essa Equipe serão mantidos em repouso nesse local. Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão armazenadas nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.

Como uma locação Multi-Geo é um único locatário global, durante @ menciona que os usuários de satélite poderão ver seus colegas de todo o mundo, independentemente de onde estão.

Conversas em chats, mensagens de canais e anotações/chats de IM de reunião dentro da experiência do Teams não têm conhecimento multi-geo e são mantidas somente no local central do locatário. Normalmente, as conversas de chat não são aplicadas às necessidades de residência de dados. Para obter mais informações, [consulte Local dos dados no Microsoft Teams](location-of-data-in-teams.md).

O suporte multi-geo para o Teams está no [roteiro do Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)

Para obter mais informações sobre Multi-Geo, consulte a página Recursos [Multi-Geo da Microsoft](https://aka.ms/multi-geo).
