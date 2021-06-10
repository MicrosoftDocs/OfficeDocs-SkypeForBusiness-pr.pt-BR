---
title: Teams experiência em um ambiente Microsoft 365 multi-geo-habilitado
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
description: Neste artigo, você aprenderá sobre como usar Teams em um ambiente Microsoft 365 multi-geo-habilitado.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760534"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams experiência em uma Microsoft 365 multi-geo-habilitada para vários ambientes

Microsoft Teams é o software de chat em grupo, o hub para o trabalho em equipe Microsoft 365 e Office 365. Ele é alimentado pelo serviço Microsoft 365 Grupos, juntamente com o SharePoint Online e OneDrive for Business para sua experiência de arquivos. Em uma locação de OneDrive for Business/SharePoint Online com Multi-Geo, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é multi-geo-ciente, portanto, Teams experiência com colaboração de arquivos também é multi-geo-ciente. Essa funcionalidade é um recurso de ponta-chave para Teams arquivos de superfície hospedados em vários Geos em sua experiência de arquivos nativos. Isso também inclui arquivos OneNote e Wiki.

Por exemplo, em uma locação da Contoso com a Europa como satélite Geo e América do Norte como  o Geo central, um usuário de satélite europeu verá seus arquivos de OneDrive na guia Arquivos no painel esquerdo, embora os arquivos sejam hospedados no local de dados da Europa e os Estados Unidos sejam o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente na **folha de exibição** Recente. Arquivos recentes podem incluir arquivos compartilhados de usuários em outras localizações geográficas. 

Um determinado site de SharePoint equipe também é multi-geo-ciente. Ou seja, se um usuário de satélite europeu estiver criando uma Equipe, o site de SharePoint correspondente será criado no local da Europa. Os arquivos associados a essa Equipe serão mantidos em repouso nesse local. Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão armazenadas nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.

Como uma locação Multi-Geo é um único locatário global, durante @ menciona que os usuários de satélite poderão ver seus colegas de todo o mundo, independentemente de onde estão.

Conversas em chats, mensagens de canais e anotações/chats de IM de reunião dentro da experiência Teams não têm conhecimento multi-geo e são mantidas somente no local central do locatário. Normalmente, as conversas de chat não são aplicadas às necessidades de residência de dados. Para obter mais informações, [consulte Local dos dados em Microsoft Teams](location-of-data-in-teams.md).

O suporte multi-geo para Teams está [no mapa Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).

Para obter mais informações sobre Multi-Geo, consulte a página Recursos [Multi-Geo da Microsoft](https://aka.ms/multi-geo).
