---
title: Experiência do teams em uma locação do Microsoft 365 ou do Office 365 do OneDrive e do SharePoint Online habilitado para várias regiões
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Neste artigo, você aprenderá a usar o Microsoft Teams em uma locação do Microsoft 365 ou do Office 365 do OneDrive e do SharePoint Online com várias regiões habilitadas para várias regiões.
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
ms.openlocfilehash: de73dc3edff66bfe8b427e570bfc661e1dec46b4
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689677"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Experiência do teams em uma locação do Microsoft 365 ou do Office 365 do OneDrive e do SharePoint Online habilitado para várias regiões
===========================================

O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Microsoft 365 e do Office 365. Ele é oferecido pelo serviço Microsoft 365 groups juntamente com o SharePoint Online e o OneDrive for Business para a experiência de seus arquivos. Em uma locação de várias regiões do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, portanto, a experiência das equipes com colaboração de arquivos também é compatível com várias regiões. Esta é uma importante funcionalidade de ponta para o uso de arquivos de superfície hospedados em vários GEOS em sua experiência nativa de arquivos.

Por exemplo, em um aluguel da contoso com Europa como uma região satélite e uma América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia arquivos no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e os Estados Unidos seja o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição recente. Os arquivos recentes podem incluir arquivos compartilhados com o usuário de usuários em outras GEOS e podem ser mestres em outros locais geográficos nos quais o locatário é estendido. 

Um site de grupo específico da equipe também reconhece várias regiões. Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site de grupos correspondentes será criado no local da Europa e os arquivos associados a esse grupo serão mantidos em repouso nesse local. Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão direcionadas para esse local europeu, mantendo a promessa de residência de dados para esses arquivos. Isso é tudo o que se torna possível pelos grupos base do Microsoft 365 tornando o reconhecimento de várias regiões.

Como uma locação de várias regiões é um único locatário global, durante a @ menção, os usuários de satélite poderão ver seus colegas em todo o mundo, onde quer que eles estejam. 

Observe que as conversas em chats e as anotações de mensagem instantânea da reunião dentro da experiência do usuário não são compatíveis com várias regiões e são mantidas apenas dentro do local central do locatário. Geralmente, as conversas de chat não são aplicadas às necessidades de residência de dados.

Para obter mais informações sobre a região geográfica, consulte a [página recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).