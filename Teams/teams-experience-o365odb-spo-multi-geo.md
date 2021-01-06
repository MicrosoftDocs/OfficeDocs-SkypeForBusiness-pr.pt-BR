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
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="a2ab8-103">Experiência do teams em uma locação habilitada para várias regiões do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2ab8-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="a2ab8-104">O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="a2ab8-105">Ele é oferecido pelo serviço Microsoft 365 groups juntamente com o SharePoint e o OneDrive para sua experiência com arquivos.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="a2ab8-106">Em uma organização de várias regiões na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, para que a experiência das equipes com colaboração de arquivos também seja compatível com várias regiões.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="a2ab8-107">Isso permite que as equipes surfacem arquivos hospedados em várias localizações geográficas em sua experiência nativa de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="a2ab8-108">Por exemplo, em um aluguel da contoso com Europa como uma região satélite e uma América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia arquivos no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e os Estados Unidos seja o local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="a2ab8-109">Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição recente.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="a2ab8-110">Os arquivos recentes podem incluir arquivos compartilhados de usuários em outros locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="a2ab8-111">Um site do SharePoint da equipe específico também reconhece várias regiões.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="a2ab8-112">Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site do SharePoint correspondente será criado no local da Europa e os arquivos associados a essa equipe serão mantidos em repouso nesse local.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="a2ab8-113">Qualquer experiência subsequente, como carregar um novo arquivo ou editar o arquivo, será armazenada nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="a2ab8-114">Observe que as conversas em chats e as anotações de mensagem instantânea da reunião dentro da experiência do Teams não são compatíveis com várias regiões e são mantidas somente dentro do local central da organização.</span><span class="sxs-lookup"><span data-stu-id="a2ab8-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="a2ab8-115">Para obter mais informações sobre a região geográfica, consulte [recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="a2ab8-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
