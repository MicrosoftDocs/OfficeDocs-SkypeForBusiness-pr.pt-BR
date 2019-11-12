---
title: A experiência no Teams em um locatário do OneDrive do Office 365 e SharePoint Online com Funcionalidades Multigeográficas
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Saiba mais sobre como usar o Microsoft Teams em um Office 365 para o OneDrive e o SharePoint Online habilitados para várias regiões.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe181e7ef55b386d4a6eb40bb7e383ca89a956d9
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231242"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>A experiência no Teams em um locatário do OneDrive do Office 365 e SharePoint Online com Funcionalidades Multigeográficas
===========================================

O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Office 365. Ele é oferecido pelo serviço grupos do Office 365, juntamente com o SharePoint Online e o OneDrive for Business, para que seus arquivos tenham experiência. Em uma locação de várias regiões do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, portanto, a experiência das equipes com colaboração de arquivos também é compatível com várias regiões. Esta é uma importante funcionalidade de ponta para o uso de arquivos de superfície hospedados em vários GEOS em sua experiência nativa de arquivos.

Por exemplo, em um aluguel da contoso com Europa como uma região satélite satélite e na América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia arquivos no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e na estatística do país es é o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição recente. Os arquivos recentes podem incluir arquivos compartilhados com o usuário de usuários em outras GEOS e podem ser mestres em outros locais geográficos nos quais o locatário é estendido. 

Um site de grupo específico da equipe também reconhece várias regiões. Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site de grupos correspondentes será criado no local da Europa e os arquivos associados a esse grupo serão mantidos em repouso nesse local. Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão direcionadas para esse local europeu, mantendo a promessa de residência de dados para esses arquivos. Isso é tudo o que se torna possível pelos grupos base do Office 365 com reconhecimento de várias regiões.

Como uma locação de várias regiões é um único locatário global, durante a @ menção, os usuários de satélite poderão ver seus colegas em todo o mundo, onde quer que eles estejam. 

Observe que as conversas em chats e as anotações de mensagem instantânea da reunião dentro da experiência do usuário não são compatíveis com várias regiões e são mantidas apenas dentro do local central do locatário. Geralmente, as conversas de chat não são aplicadas às necessidades de residência de dados.

Para obter mais informações sobre o Office 365 multi-Geo, consulte a [página recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).