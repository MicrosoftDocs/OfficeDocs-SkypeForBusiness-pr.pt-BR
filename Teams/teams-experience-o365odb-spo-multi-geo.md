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
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="4204a-103">Experiência do teams em uma locação habilitada para várias regiões do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4204a-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="4204a-104">O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Microsoft 365 e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4204a-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="4204a-105">Ele é oferecido pelo serviço Microsoft 365 groups juntamente com o SharePoint Online e o OneDrive for Business para a experiência de seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="4204a-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="4204a-106">Em uma locação de várias regiões do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, para que a experiência das equipes com colaboração de arquivos também seja compatível com várias regiões.</span><span class="sxs-lookup"><span data-stu-id="4204a-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="4204a-107">Essa funcionalidade é uma importante funcionalidade de ponta para as equipes que hospedam arquivos que são hospedados em vários GEOS em sua experiência com arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="4204a-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="4204a-108">Isso também inclui arquivos do OneNote e wiki.</span><span class="sxs-lookup"><span data-stu-id="4204a-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="4204a-109">Por exemplo, em um aluguel da contoso com Europa como uma região satélite satélite e na América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia **arquivos** no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e os Estados Unidos seja o local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="4204a-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="4204a-110">Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição **recente** .</span><span class="sxs-lookup"><span data-stu-id="4204a-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="4204a-111">Os arquivos recentes podem incluir arquivos compartilhados de usuários em outros locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="4204a-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="4204a-112">Um site do SharePoint da equipe específico também é compatível com várias regiões.</span><span class="sxs-lookup"><span data-stu-id="4204a-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="4204a-113">Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site do SharePoint correspondente será criado no local da Europa.</span><span class="sxs-lookup"><span data-stu-id="4204a-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="4204a-114">Os arquivos associados a essa equipe serão mantidos em repouso nesse local.</span><span class="sxs-lookup"><span data-stu-id="4204a-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="4204a-115">Qualquer experiência subsequente, como carregar um novo arquivo ou editar o arquivo, será armazenada nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="4204a-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="4204a-116">Como uma locação de várias regiões é um único locatário global, durante a @ menção, os usuários de satélite poderão ver seus colegas em todo o mundo, onde quer que estejam.</span><span class="sxs-lookup"><span data-stu-id="4204a-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="4204a-117">Conversas em chats, mensagens de canais e notas de chat/chats da reunião dentro da experiência do Teams não são compatíveis com várias regiões e são mantidas apenas dentro do local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="4204a-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="4204a-118">Geralmente, as conversas de chat não são aplicadas às necessidades de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="4204a-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="4204a-119">Para obter mais informações, consulte [localização de dados no Microsoft Teams](location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4204a-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="4204a-120">Para obter mais informações sobre a região geográfica, consulte a [página recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="4204a-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
