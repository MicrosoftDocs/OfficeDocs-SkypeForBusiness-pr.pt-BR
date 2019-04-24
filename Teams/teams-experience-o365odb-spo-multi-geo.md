---
title: A experiência no Teams em um locatário do OneDrive do Office 365 e SharePoint Online com Funcionalidades Multigeográficas
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
description: Saiba mais sobre o uso de equipes em uma locação Multi-Geo-enabled OneDrive do Office 365 e no SharePoint Online.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e90e4a3c1ae2886a01802a805da3464cea3d8b50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204495"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>A experiência no Teams em um locatário do OneDrive do Office 365 e SharePoint Online com Funcionalidades Multigeográficas
===========================================

Microsoft Teams é o software de bate-papo de grupo, o hub para o trabalho em equipe no Office 365. Ele é possibilitado pelo serviço de grupos do Office 365, juntamente com o SharePoint Online e o OneDrive for Business para sua experiência de arquivos. Em um OneDrive for Business/SharePoint Online Multi-Geo locação, no qual o inquilino é estendido para muitos locais geográficos como América do Norte, Europa e Austrália, a experiência de arquivos subjacente for Multi-Geo ciente, para que as equipes de experiência com o arquivo colaboração também está ciente Multi-Geo. Esse é um recurso de ponta principal para que as equipes a superfície arquivos hospedados em vários Geos na sua experiência de arquivos nativos.

Por exemplo, em um locatário Contoso com Europa como um satélite Geo e América do Norte como o Geo central, um usuário de satélite Europeu verão seu arquivos OneDrive da guia arquivos no painel esquerdo, embora os arquivos são hospedados no local dos dados Europa e o Stat United es é o local de central de locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob o blade recente do modo de exibição. Arquivos recentes podem incluir arquivos compartilhados com o usuário dos usuários em outros Geos e podem ser administrados em outras localidades Geo estendido para o inquilino. 

Site da equipe de um determinado grupo também é Multi-Geo ciente. Ou seja, se um usuário de satélite Europeu está criando uma equipe, o site de grupos correspondente será criado no local Europa e os arquivos associados que o grupo de equipe será mantido em repouso nesse local. Qualquer experiências subsequentes, como carregar um novo arquivo ou a edição do arquivo, serão direcionadas ao local europeu, mantendo a promessa de residência de dados para esses arquivos. Isso é tudo possibilitado pela foundation subjacente se tornando Multi-Geo ciente de grupos do Office 365.

Como um locatário Multi-Geo é um único locatário global, durante @ menções satélite os usuários poderão ver seus colegas em todo o mundo, não importa onde residem. 

Observe que não estão ciente Multi-Geo conversas em bate-papos e anotações de mensagens Instantâneas dentro a experiência de equipes de reunião e que estão todos mantidos somente dentro do local central do inquilino. Normalmente, as conversas de bate-papo não serão aplicadas às necessidades de residência de dados.

Para obter mais informações sobre o Office 365 Multi-Geo, consulte a [página de recursos do Microsoft Multi-Geo](https://aka.ms/multi-geo).