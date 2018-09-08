---
title: Experiência de equipes em um inquilino Multi-Geo-enabled OneDrive do Office 365 e no SharePoint Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: Saiba mais sobre o uso de equipes em uma locação Multi-Geo-enabled OneDrive do Office 365 e no SharePoint Online.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68e3acc139894f98ec2d13e0c3e7bc3ec30042f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882940"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Experiência de equipes em um inquilino Multi-Geo-enabled OneDrive do Office 365 e no SharePoint Online
===========================================

Microsoft Teams é o software de bate-papo de grupo, o hub para o trabalho em equipe no Office 365. Ele é possibilitado pelo serviço de grupos do Office 365, juntamente com o SharePoint Online e o OneDrive for Business para sua experiência de arquivos. Em um OneDrive for Business/SharePoint Online Multi-Geo locação, no qual o inquilino é estendido para muitos locais geográficos como América do Norte, Europa e Austrália, a experiência de arquivos subjacente for Multi-Geo ciente, para que as equipes de experiência com o arquivo colaboração também está ciente Multi-Geo. Esse é um recurso de ponta principal para que as equipes a superfície arquivos hospedados em vários Geos na sua experiência de arquivos nativos.

Por exemplo, em um locatário Contoso com Europa como um satélite Geo e América do Norte como o Geo central, um usuário de satélite Europeu verão seu arquivos OneDrive da guia arquivos no painel esquerdo, embora os arquivos são hospedados no local dos dados Europa e o Stat United es é o local de central de locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob o blade recente do modo de exibição. Arquivos recentes podem incluir arquivos compartilhados com o usuário dos usuários em outros Geos e podem ser administrados em outras localidades Geo estendido para o inquilino. 

Site da equipe de um determinado grupo também é Multi-Geo ciente. Ou seja, se um usuário de satélite Europeu está criando uma equipe, o site de grupos correspondente será criado no local Europa e os arquivos associados que o grupo de equipe será mantido em repouso nesse local. Qualquer experiências subsequentes, como carregar um novo arquivo ou a edição do arquivo, serão direcionadas ao local europeu, mantendo a promessa de residência de dados para esses arquivos. Isso é tudo possibilitado pela foundation subjacente se tornando Multi-Geo ciente de grupos do Office 365.

Como um locatário Multi-Geo é um único locatário global, durante @ menções satélite os usuários poderão ver seus colegas em todo o mundo, não importa onde residem. 

Observe que não estão ciente Multi-Geo conversas em bate-papos e anotações de mensagens Instantâneas dentro a experiência de equipes de reunião e que estão todos mantidos somente dentro do local central do inquilino. Normalmente, as conversas de bate-papo não serão aplicadas às necessidades de residência de dados.

Para obter mais informações sobre o Office 365 Multi-Geo, consulte a [página de recursos do Microsoft Multi-Geo](https://aka.ms/multi-geo).