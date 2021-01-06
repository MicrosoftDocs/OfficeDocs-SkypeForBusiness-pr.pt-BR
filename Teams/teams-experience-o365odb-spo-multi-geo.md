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
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757746"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Experiência do teams em uma locação habilitada para várias regiões do Microsoft 365

O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Microsoft 365. Ele é oferecido pelo serviço Microsoft 365 groups juntamente com o SharePoint e o OneDrive para sua experiência com arquivos. Em uma organização de várias regiões na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, para que a experiência das equipes com colaboração de arquivos também seja compatível com várias regiões. Isso permite que as equipes surfacem arquivos hospedados em várias localizações geográficas em sua experiência nativa de arquivos.

Por exemplo, em um aluguel da contoso com Europa como uma região satélite e uma América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia arquivos no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e os Estados Unidos seja o local central do locatário. Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição recente. Os arquivos recentes podem incluir arquivos compartilhados de usuários em outros locais geográficos. 

Um site do SharePoint da equipe específico também reconhece várias regiões. Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site do SharePoint correspondente será criado no local da Europa e os arquivos associados a essa equipe serão mantidos em repouso nesse local. Qualquer experiência subsequente, como carregar um novo arquivo ou editar o arquivo, será armazenada nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.

Observe que as conversas em chats e as anotações de mensagem instantânea da reunião dentro da experiência do Teams não são compatíveis com várias regiões e são mantidas somente dentro do local central da organização.

Para obter mais informações sobre a região geográfica, consulte [recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).
